# 生命周期函数

目前做的比较粗糙，只有如下方法

#### created

在放置了 `props` 与 `data` 参数后立即执行， 此时并没有执行任何渲染操作

#### ready

在各种数据绑定，并在指定位置渲染DOM之后执行。

#### destoryed (未实现)

在该组件因为某些原因被销毁之后调用。

关于详细的内部实现方式可以在 [核心实现](../core/README.md) 中查看。
