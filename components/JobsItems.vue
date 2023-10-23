<script setup>
const props = defineProps([
  "jobTitle",
  "contract",
  "teleworkable",
  "salaryMin",
]);
</script>

<template>
  <div class="job-items-box">
    <div class="job-items-list">
      <p class="job-title">{{ jobTitle }}</p>
      <div class="job-items">
        <p class="job-items-title">Type de poste</p>
        <p class="job-info">
          {{ contract ? contract.toUpperCase() : "Non précisé" }}
        </p>
      </div>
      <div class="job-items">
        <p class="job-items-title">Télétravail</p>
        <p class="job-info">
          {{ teleworkable ? "Ouvert" : "Fermé" }}
        </p>
      </div>
      <div class="job-items">
        <p class="job-items-title">Salaire min.</p>
        <p class="job-info">
          {{ salaryMin ? salaryMin + " €" : "Non précisé" }}
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.job-items-box {
  max-width: 1000px;
  height: 125px;
  display: block;
  background-color: #f7f7f7;
  transition: all;
  border: 3px solid #f7f7f7;
  border-radius: 15px;
  cursor: pointer;
}

.job-items-box:hover {
  border: 3px solid #4e8dec;
  transition-duration: 350ms;
}

.job-items-list {
  height: 125px;
  display: flex;
  align-items: center;
  justify-content: space-around;
  font-size: 18px;
}

.job-title {
  width: 260px;
  height: auto;
  font-weight: bold;
  text-align: left;
  color: #313131;
}

.job-items {
  width: 120px;
  display: flex;
  flex-direction: column;
}
.job-items-title {
  font-weight: bold;
}

.job-info {
  color: #525252;
}

@media (max-width: 680px) {
  .job-items-list {
    height: 300px;
    flex-direction: column;
  }

  .job-items-box {
    height: 300px;
  }

  .job-title {
    width: auto;
    text-align: center;
  }
}
</style>
