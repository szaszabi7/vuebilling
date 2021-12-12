<template>
    <tr>
        <td> {{adat.title}} </td>
        <td> {{adat.price}} </td>
        <td> {{adat.quantity}} </td>
        <td> {{adat.quantity * adat.price}} </td>
        <td><button @click="deleteItem">X</button><button>Edit</button></td>
    </tr>
</template>

<script>
export default {
    props: ['adat'],
    methods: {
        deleteItem() {
            this.$emit("deleteItem", this.adat.title)
        }
    }
}
</script>

<style scoped>
    
</style>