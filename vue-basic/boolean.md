---
description: if else v-show
---

# Boolean

```markup
<template>
  <div class="bool">
    <h2>v-if v-else / data: bool</h2>
    <label><input type="checkbox" v-model="myVisible" />表示する</label>
    <p v-if="myVisible">ON!</p>
    <p v-else>Off</p>

    <h3>v-show</h3>
    <p v-show="vShow">v-show is display: on/off</p>

    <h2>Like</h2>
    <button v-if="isShow" @click="like">Like!</button>

    <h2>Loop</h2>
    <table>
      <tr v-for="(item, index) in objArray" v-bind:key="index">
        <td>{{ item.name }}</td>
        <td>{{ item.price }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      myVisible: true,
      vShow: false,
      isShow: true,
      // Array obj v-for
      objArray: [
        { name: "メロンパン", price: 100 },
        { name: "ジャムパン", price: 120 },
        { name: "クロワッサン", price: 220 },
      ],
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
table
  width 50%
  max-width 400px
  margin auto
td
  border 1px solid
</style>

```

