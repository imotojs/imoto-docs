# 组件设置

```
class example extends Imoto {
  get styleSheet() {return ...;}
  get data() {return ...;}
}
```

目前组件中可以设置如下值

#### styleSheet

设置样式。可以使用es6中的模板字符串书写

```
get styleSheet() {
  return `
    .item {margin: 2px;}
  `;
}
```

*现在还没有支持作用域，将在之后的版本中支持*

#### data

设置当前组件的内部变量与初值，可以是 `function` 之外的任何类型

```
get data() {
  return {
    bool: false,
    str: '',
    obj: {},
    num: 123
  };
}
```

#### props

设置当前组件在父组件中可使用属性，可以是 `function` 之外的任何类型

```
和data中一样，233~
```

*现在还没有支持类似 schema 的检测功能，将在之后的版本中支持*

#### methods

设置当前内部能使用的方法。

```
get methods() {
  return {
    duang() {}
  };
}
```

#### template

设置当前组件的html模板

get template() {
  return `...`;
}

详细的书写方式会在 [下一章](template/README.md) 给出。

#### 生命周期函数

会在 [下一节](basic/lifecycle.md) 给出
