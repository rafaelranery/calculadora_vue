<script setup>
    

</script>

<template>
    <!-- <div class="container">
        <div class="calc-div">
            <input class="number-input" type="number" placeholder="0">
            <select class="operation-input">
                <option value="add">
                    +
                </option>
                <option value="subtract">
                    -
                </option>
                <option value="multiply">
                    *
                </option>
                <option value="divide">
                    /
                </option>
            </select>
            <input class="number-input" type="number" placeholder="0">
        </div>
        <div class="product-div">
            <p>1 + 2 = 0</p>
        </div>
    </div> -->
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
</style>