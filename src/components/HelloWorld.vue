<template>
    <div class='hello'>
        <h1>{{ msg }}</h1>
    </div>
</template>

<script lang="ts">
// @ts-nocheck
import Vue from 'vue'
import { axios } from 'axios'
export default Vue.extend({
    name: 'HelloWorld',
    props: {
        msg: String,
    },
    created() {
        axios
            .get('/api', {
                params: {},
            })
            .then((res) => {
                console.log(res)
            })
            .catch((err) => {
                throw new Error('err')
            })
    },
})
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
h3 {
    margin: 40px 0 0;
}
ul {
    list-style-type: none;
    padding: 0;
}
li {
    display: inline-block;
    margin: 0 10px;
}
a {
    color: #42b983;
}
</style>
