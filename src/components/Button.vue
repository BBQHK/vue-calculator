<script setup>
    defineProps({
        id: String,
        value: String,
        handleClick: Function,
    })
</script>

<template>
    <button :id="id" :value="value" @click="handleClick">{{ value }}</button>
</template>

<style scoped>
button {
  background-color: #a1a1a1;
  color:#fff;
  border: none;
  border-radius: 5px;
  font-size: 2rem;
  font-weight: bold;
  cursor: pointer;
  padding: 10px;
  transition: all 0.2s;
}

#function {
  background-color: #696969;
}

#operator {
  background-color: #ffa869;
}

#equal {
  background-color: #ffa869;
  grid-column-start: 3;
  grid-column-end: 5;
}

button:hover {
  background-color: #d9d9d9;
}

button:active {
  transform: scale(0.95);
}
</style>