
<cn>
#### 位置
可以设置通知从右上角、右下角、左下角、左上角弹出。
</cn>

<us>
#### Placement
A notification box can pop up from `topRight` or `bottomRight` or `bottomLeft` or `topLeft`.
</us>

```html
<template>
  <div>
    <select v-model="selected">
      <option v-for="val in options">{{val}}</option>
    </select>
    <a-button type="primary" @click="openNotification">Open the notification box</a-button>
  </div>
</template>
<script>
  const options = ['topLeft', 'topRight', 'bottomLeft', 'bottomRight'];
  export default {
    data () {
      return {
        options,
        selected: 'topRight',
      }
    },
    watch: {
      selected(val) {
        this.$notification.config({
          placement: val,
        });
      }
    },
    methods: {
      openNotification () {
        this.$notification.open({
          message: 'Notification Title',
          description: 'This is the content of the notification. This is the content of the notification. This is the content of the notification.',
        });
      },
    }
  }
</script>
```

