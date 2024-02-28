<template>
    <div class="radio-button-container">
        <div class="radio-button-wrapper">
            <div v-for="(option, index) in answerOptions" :key="index">
                <input type="radio" :id="'radio' + (index + 1)" :name="'radios'" v-model="selectedOption" :value="option">
                <label :for="'radio' + (index + 1)" class="radio">{{ option }}</label>
            </div>
            <input type="radio" checked="true" id="radio4" name="check" @click="handleClick">
            <label for="radio4" class="radio">Check</label>
        </div>
    </div>
    <div>name : {{ name }}
        <input v-model="InputName">
        <button @click="setUpName">Set Name</button>
    </div>
</template>

<script>
import taskData from '../TaskData.json';

export default {
    data() {
        return {
            correctAnswer: taskData.correctAnswer,
            answerOptions: taskData.answerOptions,
            selectedOption: "",
            name: "Bob",
            InputName: ""
        }
    },
    methods: {

        setUpName(e){
            e.preventDefault();
            this.name = this.InputName
            
        },
        handleClick(e){
            this.checkAnswer();
            this.selectedOption = "";
        },
        FalseIfClicked(e) {
            if(e.target.checked){
                e.target.checked = false
            }
        },
        checkAnswer() {
            if (this.selectedOption === this.correctAnswer) {
                alert('Correct answer!');
            } else if (!this.selectedOption) {
                alert('Please select an answer!');
            }
            else {
                alert('Wrong answer!');
            }
            this.selectedOption = "";
        }
    }
}
</script>

<style>


.radio-button-container {
    display: grid;
  width: 100%;
  position: absolute;
  bottom: 0;
  height: auto;
  justify-self: center;
}
.radio-button-wrapper {
    padding: 20px 30px 20px 20px;
    display: grid;
    grid-template-columns: repeat(3, 1fr) auto;
    /* Разделение на 4 колонки */
    background-color: rgba(0, 0, 0, 0.041);
    gap: 10px;
}

.radio {
    text-align: center;
    border: 1px solid #ccc;
    padding: 10px;
    cursor: pointer;
}

.check-button {
    text-align: center;
    /* Центрирование текста */
    width: 10px;
    /* Ширина кнопки */
    border: 1px solid #ccc;
    /* Граница кнопки */
    padding: 10px;
    /* Меньший отступ для check-button */
    cursor: pointer;
    /* Курсор при наведении */
}

input[type="radio"] {
    display: none;
    /* Скрыть стандартные радио кнопки */
}

label.radio {
    display: inline-block;
    width: 90%;
    /* Ширина кнопки */
    text-align: center;
    /* Центрирование текста */
    border: 1px solid #ccc;
    /* Граница кнопки */
    cursor: pointer;
    /* Курсор при наведении */
    background-color: #ffffffa3;
    border-radius: 10px;
    transition: 0.3s ease;
    box-shadow: 0px 4px 4px rgba(0, 1, 50, 0.667);
}


input[type="radio"]:checked+label.radio {
    box-shadow: none;

    background-color: #e0e0e0;
    /* Цвет фона при выборе */
}

@media (max-width: 600px) {
    .radio-button-container {
        display: grid;
        width: 100%;
        position: absolute;
        bottom: 0;
    }
    .radio-button-wrapper {
    display: grid;
    /* Разделение на 4 колонки */
    grid-template-columns:  1fr;
    background-color: rgba(0, 0, 0, 0.041);
    gap: 10px;
    }
    .radio{
        width: 500px;
        margin-left: 6px;
    }
}


</style>
