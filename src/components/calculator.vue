<template>
    <div class="ut-profit">
        <div>
            <span>Buying price</span>
            <input type="text" v-model="buying_price">
        </div>
        <div>
            <span>Sell price</span>
            <input type="text" v-model="sell_price">
        </div>
        <input type="button" class="button" value="Calcular" v-on:click="calculate">
        <h2>{{result}}</h2>
    </div>
</template>

<script>
export default {
    name: "Calculator",
    data() {
        return {
            buying_price: "",
            sell_price: "",
            result: 0
        }
    },
    methods: {
        calculate(){
            let tax = parseFloat(this.sell_price) * 0.05;
            let sale = parseFloat(this.sell_price) - parseFloat(tax);
            let profit = parseFloat(sale) - parseFloat(this.buying_price);
            return this.result = profit;
        }
    }
}
</script>

<style scoped>
.ut-profit{
    margin: auto;
    max-width: 700px;
    padding: 20px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

.ut-profit div span{
    display: block;
    margin-top: 20px;
}

.button {
    margin-top: 10px;
    padding: 5px;
}

</style>