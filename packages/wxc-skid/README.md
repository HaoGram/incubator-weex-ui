# wxc-skid

!> These rich interaction components are based on [BindingX](https://alibaba.github.io/bindingx/) feature. Make sure your app [install it](https://github.com/alibaba/bindingx#installation).

### Rule
- Only one row can be swiped at a time
- Hide operations by clicking on the right button or by clicking on the list.

## Code Example
```vue
<template>
<div>
    <WxcSkid @onNodeClick='onTest' :data='data'/>
</div>
</template>

<script>
import { WxcSkid } from 'weex-ui';
const modal = weex.requireModule("modal");

export default {
  components: {
    WxcSkid
  },
  data() {
    return {
      data: [
        {
          title: "标题1",
          right: [
            {
              text: "置顶",
              onPress: function() {
                modal.toast({
                  message: "置顶",
                  duration: 0.3
                });
              }
            },
            {
              text: "删除",
              onPress: () => {
                modal.toast({
                  message: "删除",
                  duration: 0.3
                });
              },
              style: { backgroundColor: "#F4333C", color: "white" }
            }
          ]
        },
        {
          title: "标题2",
          right: [
            {
              text: "删除",
              onPress: () => {
                modal.toast({
                  message: "删除",
                  duration: 0.3
                });
              },
              style: { backgroundColor: "#F4333C", color: "white" }
            }
          ]
        },
        {
          title: "标题3",
          right: [
            {
              text: "删除",
              onPress: () => {
                modal.toast({
                  message: "删除",
                  duration: 0.3
                });
              },
              style: { backgroundColor: "#F4333C", color: "white" }
            }
          ]
        }
      ]
    };
  },
  
  methods: {
    onTest(node, i) {
      modal.toast({
        message: node.title,
        duration: 0.3
      });
    }
  }
};
</script>
```

### API
|Prop|Type|Required|Default|Description|
|-------------|------------|--------|-----|-----|
|data|Array|Y|[]|list|

### API
|Prop|Description|Type|Default|
|-------------|------------|--------|-----|
|title|content|String|null|
|right|Right button group|Array|null|
|autoClose|Hide the button automatically after clicking the button|Boolean|false|

### Button
|Prop|Type|Description|
|-------------|------------|--------|
|text|String|copywriting|
|style|Object|button style|
|onPress|():void|click|

### Event

```
// click
`@onNodeClick='onTest'`
```
