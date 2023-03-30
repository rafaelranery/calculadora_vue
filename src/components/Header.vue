<template>
    <header class="header">
        <div class="container">
            <img class="header__icon d-block w-100" src="https://www.svgrepo.com/show/501484/calculator.svg" alt="">
            <h1 class="header__title">Bem vindo a CalculaOnline!</h1>
            <p class="header__note">* Realizamos apenas operações aritméticas básicas.</p>
        </div>
    </header>
</template>

<style scoped>
    .header {
        text-align: center;
        margin-top: 64px;
        border-bottom: 10px dotted grey;
    }

    .header__icon {
        height: 96px;
        margin-bottom: 16px;
    }
    
    .header__note {
        font-size: 16px;
    }
</style>