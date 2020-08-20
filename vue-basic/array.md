---
description: Object
---

# Loop/Array Object



```markup
<template>
  <div class="">

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
      // Array obj v-for
      objArray: [
        { name: "メロンパン", price: 100 },
        { name: "ジャムパン", price: 120 },
        { name: "クロワッサン", price: 220 },
      ],
    }
  },
}
</script>

<style scoped lang="stylus">
</style>
```

