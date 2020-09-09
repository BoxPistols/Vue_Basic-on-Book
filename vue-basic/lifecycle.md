# LifeCycle

```javascript
const vm = new Vue({
  el: '#app',
  data() {
    return {
      message: 'こんにちは'
    }
  },
  beforeCreate() {
    console.log('Vueインスタンス作成前')
  },
  created() {
    console.log('Vueインスタンス作成後')
  },
  beforeMount() {
    console.log('マウント前')
  },
  mounted() {
    console.log('マウント後') 
  },
  beforeUpdate() {
    console.log('再描画前')
  },
  updated() {
    console.log('再描画後')
  },
  beforeDestroy() {
    console.log('Vueインスタンス削除前')
  },
  destroyed() {
    console.log('Vueインスタンス削除後')
  }
})

window.vm = vm
```



