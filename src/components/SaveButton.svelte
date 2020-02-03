<script>
  export let onSave;
  export let disabled = false;
</script>

<style>
  .save {
    background-color: rgb(62, 68, 163);
    border: none;
    border-radius: 3px;
    color: white;
    font-size: 1em;
    padding: 0.5em 1em;
    cursor: pointer;
  }

  .save:disabled {
    opacity: 0.3;
    cursor: auto;
  }
</style>

<button class="save" on:click={onSave} {disabled}>Save</button>
