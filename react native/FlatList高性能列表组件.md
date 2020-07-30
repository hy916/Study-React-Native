高性能的简单列表组件，支持下面这些常用的功能：

* 完全跨平台。
* 支持水平布局模式。
* 行组件显示或隐藏时可配置回调事件。
* 支持单独的头部组件。
* 支持单独的尾部组件。
* 支持自定义行间分隔线。
* 支持下拉刷新。
* 支持上拉加载。
* 支持跳转到指定行（ScrollToIndex）。
* 支持多列布局。

如果需要分组/类/区（section），请使用`<SectionList>`。

[SectionList]()

**文档：**

## renderItem

从data中挨个取出数据并渲染到列表中。

```js
import { FlatList } from "react-native";

      <FlatList
        data={DATA}
        renderItem={renderItem}
        keyExtractor={(item) => item.id}
      />

```

本组件实质是基于`<VirtualizedList>`组件的封装，继承了其所有 props（也包括所有`<ScrollView>`)的 props）。

**注意的事项：**

* 当某行滑出渲染区域之外后，其内部状态将不会保留。请确保你在行组件以外的地方保留了数据。

* 本组件继承自PureComponent而非通常的Component，这意味着如果其props在浅比较中是相等的，则不会重新渲染。所以请先检查你的renderItem函数所依赖的props数据（包括data属性以及可能用到的父组件的 state），如果是一个引用类型（Object 或者数组都是引用类型），则需要先修改其引用地址（比如先复制到一个新的 Object 或者数组中），然后再修改其值，否则界面很可能不会刷新。（ [基本类型和引用类型](https://segmentfault.com/a/1190000002789651)。）

* 为了优化内存占用同时保持滑动的流畅，列表内容会在屏幕外异步绘制。这意味着如果用户滑动的速度超过渲染的速度，则会先看到空白的内容。这是为了优化不得不作出的妥协，你可以根据自己的需求调整相应的参数，而我们也在设法持续改进。
默认情况下每行都需要提供一个不重复的 key 属性。你也可以提供一个keyExtractor函数来生成 key。

## data

为了简化起见，data 属性目前只支持普通数组。如果需要使用其他特殊数据结构，例如 `immutable` 数组，请直接使用更底层的`VirtualizedList`组件。

[VirtualizedList]()

## ItemSeparatorComponent

行与行之间的分隔线组件。不会出现在第一行之前和最后一行

## ListEmptyComponent

列表为空时渲染该组件。可以是 React Component, 也可以是一个 render 函数，或者渲染好的 element。

```JS

  ListEmptyComponent={<View>{<Empty label="暂无数据" style={{ marginTop: 60 }} />}</View>}


```

## ListFooterComponent

尾部组件。可以是 React Component, 也可以是一个 render 函数，或者渲染好的 element。

## ListHeaderComponent

头部组件。可以是 React Component, 也可以是一个 render 函数，或者渲染好的 element。

