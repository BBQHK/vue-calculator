<script setup>
import { ref } from 'vue';
import Display from './components/Display.vue';
import Button from './components/Button.vue';

const input = ref('');
const prev_input = ref('');

const handleClick = (e) => {
  const value = e.target.value;
  switch (value) {
    case '=': {
      const result = eval(prev_input.value + input.value);
      input.value = result;
      prev_input.value = '';
      break;
    }
    case 'C': {
      input.value = '';
      prev_input.value = '';
      break;
    }
    case '+/-': {
      input.value = input.value * -1;
      break;
    }
    case '%': {
      input.value = input.value / 100;
      break;
    }
    case '+': {
      prev_input.value = input.value + '+';
      input.value = '';
      break;
    }
    case '-': {
      prev_input.value = input.value + '-';
      input.value = '';
      break;
    }
    case '*': {
      prev_input.value = input.value + '*';
      input.value = '';
      break;
    }
    case '/': {
      prev_input.value = input.value + '/';
      input.value = '';
      break;
    }
    default: {
      input.value = input.value + value;
      break;
    }
  }
}

</script>

<template>
    <div class="calculator">
      <Display :input="input" />
      
      <div class="buttons">
        <Button id="function" value="C" :handleClick="handleClick" />
        <Button id="function" value="+/-" :handleClick="handleClick" />
        <Button id="function" value="%" :handleClick="handleClick" />
        <Button id="operator" value="/" :handleClick="handleClick" />
        
        <Button value="7" :handleClick="handleClick" />
        <Button value="8" :handleClick="handleClick" />
        <Button value="9" :handleClick="handleClick" />
        <Button id="operator" value="*" :handleClick="handleClick" />
        
        <Button value="4" :handleClick="handleClick" />
        <Button value="5" :handleClick="handleClick" />
        <Button value="6" :handleClick="handleClick" />
        <Button id="operator" value="-" :handleClick="handleClick" />
        
        <Button value="1" :handleClick="handleClick" />
        <Button value="2" :handleClick="handleClick" />
        <Button value="3" :handleClick="handleClick" />
        <Button id="operator" value="+" :handleClick="handleClick" />
        
        <Button value="0" :handleClick="handleClick" />
        <Button value="." :handleClick="handleClick" />
        <Button id="equal" value="=" :handleClick="handleClick" />
      </div>
    </div>
</template>

<style scoped>
.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-top: 50px;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  padding: 10px;
}
</style>
