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

<h3>Twitter Card Tags</h3>
<form>
  <div class="form-input-container">
    <Input labelFor="Card" />
    <Input labelFor="Site" />
    <Input labelFor="Site:ID" />
    <Input labelFor="Creator" />
    <Input labelFor="Creator:ID" />
    <Input labelFor="Description" />
    <Input labelFor="Title" />
    <Input labelFor="Image" />
    <Input labelFor="Image:Alt" />
    <Input labelFor="Player" />
    <Input labelFor="Player:Width" />
    <Input labelFor="Player:Height" />
    <Input labelFor="Player:Stream" />
    <Input labelFor="App:Name:iPhone" />
    <Input labelFor="App:ID:iPhone" />
    <Input labelFor="App:URL:iPhone" />
    <Input labelFor="App:Name:iPad" />
    <Input labelFor="App:ID:iPad" />
    <Input labelFor="App:URL:iPad" />
    <Input labelFor="App:Name:GooglePlay" />
    <Input labelFor="App:ID:GooglePlay" />
    <Input labelFor="App:URL:GooglePlay" />
  </div>
</form>

<script>
  import Input from '../components/Input.svelte';
</script>
