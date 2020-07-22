<style>
  header {
    margin: 2.5rem 0;

    font-size: 2.5rem;
    line-height: 2.5rem;
    text-align: center;

    color: #25d09d;
  }

  main {
    display: flex;
    align-items: center;
    justify-content: center;

    height: calc(100% - 5rem);
    width: 100%;

    max-width: 15rem;
  }

  .form-container {
    display: flex;
    flex-direction: column;
    padding: 1rem;

    height: auto;
    max-height: calc(70% - 2rem);
    width: 35rem;

    border-radius: 0.5rem;
    box-shadow: 0 0 1.5rem #dddddd;

    overflow: auto;
  }

  .button-container {
    display: flex;
    align-items: center;
    justify-content: flex-end;
  }

  .button-container > button {
    padding: 0.5rem 1rem;

    border-radius: 0.25rem;
    border: none;

    color: #fdfff7;

    background-color: #25d09d;

    cursor: pointer;
  }

  .button-continue {
    margin-left: 1rem;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<header>
  <div>Meta Tags Generator</div>
</header>
<main>
  <div class="form-container">
    <div style="flex: 1 0 auto;">
      {#if currentFormState === 1}
        <SiteForm />
      {:else if currentFormState === 2}
        <OpenGraphForm />
      {:else if currentFormState === 3}
        <FacebookForm />
      {:else}
        <TwitterForm />
      {/if}
    </div>
    <div class="button-container">
      {#if currentFormState > 1}
        <button
          on:click={() => {
            handleFormProgress('dec');
          }}>
          Back
        </button>
      {/if}
      <button
        class="button-continue"
        on:click={() => {
          handleFormProgress('inc');
        }}>
        Continue
      </button>
    </div>
  </div>
</main>

<script>
  import SiteForm from '../forms/SiteForm.svelte';
  import OpenGraphForm from '../forms/OpenGraphForm.svelte';
  import FacebookForm from '../forms/FacebookForm.svelte';
  import TwitterForm from '../forms/TwitterForm.svelte';

  let currentFormState = 1;

  function handleFormProgress(type) {
    if (type === 'inc' && currentFormState < 4) {
      currentFormState += 1;
    }

    if (type === 'dec' && currentFormState > 1) {
      currentFormState -= 1;
    }
  }
</script>
