<template>
    <input min="0" type="number" @input="changeAmount($event.target.value)" placeholder="Введите сумму"><br>
    <button @click="convert()">Конвертировать</button>
</template>
  
  
<script>
export default {
    props: {
        changeAmount: {
            type: Function,
            required: true
        },
        convert: {
            type: Function,
            required: true
        }
    }
}
</script>
  
<style scoped>
  input {
    border-radius: 5px;
    border: 4px solid #1a032d;
    background-color: #fafafa;
    color: #333;
    outline: none;
    width: 500px;
    position: relative;
    top: -50px;
    font-size: 1.2em;
    padding: 15px 20px;
  }

  button {
    position: relative;
    top: -20px;
    padding: 15px 20px;
    color: #fff;
    text-transform: uppercase;
    cursor: pointer;
    background: #1a032d;
    border: 0;
    border-radius: 3px;
  }
</style>
  