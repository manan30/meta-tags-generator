<style>
  div {
    display: flex;
    flex-direction: column-reverse;

    padding: 0.5rem;

    border-radius: 0.5rem;
  }

  label {
    width: calc(100% - 0.4rem);
    padding: 0.4rem;
    margin-bottom: 0.2rem;

    transform: translate3d(0.5rem, 1.8rem, 0);
    opacity: 0;

    transition: all 0.5s ease-out;
  }

  input,
  textarea {
    width: 100%;
    margin: 0;

    border: none;
    border-bottom: 1px solid #ccc;

    background-color: transparent;

    transition: all 0.4s ease-out;
  }

  input:focus,
  textarea:focus {
    outline: none;
    border-bottom: 1px solid #25d09d;
  }

  input:focus + label,
  textarea:focus + label {
    color: #25d09d;
    transform: translate3d(0, 0, 0);
    opacity: 1;
  }

  /* Do not transform label when input has text */
</style>

<div>
  {#if inputElement === 'input'}
    <input
      id={labelFor.toLowerCase()}
      placeholder={!isFocused ? labelFor : ''}
      type={inputType}
      value={inputValue}
      on:input={handleInput}
      on:focus={handleFocus}
      on:blur={handleFocus}
      {required} />
  {:else}
    <textarea
      id={labelFor.toLowerCase()}
      placeholder={labelFor}
      rows={5}
      cols={10}
      on:focus={handleFocus}
      on:blur={handleFocus}
      bind:value />
  {/if}
  <label for={labelFor.toLowerCase()}>{labelFor}</label>
</div>

<script>
  export let labelFor = '';
  export let required = false;
  export let inputType = 'text';
  export let inputElement = 'input';
  export let inputCallback = () => {};

  let inputValue = '';
  let value = '';
  let isFocused = false;

  const handleInput = (e) => {
    inputValue = e.target.value;
  };

  const handleFocus = () => {
    isFocused = !isFocused;
  };

  $: if (!isFocused) inputCallback(labelFor.toLowerCase(), inputValue);
</script>
