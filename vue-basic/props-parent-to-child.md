# Props Parent to Child

### [https://github.com/BoxPistols/m1-vue-dev](https://github.com/BoxPistols/m1-vue-dev)

`66a5ec64a2c5addb0d05a363c897b0ba4d9c8c02`

### Parent

#### Home.vue

```markup
<template>
    <div class="home">
        <img alt="Vue logo" src="../assets/logo.png" />
        <Dev01 dev01Msg="iI,m Developer" like="12" />
        <HelloWorld msg="Vue.js + TypeScript App" num="33" />
    </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Dev01 from '@/components/Dev01.vue'

@Options({
    components: {
        HelloWorld,
        Dev01,
    },
})
export default class Home extends Vue {}
</script>

<style lang="scss" scoped>
img {
    max-width: 48px;
}
</style>

```

### Child

#### Dev01.vue

```markup
<template>
    <div>
        <h1>Prop:dev01Msg = {{ dev01Msg }}</h1>
        <h2>{{ inputMsg }}</h2>
        <input type="text" v-model="inputMsg" />
        <button @click="doAction">Click doAction</button>
        <p>Like: {{ like }}</p>
        <p>halfNum: {{ halfNum }}</p>
    </div>
</template>
<script>
export default {
    props: {
        dev01Msg: String,
        like: Number,
    },
    data() {
        return {
            inputMsg: 'Hi!',
        }
    },
    computed: {
        halfNum() {
            return this.like / 2
        },
    },
    methods: {
        doAction() {
            this.inputMsg = 'Oh!!'
        },
    },
}
</script>

```

---

## Brush Up

![](../.gitbook/assets/image.png)

### Parent

```markup
<!-- 親コンポーネント -->
<template>
    <div class="home">
        <img alt="Vue logo" src="../assets/logo.png" />
        <dev01 hero-message="I'm developer" :like="likeNumber" />
        <dev01 hero-message="I'm designer" :like="likeNumber2" />
        Like: <input type="number" v-model="likeNumber" />
    </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
import Dev01 from '@/components/Dev01.vue'

@Options({
    data() {
        return {
            likeNumber: 50,
            likeNumber2: 70,
        }
    },
    components: {
        Dev01,
    },
})
export default class Home extends Vue {}
</script>

<style lang="scss" scoped>
img {
    max-width: 48px;
}
</style>

```

### Child

```markup
<!-- 子コンポーネント -->
<template>
    <div>
        <h3>{{ heroMessage }} / Like: {{ like }} / halfNum: {{ halfNum }}</h3>
    </div>
</template>
<script>
export default {
    props: {
        heroMessage: String,
        // like: Number,
        like: {
            type: Number,
            // required: true,  *defaultかrequiedかどちらか単一選択
            default: 0,
        },
    },
    data() {
        return {}
    },
    computed: {
        halfNum() {
            return this.like / 2
        },
    },
    methods: {},
}
</script>

```

