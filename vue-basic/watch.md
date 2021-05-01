# Watch

### Option

```javascript
<template>
    <div class="about">
        <div class="container">
            <h1>WatchApp {{ tex }}</h1>

            <div class="row">
                <div class="col">
                    <ul v-for="color in colors" :key="color.id">
                        <li>{{ color.name }}</li>
                    </ul>
                    <button @click="changeColor">Change Color</button>
                    <div>{{ colorLog }}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
export default {
    props: {
        tex: String,
    },
    data() {
        return {
            colors: [{ name: 'red' }, { name: 'green' }, { name: 'blue' }],
            colorLog: 'colorLog',
        }
    },
    methods: {
        changeColor() {
            this.colors[1].name = 'pink'
            this.colorLog = this.colors[1].name
        },
    },
    watch: {
        colors: {
            handler(newVal, oldVal) {
                this.colorLog = this.colors[1].name

                console.log('Update')
                console.log(
                    'newVal: %s, oldVal: %s',
                    JSON.stringify(newVal, null, '\t'),
                    JSON.stringify(oldVal, null, '\t')
                )
            },
            deep: true,
            immediate: true,
        },
    },
}
</script>

<style lang="scss" scoped>
.col {
    margin-bottom: 12px;
    font-size: 20px;
}
ul,
li {
    list-style: none;
    margin: 4px 0 12px;
    line-height: 1.5;
}
</style>

```

