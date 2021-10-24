<script>
</script>

<style>
  h3 {
    text-align: center;
  }

  hr {
    width: var(--unit);
    color: var(--primary);
    margin: 0 calc(var(--unit) / 6);
  }

  .caps {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: row;
  }
</style>

<div class="caps">
  <hr />
  <h3>
    <slot />
  </h3>
  <hr />
</div>
