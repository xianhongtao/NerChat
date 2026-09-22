# 加密协议

Matrix 的加密协议建立在成熟的密码学基础之上，用来保证聊天内容的安全。

## Olm库

Olm（libolm）是 Double Ratchet 加密棘轮在 C / C++ 中的独立实现，其中也包含 Matrix 使用的 Megolm“群组棘轮”算法。Olm 是整个 Matrix 密码学实现的核心依赖，您运行的每个 Matrix 客户端，以及我们的服务端，都用到了这个库。

Olm 库的仓库托管在 [GitLab](https://gitlab.matrix.org/matrix-org/olm) 上。

2016 年 9 月，NCC 集团的密码学部门对 Olm 1.3.0 进行了独立安全评估，您可以下载评估报告了解详情。

[https://www.nccgroup.com/globalassets/our-research/us/public-reports/2016/november/ncc_group_olm_cryptogrpahic_review_2016_11_01.pdf](https://www.nccgroup.com/globalassets/our-research/us/public-reports/2016/november/ncc_group_olm_cryptogrpahic_review_2016_11_01.pdf)

[https://matrix.org/blog/2016/11/21/matrixs-olm-end-to-end-encryption-security-assessment-released-and-implemented-cross-platform-on-riot-at-last/](https://matrix.org/blog/2016/11/21/matrixs-olm-end-to-end-encryption-security-assessment-released-and-implemented-cross-platform-on-riot-at-last/)

## Megolm

[Megolm](https://gitlab.matrix.org/matrix-org/olm/blob/master/docs/megolm.md) 是一种基于 AES 的双棘轮加密协议，用来加密群组聊天内容。当一条消息可能有大量接收者时，点对点加密方案（如 Olm）不再适用，Megolm 棘轮正是为此设计的；它还允许接收者反复解密同一条消息。例如在客户端／服务器架构中，密文副本可以存放在（不可信的）服务器上，客户端只需要保存会话密钥。

每个参与者都用各自的出站会话加密消息。会话由棘轮和一对 Ed25519 密钥组成：棘轮只能向前计算、不能反向推导，因此提供了保密性，并负责为每条消息派生一个独立的密钥；真实性则由 Ed25519 签名保证。棘轮的值和 Ed25519 公钥通过安全的点对点通道与其他参与者共享，Megolm 会话也因此继承了这条通道的特性——对参与者提供消息真实性，对第三方提供可否认性。

在 Matrix 中，Megolm 密钥库保存在用户本地，同时会经过加密后备份到服务器。Megolm 的应用范围其实很广，并不只用于人数众多的群聊，两人私聊同样由 Megolm 保护，这样做的目的主要是统一实现。
