# 项目的 bug 管理

bug 管理文档，主要介绍如何提交 bug，以及这些 bug 如何管理、关闭、跟踪等

## bug 基本信息定义

bug 总共有以下状态：

- 新建
  - 下一步可流转状态：接受/处理、已拒绝、挂起、延期
- 接受/处理
  - 下一步可流转状态：转需求、已解决、已拒绝、挂起、延期
- 转需求
  - 下一步可流转状态：新建
- 已解决
  - 下一步可流转状态：重新打开、已关闭
- 重新打开
  - 下一步可流转状态：接受/处理
- 已拒绝
  - 下一步可流转状态：重新打开、已关闭
- 已关闭
  - 下一步可流转状态：重新打开
- 挂起
  - 下一步可流转状态：接受/处理
- 延期
  - 下一步可流转状态：接受/处理

bug 严重程度说明：

- 致命： 导致整个系统功能不可用、资金流转异常等
- 严重： 主要功能不可用，或者导致某个分支流 block 住
- 一般： 不影响其他功能的功能性 bug
- 提示：文案错误或者提示内容不友好
- 建议：非需求内的交互体验，不影响功能使用，但是可以提高交互友好型性或者效率

## 发现 bug 与 bug 提交

- 相关人员在使用产品、测试产品的过程中，发现 bug 之后，提交到测试同事，由测试同事统一管理。需要提供测试场景描述、问题描述等，最好能提供截图供测试人员复现 bug
- 测试人员收到其他同事的 bug，需自己再复现 bug，并进行一定的分析
- 测试人员在分析完 bug 之后，依据分析结果，在 tapd 上建立相应的缺陷，并指定模块负责人为缺陷处理人
- 填写 bug 时，需要填写的信息为：处理人、优先级、严重程度、发现版本、测试阶段、重现概率

## bug 的解决

- 开发人员需每次查看自己负责模块（迭代）的缺陷列表，并根据其优先级，逐一解决或者流转状态。无法定为到具体原因的，由小组组长定为之后再分配到人
- 如果 bug 涉及到了需求的改动，请及时通知产品进行商量和需求文档的改动
- 解决 bug 之后，提 PR 的时候，请将 bug 的 ID 附在 PR 的 commit message 内
- bug 处理完之后，及时流转其状态，以便检查

## issue 的关闭

基本原则：开发人员，处理、流转 bug 的状态，bug 的最终关闭，由测试人员在测试通过后进行关闭

- Bug 解决完之后，部署到测试环境，由测试人员验证，待通过之后，则可关闭相关 issue

## bug 报告

- 在模块开发、上线前，测试小组会发出模块测试报告
- 定期的，会做线上 bug 统计，并发出报告
