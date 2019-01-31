<template>
    <div class="converter">
        <h2>{{coinA}} to {{coinB}}</h2>
            <input type="text" v-bind:placeholder="coinA" v-model="coinA_value">
            <input type="button" value="Converter" v-on:click="convert()">
        <h2>{{coinB_value}}</h2>
    </div>
</template>

<script>
export default {
    name: "Converter",
    props: ['coinA', 'coinB'],
    data(){
        return {
            coinA_value: '',
            coinB_value: 0
        }
    },
    methods: {
        convert(){
            let from_to = `${this.coinA}_${this.coinB}`;
            let url = `https://free.currencyconverterapi.com/api/v6/convert?q=${from_to}&compact=y`
            fetch(url)
                .then(res => res.json())
                .then(json => {
                    let valueOfCoin = json[from_to].val;
                    this.coinB_value = (valueOfCoin * parseFloat(this.coinA_value)).toFixed(2);
                });
                

        }
    }
}
</script>

<style scoped>
    .converter{
        padding: 20px;
        max-width: 350px;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
        background-color: #FFF;
        margin-bottom: 10px
    }
</style>
