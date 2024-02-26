<template>
    <div>
        <h1> Calulator Components</h1>
        <div class="form-wrapper">
            <div class="form-input">
                <label for="#">Number</label>
                <input type="number" name="number" id="" v-model="inputOne">
            </div>
            <div class="form-input">
                <label for="#">Number</label>
                <input type="number" name="number" id="" v-model="inputTwo">
            </div>
            <div class="form-input">
                <label for="#">Select Arithmetic Operation </label>

                <select class="form-select" name="" id="" v-model="selectOption">
                    <option selected>Select one</option>
                    <option value="+">+</option>
                    <option value="-">-</option>
                    <option value="*">*</option>
                    <option value="/">/</option>
                </select>

            </div>
            <div class="form-input">
                <button @click="calculatValue">Calculate</button>
            </div>
            <h2>Result: {{ result }}</h2>
        </div>
    </div>
</template>

<script setup>
import { ref } from "vue";

const inputOne = ref(0)
const inputTwo = ref(0)
const result = ref(0)

const selectOption = ref()

const calculatValue = ((e) => {
    if (selectOption.value === '+') {
        result.value = inputOne.value + inputTwo.value
    } else if (selectOption.value === '-') {
        result.value = inputOne.value - inputTwo.value
    } else if (selectOption.value === '*') {
        result.value = inputOne.value * inputTwo.value
    } else if (selectOption.value === '/') {
        result.value = inputOne.value / inputTwo.value
    } else {
        console.log('no value found');
        console.log(selectOption.value);
    }



})
</script>

<style  scoped>
.form-wrapper {
    padding: 20px;
    background: #111;
    border-radius: 8px;
    width: 400px;
}

.form-wrapper .form-input {
    display: flex;
    flex-direction: column;
    text-align: left;
    gap: 10px;
    margin-bottom: 10px;
}

.form-wrapper .form-input input,
.form-wrapper .form-input select {
    padding: 10px 10px;
    border-radius: 6px;
    border: 1px solid #888;
    background: transparent;

}

.form-wrapper .form-input select {
    background-color: #111;
}

.form-wrapper .form-input button {
    padding: 10px 15px;
    background: #888;
}
</style>