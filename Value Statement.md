



# Value Statement

## **SHECA的介绍和客户群体**

上海电子认证中心有限公司（SHECA）是中国最早成立的数字证书认证机构之一，已有25年历史。自2008年起，SHECA已连续17年通过WebTrust审计。为了进一步提升合规标准，SHECA正积极推进ETSI审计，预计到2026年，SHECA将成为中国首家同时满足WebTrust和ETSI双重审计标准的CA机构。

SHECA的SSL证书广泛应用于中国大陆的各行各业，包括教育、金融、大型互联网公司等。根据Statcounter最新报告，谷歌Chrome浏览器在中国大陆的市场份额为44.5%。根据这一数据，SHECA的SSL证书间接服务超过3000万Chrome用户，保障了用户在Chrome浏览器中的安全访问。

近年来，SHECA不断拓展海外市场，支持多语种国家（如中文、英文、阿拉伯语等）的证书申请。

## 免费指导

SHECA 提供了一系列免费的资源，包括指导文章、帮助文档和常见问题解答（FAQ），以支持用户社区在请求/续订证书或配置 TLS 时的需求。以下是关键支持选项：

1. **SHECA 知识库**：SHECA 网站上专门设立的知识库部分，提供详细的步骤指导，帮助用户完成证书请求、续订以及 TLS 配置。文章涵盖从简单的 SSL 证书安装到复杂的配置等多种使用场景。
2. **常见问题解答（FAQ）**：一个集中解答常见问题的页面，涵盖证书申请、验证和 TLS 设置相关的常见问题及解答。此部分还提供了技术问题的解决方案和故障排除技巧。
3. **TLS 配置帮助文章**：一系列技术文章和最佳实践指南，专注于如何正确配置 TLS 证书，适用于 Web 服务器、邮件服务器及其他服务。此类指南定期更新，以反映行业标准和 SHECA 特定的配置要求。
4. **证书管理帮助文章**：详细说明整个证书生命周期的文章，包括如何申请、续订和吊销证书。文中还包含了相关表单和门户的链接，以及在发生错误时的故障排除步骤。
5. **社区论坛与在线支持**：SHECA 提供在线支持论坛，用户可以在此提问和分享经验。此外，客户还可以通过电子邮件或在线聊天获取 SHECA 支持团队的帮助。
6. **视频教程**：SHECA 提供了一些视频教程，指导用户完成证书请求、TLS 配置及续订等过程。这些视频帮助用户更清晰地了解技术步骤。

通过提供这些资源，SHECA 致力于帮助用户社区自信地管理与证书相关的需求，确保用户能够顺利完成操作。

目前，上述文档和视频大部分为中文版本，SHECA正在积极推动翻译工作。同时，SHECA还在开发将相关知识库与AI技术结合的项目，计划推出针对SSL证书申请、 安装、部署、检测的的智能AI解决方案。



## SHECA TLS 证书PKI层次有效期承诺

为了遵循Google对根证书有效期的限制，SHECA自2025年1月1日起，所有签发的根证书有效期将不超过15年，Subordinate CA的有效期将不超过10年。此外，本次提交的两个TLS根证书将不会签发超过90天的订户证书。为应对高SLA要求的用户，SHECA正在推动使用短期证书（有效期小于10天），以避免大规模证书吊销对用户业务连续性造成冲突。

针对Google每五年轮换一次根证书的要求，SHECA正在积极推进相关工作，这一要求SHECA后续运营带来了一些挑战，需要一些时间去推进。



## Moving Forward, Together Practice

### **SHECA多用途根规划**

SHECA已有两个根证书在多家浏览器和操作系统的根证书库,根证书信息如下：

| CN                           | Hash                                                         | Trust Bit                  |
| ---------------------------- | ------------------------------------------------------------ | -------------------------- |
| UCA Extended Validation Root | D43AF9B35473755C9684FC06D7D8CB70EE5C28E773FB294EB41EE71722924D24 | WebSite，Email，Code Sign  |
| UCA Global G2 Root           | 9BEA11C976FE014764C1BE56A6F914B5A560317ABD9988393382E5161AA0493C | WebSite，Emaill，Code Sign |

