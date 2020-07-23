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

    transition: all 0.5s ease-out;
  }

  input {
    width: 100%;
    margin: 0;

    border: none;
    border-bottom: 0px solid #25d09d;

    background-color: transparent;

    transition: all 0.4s ease-out;
  }

  input:focus {
    outline: none;
    border-bottom: 1px solid #25d09d;
  }

  input:focus + label {
    color: #1c3738;
    transform: translate3d(0, 0, 0);
  }

  /* Do not transform label when input has text */
</style>

<div>
  <input
    id={labelFor.toLowerCase()}
    type={inputType}
    value={inputValue}
    on:input={handleInput}
    on:focus={() => handleFocus(true)}
    on:blur={() => handleFocus(false)}
    {required} />
  <label for={labelFor.toLowerCase()}>{labelFor}</label>
</div>

<script>
  export let labelFor = '';
  export let required = false;
  export let inputType = 'text';
  export let inputCallback = () => {};

  let inputValue = '';
  let isFocused = false;

  const handleInput = (e) => {
    inputValue = e.target.value;
  };

  const handleFocus = (hasFocus = false) => {
    isFocused = hasFocus;
  };

  $: if (!isFocused) inputCallback(labelFor.toLowerCase(), inputValue);
</script>
