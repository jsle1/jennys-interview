<template>
    <div>
        <div v-bind:key="city.id" v-for="city in city"> 
            <p>{{city.title}}</p>
        </div>
    </div> 
</template>

<script>
export default {
    name: "Cities",
    props: ["city"]
}
</script>

<style scoped>

</style>