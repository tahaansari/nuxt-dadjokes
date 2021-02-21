<template>
    <div>
        <nuxt-link :to="'/jokes/'+id">
            {{joke}}
        </nuxt-link>
    </div>
</template>

<script>
export default {
    props:['joke','id'],
}
</script>

<style>

</style> 