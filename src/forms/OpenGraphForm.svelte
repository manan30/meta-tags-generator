<style>
  h3 {
    text-align: center;
  }

  form {
    display: grid;
    gap: 1rem 1rem;
    grid-template-columns: 1fr 1fr;

    margin-bottom: 1rem;
  }
</style>

<h3>Open Graph Tags</h3>
<form>
  <Input labelFor="Title" required={true} />
  <Input labelFor="Type" required={true} />
  <Input labelFor="Image" required={true} />
  <Input labelFor="URL" required={true} />
</form>

<script>
  import Input from '../components/Input.svelte';
</script>
