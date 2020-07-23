<style>
  h3 {
    /* text-align: center; */
    margin-bottom: 0.5rem;
  }

  .form-input-container {
    display: grid;
    gap: 1rem 1rem;
    grid-template-columns: 1fr 1fr;

    margin-bottom: 1rem;

    font-size: 0.8rem;
  }

  hr {
    margin: 0.5rem 1rem 1rem 1rem;
  }
</style>

<h3>Site Tags</h3>
<form>
  <div class="form-input-container">
    <Input labelFor="Title" required={true} />
    <Input labelFor="Type" required={true} />
    <Input labelFor="Image" required={true} />
    <Input labelFor="URL" required={true} />
  </div>
</form>

<script>
  import Input from '../components/Input.svelte';

  const siteFormState = {
    title: '',
  };
</script>
