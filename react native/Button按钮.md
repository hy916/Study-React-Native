# Button

一个简单多平台使用的按钮组件。

该组件的样式是固定的。如果它的样式你不满意，那你可以使用`TouchableOpacity`或是`TouchableNativeFeedback`组件来定制自己所需要的按钮。

[TouchableOpacity]()

[TouchableNativeFeedback]()

**用法：**

```js
import { Button } from 'react-native';

        <Button
          title="确认"
          onPress={() => Alert.alert('确认之后不可更改！')}
        />

```

**文档：**

## onPress

用户点击此按钮时所调用的处理函数

## title

按钮内显示的文本

## accessibilityLabel

用于给残障人士显示的文本（比如会读取这一内容）

## color

文本的颜色(iOS)，或是按钮的背景色(Android)

## disabled

设置为 true 时此按钮将不可点击。

## testID

用来在端到端测试中定位此视图。

