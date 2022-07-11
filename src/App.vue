<template>
  <div class="container">
    <header>
      <h1>LinkShortner</h1>
    </header>

    <main>
      <LinkForm />
    </main>
  </div>
</template>

<script>
  import LinkForm from './components/LinkForm.vue';
  export default {
    components: {
      LinkForm
    }
  }
</script>

<style>

</style>
