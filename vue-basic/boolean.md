---
description: v-if v-else / v-show
---

# Boolean

```markup
<template>
  <div class="bool">

    <h2>v-if v-else / data: bool</h2>   
     
    <label><input type="checkbox" v-model="myVisible" />表示する</label>
    <p v-if="myVisible">ON!</p>
    <p v-else>Off</p>

    <h2>v-show</h2>
    <p v-show="vShow">v-show is display: on/off</p>

    <h2>Like</h2>
    <button v-if="isShow" @click="like">Like! for Method</button>

  </div>
</template>

<script>
export default {
  data() {
    return {      
      // bool init
      myVisible: true,
      vShow: false,
      isShow: true,
    }
  },
  methods: {
    like() {
      this.isShow = false
    },
  },
}
</script>

<style scoped lang="stylus">
</style>

```

