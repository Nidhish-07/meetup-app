<script>
  export let inputType;
  export let id;
  export let labelName;
  export let rows;
  export let value;
</script>

<div class="form-control">
  <label for={id}>{labelName}</label>
  {#if inputType === "textarea"}
    <textarea {rows} id="title" {value} on:input />
  {:else}
    <input type="text" name="" id="title" {value} on:input />
  {/if}
</div>

<style>
  input,
  textarea {
    display: block;
    width: 100%;
    border: none;
    border-bottom: 2px solid #ccc;
    border-radius: 3px 3px 0 0;
    background: white;
    padding: 0.15rem 0.25rem;
    transition: border-color 0.1s ease-out;
  }

  input:focus,
  textarea:focus {
    border-color: #41f2c0;
    outline: none;
  }

  label {
    display: block;
    margin-bottom: 0.5rem;
    width: 100%;
  }
  .form-control {
    padding: 0.5rem 0;
    width: 100%;
    margin: 0.25rem 0;
  }
</style>
