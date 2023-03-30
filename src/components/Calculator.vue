<script setup>
const props = defineProps(['numAInput', 'signChange', 'numBInput', 'verificaCalc', 'numA', 'numB', 'sign', 'calcular'])

</script>

<template>
    <div class="container">
        <div class="calc-div">
            <input @keyup="props.numAInput" class="number-input" type="number" placeholder="0">
            <select class="operation-input" @change="props.signChange">
                <option value="">

                </option>
                <option value="+">
                    +
                </option>
                <option value="-">
                    -
                </option>
                <option value="*">
                    *
                </option>
                <option value="/">
                    /
                </option>
            </select>
            <input @keyup="props.numBInput" class="number-input" type="number" placeholder="0">
        </div>
        <div class="product-div">
            <p v-if="props.verificaCalc">{{ props.numA }} {{ props.sign }} {{ props.numB }} = {{ props.calcular }}</p>
            <p v-else>Realize uma conta! <span class="instructions-disclaimer">* São necessários dois dígitos e um operador.</span></p>
        </div>
    </div>
</template>

<style scoped>
.calc-div {
    display: flex;
    margin: 64px auto;
    max-width: fit-content;
    gap: 24px;
}

.number-input {
    max-width: 104px;
    /* height: 104px; */
    font-size: 44px;
    border-radius: 8px;
    outline: none;
    text-align: center;

}

.operation-input {
    border-radius: 50%;
    width: 88px;
    font-size: 44px;
    padding: 10px;
    text-align: center;
}

.product-div {
    text-align: center;
    width: 344px;
    margin: 0 auto;
    font-size: 64px;
}

.instructions-disclaimer {
    font-size: 14px;
    display: block;
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
}
</style>