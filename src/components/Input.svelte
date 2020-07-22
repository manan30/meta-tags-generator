<style>
  div {
    display: flex;
    flex-direction: column-reverse;

    padding: 0.5rem;

    border-radius: 0.5rem;
  }

  label {
    width: calc(100% - 0.4rem);
    margin-bottom: 0.2rem;
    transform: translate3d(0.4rem, 1.8rem, 0);

    transition: all 1s cubic-bezier(0.075, 0.82, 0.165, 1);
  }

  input {
    width: 100%;
    margin: 0;

    border: none;
    border-bottom: 1px solid #ccc;

    background-color: transparent;
  }

  input:focus {
    outline: none;
  }

  input:focus + label {
    transform: translate3d(0, 0, 0);
  }
</style>

<div>
  <input id={labelFor.toLowerCase()} />
  <label for={labelFor.toLowerCase()}>{labelFor}</label>
</div>

<script>
  export let labelFor;
</script>
