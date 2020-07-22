<style>
  main {
    display: flex;
    align-items: center;
    justify-content: center;

    height: 100%;
    width: 100%;

    max-width: 15rem;
  }

  .form-container {
    display: flex;
    flex-direction: column;
    padding: 1rem;

    height: auto;
    width: 35rem;

    border-radius: 0.5rem;
    box-shadow: 0 0 1.5rem #dddddd;
  }

  .button-container {
    display: flex;
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
    margin-left: auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <div class="form-container">
    {#if currentFormState === 1}
      <OpenGraphForm />
    {:else if currentFormState === 2}
      <FacebookForm />
    {:else}
      <TwitterForm />
    {/if}
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
  import OpenGraphForm from './forms/OpenGraphForm.svelte';
  import FacebookForm from './forms/FacebookForm.svelte';
  import TwitterForm from './forms/TwitterForm.svelte';

  let currentFormState = 1;

  $: console.log(currentFormState);

  function handleFormProgress(type) {
    if (type === 'inc' && currentFormState < 3) {
      currentFormState += 1;
    }

    if (type === 'dec' && currentFormState > 1) {
      currentFormState -= 1;
    }
  }
</script>
