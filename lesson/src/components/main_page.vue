
<template>
    <main>
        <div class="container">
            <div class="coins">
                <p class="user-name">Anton</p>
                <div class="coins-container">
                    <span class="count-coins">1000</span>
                    <img class="coin-img" src="../assets/coin.png" alt="coin-image">
                </div>
            </div>
        </div>
    </main>
</template>
  
<script setup>

</script>

<style scoped>
body {
    padding: 0;
    margin: 0;
}

main {
    display: grid;
    width: 90%;
    margin-top: 25px;
}

.container {
    display: grid;
    grid-template-columns: 1fr auto;
}

.coins {
    margin: 0;
    padding: 0;
    line-height: 25px;
    justify-self: end;
}

.coins p, .coins img {
    margin: 0;
}

.coins-container{
    display: flex;
    align-items: center;
}

.coin-img {
    width: 20px;
    height: 20px;
}
</style>
