# 滑动穿透问题

在移动端小程序开发中，如果跳出了一个弹窗，我们期望弹窗下面的内容是不可滑动的，在一般情况下，如果没有给弹窗组件加入“不可滚动”属性，底部的内容还是可滑动的，显然这是我们不期望发生的。

但是给弹窗组件加入了“不可滚动”属性后，弹窗组件内的子组件也会不可滚动了，如果我们希望它滚动的话，下面给出两种方案解决。

# mask 与弹窗同级，弹窗滚动区域和不可滚动区域同级

```html
<!-- 弹窗蒙层：
  disable-scroll 可阻止支付宝小程序滑动穿透
  catchtouchmove 可阻止微信小程序滑动穿透
  touchmove.prevent 可阻止H5滑动穿透
-->
<div class="mask-wrapper">
  <div class="mask">不可滚动</div>
  <div class="dialog">
    <div class="non-scrollable-content">不可滚动</div>
    <div class="scrollable-content"></div>
  </div>
</div>
```

# 监听滚动事件，动态修改能否滚动的属性

```html
<!--scrollable默认为false-->
<div class="mask-wrapper" :scrollable="{{scrollInContent}}">
  <div class="mask">
    <div class="dialog">
      <div class="content">
        当滚动事件在content发生时，把scrollInContent置为true，结束滚动置为false。
      </div>
    </div>
  </div>
</div>
```
