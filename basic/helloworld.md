# helloworld

首先需要继承 `Imoto` 类，写出你需要的 `component`

使用到es6的class，要是想兼容ie，用一波babel吧~

```
class example extends Imoto {
  get styleSheet() {return '.lala{border: 1px}'}
  get data() {
    return {
      hehe: false,
      items: ['11', '22', {a: 333}],
      val: ''
    }
  }
  created() {
    console.log('created!');
  }
  ready() {
    console.log('ready!');
    this.hehe = true;
  }
  get methods() {
    return {
      duang: function() {
        this.hehe = !this.hehe;
        this.items = ['11', '22'];
      },
      lala: function() {
        console.log(this.hehe);
      },
      itemClick: function(index) {
        console.log(index);
      },
      input: function() {
        console.log(this.val);
      }
    }
  }
  get template() {
    return `
      <button @click="duang">duang</button>
      <input @input="input" :model="val">
      <div :text="val"></div>
      <div class="lala" :if="hehe" :text="hehe" @click="lala"></div>
      <a :for="item in items">
        <span :text="item" @click="itemClick($index, item)"></span>
      </a>
    `;
  }
}
(new example()).render('body') // css选择器，渲染在某个DOM上
```

试试吧~几乎涵盖了Imoto的现有功能。

糊涂了？看看 [组件设置](../basic/component.md) 吧~
