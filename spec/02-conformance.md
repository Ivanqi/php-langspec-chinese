# 规范
在本规范中, "must"应解释为对实施或程序的要求;相反, "must not"应解释为禁止

如果违反了出现在约束之外的"must"或"must not"，则行为未定义.未定义的行为在本规范中以"未定义的行为"或任何明确的行为定义表示。这三者在重点上没有区别。它们都描述了"未定义行为"

"may"一词表示"permission" (允许)，同时从未用于表示允许"might"(可能)

*严格一致的程序* 必须仅使用本规范中描述的语言特征。 特别是，它不能产生输出或表现除依赖于任何未指定、未定义或实现定义的行为的行为

*规范实现* 必须接受任何严格规范的计划。规范实现可以有任何扩展，只要它们不改变任何严格规范程序的行为

*规范程序* 是规范实施的可接受的计划

规范实施必须附有一份文件，该文件定义了所有实施定义的特征和所扩展

一些语法部分后面是约束部分，这进一步限制了语法. 在发出约束违反诊断后，一致性实现可以继续程序执行。 在某些情况下，会记录这种延续行为(例如, 向函数传递的参数太少时会发生什么)。 使这些事情违反约束只是迫使发布诊断, 它不
要求程序执行

本规范包含被成为*信息性*或*非规范性文本*的解释性材料，严格来说，这些材料在正式语言规范中是不必要的。举例说明所述结构的可能形式. 参考文献用于指代相关条款. 注释和实现者注释用于向实现者或程序员提供建议或指导。资料性附录提供了附加信息，并总结了本规范中包含信息。所有未标记为信息性的文本均为*规范性文本*

某些功能被标记为*弃用*。 虽然这些是本规范当前版本的规范文件，但不保证在未来版本中存在。通常，它们是旧方法，已被新方法取代，不鼓励使用旧方法(这方面的例子包括使用大括号{})进行订阅，以及使用老式的构造函数名。