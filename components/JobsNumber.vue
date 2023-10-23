<script setup>
const props = defineProps(["quantity"]);
</script>

<template>
  <div class="job-number-box">
    <p>{{ quantity }} offres</p>
  </div>
</template>

<style scoped>
.job-number-box {
  width: 135px;
  height: 40px;
  border-radius: 10px;
  background-color: #4e8dec;
  color: #fff;
  font-size: 24px;
  font-weight: bold;
  text-align: center;
}

p {
  height: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
