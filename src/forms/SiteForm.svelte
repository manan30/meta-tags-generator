<style>
  h3 {
    /* text-align: center; */
    margin-bottom: 0.5rem;
  }

  .form-input-container {
    display: grid;
    gap: 1rem 1rem;
    grid-template-columns: 1fr;

    margin-bottom: 1rem;

    font-size: 0.8rem;
  }
</style>

<h3>Site Tags</h3>
<form>
  <div class="form-input-container">
    <Input labelFor="Title" required={true} inputCallback={handleInputChange} />
    <Input labelFor="Description" inputElement="textarea" />
    <!-- <Input
      labelFor="Description"
      required={true}
      inputCallback={handleInputChange} /> -->
  </div>
</form>

<script>
  import Input from '../components/Input.svelte';

  const siteFormState = {};

  const handleInputChange = (key, value) => {
    siteFormState[key] = value;
  };
</script>
