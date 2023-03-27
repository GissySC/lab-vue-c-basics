<template>
    <div id="content">
        <h1>The result of 2 + 2 is: {{ 2 + 2 }}</h1>
        <h2>{{ getMyString() }}</h2>
    </div>
</template>

<script>
export default {
    name: 'ContentComp',
    data() {
        return {
            msg1: 'Hooray!',
            msg2: 'You are a genius!'
        }
    },
    methods: {
        getMyString() {
            return `${this.msg1} ${this.msg2}`;
        }
    }
}
</script>

<style scoped>

    #content {
        background-color: coral;
        text-align: center;
    }

</style>