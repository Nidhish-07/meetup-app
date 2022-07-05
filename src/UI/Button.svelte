<script>
  export let buttonType;
  export let caption;
  export let href;
  export let mode;
</script>

{#if href}
  <a {href}>{caption}</a>
{:else}
  <button class={mode} type={buttonType}>{caption}</button>
{/if}

<style>
  button,
  a {
    font: inherit;
    border: 1px solid #41f2c0;
    background: #41f2c0;
    padding: 0.5rem 1rem;
    color: white;
    border-radius: 5px;
    box-shadow: 1px 1px 3px rgba(0, 0, 0, 0.26);
    cursor: pointer;
    text-decoration: none;
  }

  button:focus {
    outline: none;
  }

  button:hover,
  button:active,
  a:hover,
  a:active {
    background: #93efd5;
    border-color: #80eecf;
    box-shadow: 1px 1px 8px rgba(77, 51, 51, 0.26);
  }

  button:disabled,
  button:disabled:hover,
  button:disabled:active {
    background: #ccc;
    border-color: #ccc;
    color: #959595;
    box-shadow: none;
    cursor: not-allowed;
  }

  .success {
    background: #75e6c6;
    border-color: #75e6c6;
  }

  .success:hover,
  .success:active {
    background: #75e6c6;
    border-color: #75e6c6;
  }

  .outline {
    background: transparent;
    color: #41f2c0;
    box-shadow: none;
  }

  .outline:hover,
  .outline:active {
    background: #b9f5e4;
    box-shadow: none;
  }

  .outline:disabled,
  .outline:disabled:hover,
  .outline:disabled:active {
    background: transparent;
    color: #ccc;
  }

  .outline.success {
    border-color: #75e6c6;
    color: #75e6c6;
  }

  .outline.success:hover,
  .outline.success:active {
    background: #c2ffd1;
  }
</style>
