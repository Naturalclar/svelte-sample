<script>
  import { push } from "svelte-spa-router";
  import NoteEditor from "../components/NoteEditor.svelte";
  import SaveButton from "../components/SaveButton.svelte";
  import { loadNotes, overwriteNote } from "../lib/storage";

  export let params = {};
  const note = loadNotes()[params.id];
  let title = note.title;
  let content = note.content;

  const onSave = () => {
    overwriteNote(params.id, { title, content });
    push("/");
  };
</script>

<style>
  .add {
    display: flex;
    flex-direction: column;
    height: 100%;
  }

  .button-container {
    padding: 1em 0;
    text-align: right;
  }
</style>

<section class="add">
  <NoteEditor bind:title bind:content />
  <div class="button-container">
    <SaveButton {onSave} disabled={!title || !content} />

  </div>
</section>
