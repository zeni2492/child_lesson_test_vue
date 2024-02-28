<template>
    <main>
        <div class="top-button-container">
            <div class="top-button-wrapper">
                <div class="exit-button ">
                    <img class="exit-img" src="../assets/close_btn.png" alt="exit-image">
                </div>

                <div class="title">
                    <p class="title-text">Choose the right answer</p>
                    <p class="title-question">Which shape shows third</p>
                </div>

                <div class="tip-button " @click="showModal = true">
                    <img class="bulb-img" src="../assets/bulb.png" alt="bulb-image">
                </div>
            </div>
        </div>
        <div v-if="showModal" class="modal">
            <span class="close" @click="showModal = false">&times;</span>
            <div class="modal-content">
                <p>Right answer is C</p>
            </div>
        </div>
    </main>
</template>

<script>
export default {
    data() {
        return {
            showModal: false
        }
    }
}
</script>

<style scoped>
main {
    width: 90%;
    margin-top: 25px;
}

.top-button-wrapper {
    display: grid;
    grid-template-columns: auto 1fr auto;
    /* Распределение пространства между элементами */
    align-items: center;
    justify-content: center;
    padding: 20px;
}

.tip-button {
    align-self: start;
    justify-self: start;
    border: 1px solid black;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.667);
    background-color: rgba(0, 0, 0, 0.103);
    width: 35px;
    height: 35px;
    display: flex;
    border-radius: 10px;
    align-items: center;
    justify-content: center;
    cursor: pointer;
}

.modal {
    display: block;
    position: fixed;
    /* Фиксированное позиционирование */
    z-index: 1;
    /* Поверх других элементов */
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    width: 70%;
    /* Занимает всю ширину экрана */
    height: 70%;
    /* Занимает всю высоту экрана */
    overflow: auto;
    /* Добавляет прокрутку, если содержимое выходит за границы */
    background-color: rgba(0, 0, 0, 0.719);
    /* Полупрозрачный черный фон */
}

.close {
    color: #aaa;
    float: right;
    font-size: 40px;
    font-weight: bold;
    margin-right: 10px;
}

.close:hover,
.close:focus {
    color: black;
    text-decoration: none;
    cursor: pointer;
}

.modal-content {
    background-color: #fefefebd;
    /* Цвет фона модального окна */
    margin: 15% auto;
    text-align: center;
    /* Отступ сверху и снизу, автоматическое центрирование */
    padding: 20px;
    border: 1px solid #888;
    width: 80%;
    /* Ширина модального окна */
}

.bulb-img {
    width: 20px;
    height: 20px;
}

.exit-button {
    align-self: start;
    border: 1px solid black;
    width: 35px;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.667);
    background-color: rgba(0, 0, 0, 0.103);
    height: 35px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.exit-img {
    width: 20px;
    height: 20px;
}

.title {
    grid-column: 2;
    text-align: center;
    line-height: 10px;
    /* Центрирование текста */
}

.title-text {
    font-size: 14px;
}

.title-question {
    font-size: 28px;
}
@media (max-width: 500px){

    .top-button-wrapper {
        padding: 5px;
}

    .title-question {
    font-size: 16px;
}
}

</style>