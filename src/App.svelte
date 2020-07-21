<style>
  main {
    display: flex;
    align-items: center;
    justify-content: center;

    height: 100%;
    width: 100%;

    max-width: 15rem;
  }

  .main-container {
    display: flex;
    flex-direction: column;
    align-items: center;

    height: auto;
    width: 35rem;

    border-radius: 0.5rem;
    box-shadow: 0 0 1.5rem #dddddd;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <div class="main-container">
    <h1>Open Graph Tags</h1>
  </div>
</main>

<script>
  export let name;
</script>
