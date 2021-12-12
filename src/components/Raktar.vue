<template>
    <table>
        <tr>
            <th>Title</th>
            <th>Price</th>
            <th>Quantity</th>
        </tr>
        <tr v-for="adat in adatok" :key="adat.title">
            <td> {{adat.title}} </td>
            <td> {{adat.price}} </td>
            <td> {{adat.quantity}} </td>
        </tr>
    </table>
</template>

<script>
export default {
    props: ['adatok']
}
</script>

<style scoped>
    table {
        width: 50%;
        margin: auto;
        border: 2px solid;
        text-align: center;
    }

    th {
        border-bottom: 2px solid black;
    }
</style>