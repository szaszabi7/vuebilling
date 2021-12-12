<template>
    <table>
        <tr>
            <th>Title</th>
            <th>Price</th>
            <th>Quantity</th>
            <th>Összérték</th>
            <th>Operations</th>
        </tr>
        <Item v-for="adat in adatok" :key="adat.title" :adat="adat" @deleteItem="deleteItem"/>
        <tr id="osszertek">
            <td colspan="3">Összérték:</td>
            <td> {{osszertek}} </td>
        </tr>
        <tr>
            <td><input type="text" v-model="title"></td>
            <td><input type="number" v-model="price"></td>
            <td><input type="number" v-model="quantity"></td>
            <td><button @click="addItem">Add</button></td>
        </tr>
    </table>
</template>

<script>
import Item from "./Item.vue";

export default {
    props: ['adatok', 'osszertek'],
    components:{
        Item
    },
    methods: {
        addItem() {
            this.$emit("addItem", {title: this.title, price: this.price, quantity: this.quantity})
            this.title = ""
            this.price = ""
            this.quantity = ""
        },
        deleteItem(e){
            this.$emit("deleteItem", e)
        }
    }
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

    #osszertek td{
        padding-top: 1em;
    }
</style>