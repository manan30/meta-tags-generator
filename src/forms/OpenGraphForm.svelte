<style>
  h3 {
    text-align: center;
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

<h3>Open Graph Tags</h3>
<div style="margin: 0 1rem;">Required Tags *</div>
<form>
  <div class="form-input-container">
    <Input labelFor="Title" required={true} />
    <Input labelFor="Type" required={true} />
    <Input labelFor="Image" required={true} />
    <Input labelFor="URL" required={true} />
  </div>
  <hr />
  <div style="margin: 0 1rem;">Optional Tags</div>
  <div class="form-input-container">
    <Input labelFor="Audio" />
    <Input labelFor="Description" />
    <Input labelFor="Determiner" />
    <Input labelFor="Locale" />
    <Input labelFor="Locale Alternate" />
    <Input labelFor="Site Name" />
    <Input labelFor="Video" />
    <Input labelFor="Video" />
    <Input labelFor="Video" />
    <Input labelFor="Video" />
    <Input labelFor="Video" />
    <Input labelFor="Video" />
  </div>
</form>

<script>
  import Input from '../components/Input.svelte';
</script>
