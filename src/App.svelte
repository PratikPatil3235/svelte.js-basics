<script>
  import ReactiveDeclaration from "./ReactiveDeclaration.svelte";
  import Counter from "./Counter.svelte";
  import FormHandler from "./FormHandler.svelte";
</script>

<main>
  <h1
    style="text-align: center; color: aqua ; font-weight: bolder; font-size: 65px;"
  >
    My App
  </h1>

  <!-- Row container for Counter + ReactiveDeclaration -->
  <div class="row">
    <Counter />
    <ReactiveDeclaration />
  </div>

  <!-- FormHandler below the row -->
  <div class="form-container">
    <FormHandler />
  </div>
</main>

<style>
  main {
    padding: 2rem;
    font-family: 'Segoe UI', sans-serif;
  }

  .row {
    display: flex;
    gap: 2rem;
    justify-content: space-around;
    align-items: center;
    margin-bottom: 2rem;
  }

  .form-container {
    max-width: 900px;
    margin: 0 auto;
  }

  @media (max-width: 768px) {
    .row {
      flex-direction: column;
      align-items: center;
    }
  }
</style>
