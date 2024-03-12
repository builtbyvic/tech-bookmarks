<script>
  export let searchTerm;
  export let onInput;
</script>

<div class="input-wrapper">
  <label for="search">🔎</label>
  <input type="search" id="search" placeholder="Coming Soon..." bind:value={searchTerm} on:input={onInput}/>
</div>

<style>
   .input-wrapper {
    /* border: 2px solid red; */
    color: #fff;
    align-items: center;
    display: flex;
    font-size: var(--xxl);
    inline-size: 540px;
    margin-block: var(--large);
  }
  [type="search"] {
    background-color: transparent;
    border: var(--border-glass);
    border-radius: var(--large);
    padding: var(--large);
    inline-size: 100%;
  }
  [type="search"]:focus {
    outline: 1px solid rgba(255 255 255 / 0.2);
  }
  @media (max-width: 640px) {
     .input-wrapper {
       inline-size: 100%;
    }
  }
</style>