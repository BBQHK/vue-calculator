<script setup>
  defineProps({
    input: String,
  })
</script>

<template>
  <div class="display">
    <p>{{ input }}</p>
  </div>
</template>

<style scoped>
.display {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  width: 300px;
  height: 80px;
  background-color: #f2f2f2;
  border-radius: 5px;
  padding: 10px;
  margin-bottom: 20px;
  font-size: 4rem;
  font-weight: bold;
}

.display p {
  margin: 0;
}
</style>