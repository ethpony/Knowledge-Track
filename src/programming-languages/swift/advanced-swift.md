# 《Swift 进阶》阅读纪要

《[Swift 进阶](https://objccn.io/products/advanced-swift/)》是 objc.io 出的[系列书籍](https://objccn.io/products/)之一，除此之外参与[码力全开](https://www.maliquankai.com/)公众号活动时，非常幸运地中到了实体书。在此记录阅读时记录的重点摘要。

## 泛型

使用泛型代码编程，可以写出可重用的函数和数据结构，只要满足所定义的约束，就能够使用各种类型。

* 重载：拥有同样的名字，但参数或返回类型不同的多个方法互相被称为重载方法。
  * 自由函数的重载
  * 运算符的重载
  * 使用泛型约束进行重载
  * 使用闭包对行为进行参数化

> 非通用的函数会优先于通用函数被使用。

> ⚠️ 重载的使用时在编译期间静态决定的。若需要运行时的多态，不应采用自由函数，而是定义为类型方法。

> 对于重载的运算符，类型检查器会使用非泛型版本，而不考虑泛型版本。

> 可以通过收紧序列元素类型的限制写出性能更好的版本。

* 对集合采用泛型操作
  * 泛型二分查找
  * Subsequence 和泛型算法
* 使用泛型进行代码设计
* 泛型的工作方式
  * witness table
  * 泛型特化
  * 全模块优化

// TODO: 结合 Gist 添加完整代码示例
