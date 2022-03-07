# PROD
The performance risk open data
性能风险开放数据

随着系统架构复杂度的不断提高，DevOps实践的不断普及，来自应用性能风险规模和深度的挑战也越来越高。众所周知，性能风险的根因定位和调优本就非常复杂，费时费力，为了方便所有开发者能降低性能分析调优的成本，HeapDump性能社区(heapdump.cn)发起此开源项目，本着共建共享的精神，邀请大家一起来收集日常工作中遇到过的、解决过的性能风险信息，让所有开发者可以少走弯路了，提高效率。

#Schema 定义
本项目作为开放数据类型项目，贡献者们可以按此Schema定义贡献内容
{
	"tech-field": "技术领域",
	"tech-stack": "技术栈",
	"check-point": "技术点",
	"risk-item": "风险项",
	"risk-behavior": "风险表现",
	"root-cause": "根因描述",
	"check-out": "判断依据",
	"solution": "优化建议",
	"reference": "参考链接",
	"contributor": "贡献者姓名",
	"website": "贡献者个人网址"
}

示例如下：
{
	"tech-field": "虚拟机",
	"tech-stack": "JVM",
	"check-point": "codecache",
	"risk-item": "codecache 配置不合理",
	"risk-behavior": "应用运行了一段时间之后，Load飙升，处理能力下降，接口响应时间变长，在日志中发现有 CodeCache is full 记录",
	"root-cause": "JVM编译优化后的代码会存储在CodeCache，当CodeCache不足或者设置不合理时会导致热代码退优化或重复编译，导致性能下降",
	"check-out": "观察 ReservedCodeCacheSize 值是否为小于等于240M的默认值",
	"solution": "配置 -XX:ReservedCodeCacheSize 参数为一个大于240M默认值的合理值",
	"reference": "https://heapdump.cn/article/304430",
	"contributor": "占小狼",
	"website": "https://www.jianshu.com/u/90ab66c248e6"
}
