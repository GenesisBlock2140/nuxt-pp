<script setup>
const apiUrl = "https://app.staging.profilpublic.fr/api/jobs";
const queryParams = {
  query: {
    "fields[0]": "teleworkable",
    "fields[1]": "salaryMin",
    "fields[2]": "title",
    "fields[3]": "privateContract",
  },
};
const { data: posts } = await useFetch(apiUrl, queryParams);
</script>

<template>
  <div class="welcome">
    <h1>Profil Public</h1>
    <p>Trouver un job au service de l’intérêt général</p>
  </div>
  <JobsListBox>
    <JobsNumber :quantity="posts.data.length" />
    <JobsItems
      v-for="(post, index) in posts.data"
      :key="index"
      :job-title="post.title"
      :contract="post.privateContract"
      :teleworkable="post.teleworkable"
      :salary-min="post.salaryMin"
    />
  </JobsListBox>
</template>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

h1 {
  text-transform: uppercase;
  font-size: 32px;
  font-weight: bold;
}

.welcome {
  width: 350px;
  display: block;
  margin: 60px auto;
  color: #313131;
  font-family: sans-serif;
  text-align: center;
}
</style>
