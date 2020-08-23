<template>
    <div>
        <h1>Parent</h1>
        <h3>{{msg}}</h3> 
        <h5>vuex <span style="color: red">{{count}}</span></h5>
        <m-child v-bind:msg="'from Parent message'" @showMsg="showMsg" v-bind="$attrs"></m-child>

    </div>
</template>

<script>
    import MChild from './Child'
    export default {
        computed: {
            count() {
                return this.$store.state.count
            }
        },
        data() {
            return {
                msg: ''
            }
        },
        components: {
            MChild,
        },
        methods: {
            showMsg(val) {
                this.msg = val 
            }
        },
    }
</script>

<style scoped>

</style>>
