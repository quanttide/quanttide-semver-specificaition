# 预发布版本

本文约定预发布版本的使用方式。

## 正式版本 vs 预发布版本

简单地说，我们以正式版本定义约定给本项目开发者以外的用户，以预发布版本作为开发者自己在研发流程的阶段性标记。比如，课程平台PRD文档的0.1.0约定了产品团队读的PRD文档的整体结构包括用户故事、产品原型等部分。

因此，正式版本必须有规范详细的release note。具体的要求是，在仓库根目录维护CHANGELOG.md，按照标准CHANGELOG文件规范（具体规则直接搜索“CHANGELOD格式”即可）。

预发布版本只要求开发者自己写简单的备注说明预发布版本的目的，比如Alpha增加一些特性，Beta版本修复一些异常等等。

除非特殊情况，预发布版本不应该被其他项目使用。尽可能在本项目内完成外部项目需要的使用方式的测试。

## 预发布版本alpha, beta, rc

预发布版本格式以x.y.z-alpha/beta/rc.n的形式，以1, 2, 3等数字的方式增加版本号即可。

alpha版本约定本地开发版本。常见的情况是增加一系列特性时阶段性地标记。推荐一次几个小时的开发标记一次。不要求alpha版本是可以在云端使用的，或者整个项目在本地可以跑通。

beta版本约定云端测试版本。云端测试可用的最基础标准是整个项目可以跑通。一轮测试应该标记一次版本，部署流程以版本发布为触发条件。

rc版本约定内部评审版本。这个版本和正式版的唯一区别应当是版本号。主要的注意事项是保持实际特性和release note约定的一致。不要求rc版本甚至正式版本达到中版本预期的特性目标。如果发现出入较大，应当修改release note以符合实际实现，把计划的改动约定到下一个正式版本。未来rc版本还可能用来做AB测试的版本标记，具体取决于我们的技术架构。

注意不要使用dev.n，因为语义化版本按照字母顺序识别，dev会比alpha和beta版本高。

## release note维护建议

目前我们还没有采取clean git commit实践，考虑到实行难度比较大。因此没有条件从commit里生成release note，或者采取生成后手动维护的半自动化流程。目前采取手动维护版本release note的策略。建议每次commit或者预发布版本更新维护一次CHANGELOG，并且在rc或正式版本发布审查时再检查一遍。
