# ActivityIndicator

显示一个圆形的 loading 提示符号。

**用法：**

```js

  <ActivityIndicator size="large" color="#0000ff" />

```

**文档：**

## animating

是否要显示指示器动画，默认为 true 表示显示，false 则隐藏。

## color

滚轮的前景颜色（iOS 上默认为灰色，安卓上默认为深绿色）。

## size

指示器的大小，默认为'small'。目前只能在 Android 上设定具体的数值。

## hidesWhenStopped

在 animating 为 false 的时候，是否要隐藏指示器（默认为 true）。如果animating和hidesWhenStopped都为 false，则显示一个静止的指示器。（iOS平台使用）