SHECA已于2025年3月停止在旧根证书下签发任何非TLS用途的订阅证书，截止2025年9月23日吊销了所有非TLS用途的Subordinate CA证书。SHECA计划在2025年10月内向Mozilla请求移除该根证书的Email信任位，并向微软请求移除Email和Code Sign的信任位。

为全面符合Google对单一用途根证书的要求，SHECA预计将在2025年12月31日之前，将所有用于签发TLS证书的EKU（扩展密钥用途）切换至新签发的仅包含server-auth的中级根。原有的包含server-auth和server-client的中级根证书将全部停用，并将根据证书有效期逐步吊销。

### **SHECA旧根停用计划**

SHECA has two active root certificates in Google root store, UCA Extended Validation Root and UCA Global G2 Root. SHECA will cease issuing certificates under the old certificates when the single-purpose root certificates are included in the browser root stores.

停用时间表如下：

| CN                           | Hash                                                         | Stop issuing certificates |
| ---------------------------- | ------------------------------------------------------------ | ------------------------- |
| UCA Extended Validation Root | D43AF9B35473755C9684FC06D7D8CB70EE5C28E773FB294EB41EE71722924D24 | 2030-12-31                |
| UCA Global G2 Root           | 9BEA11C976FE014764C1BE56A6F914B5A560317ABD9988393382E5161AA0493C | 2030-12-31                |

### 抗量子算法SSL证书

为应对量子计算机对RSA和ECDSA算法的潜在冲击，SHECA正在积极推动公司内的POC（Proof of Concept）算法切换，并进行硬件设备的升级。预计到2027年下半年，SHECA将能够签发基于PQC（Post-Quantum Cryptography）算法的证书，以确保在量子计算时代的安全性和合规性。SHECA的这一举措旨在提前布局量子安全认证，并为客户提供未来-proof的数字安全解决方案。

### linting的支持

**签发流程中的Linting：**
 SHECA目前使用`pkimetal`和`certlint`对预证书进行Linting操作，以避免签发出格式错误的预证书。`pkimetal`和`certlint`至少每30天更新到最新的版本，确保规则与标准的及时更新。

**签发后Linting：**
 SHECA每天上午对所有有效期内的证书执行Linting操作，并对发现的错误证书进行内部报警。



## **SHECA自动化方案**

SHECA已完全实现满足Google Chrome Root Program Policy  4.3.1章节要求的的ACME自动化方案 包含ARI和，并且正在推动客户逐步切换至该方案。目前，约15%SHECA证书订户已经开始使用通过ACME签发的证书。由于OV（组织验证）和EV（扩展验证）SSL证书的ACME申请需要进行组织预审，因此暂时无法提供对外测试的KID（Key ID）。

| ACME endpoint                                                | Demo Site                      |
| ------------------------------------------------------------ | ------------------------------ |
| DV ACME URL:https://acme.imtrust.cn/v2/D10/directory <br />KID: JbMNCfGGEvgqvjmoatVT2BTXQJ                                                          <br />EHMAC: 1d0WDz_S9suzc1-9qvnqvWmqfMHcGGcVfMOkXUMUL44 | https://rsadv1a.acme.sheca.com |
| OV ACME URL:https://acme.imtrust.cn/v2/OV10/directory        | https://rsaov1a.acme.sheca.com |
| EV  ACME URL:https://acme.imtrust.cn/v2/EV10/directory       | https://rsaev1a.acme.sheca.com |

## **CT日志**

SHECA严格遵循Google的要求，所有Google根证书下签发的证书将至少上报至两家CT日志。为了进一步贡献于生态系统，SHECA正在筹备加入更多CT日志，计划预计在2026年底前完成CT日志的并入工作。
