<template>
  <div class="job-list-box">
    <div class="job-list">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.job-list-box {
  max-width: 1000px;
  display: block;
  margin: 10px auto;
  padding: 5px;
}

.job-list {
  display: flex;
  flex-direction: column;
  gap: 10px;
}
</style>
