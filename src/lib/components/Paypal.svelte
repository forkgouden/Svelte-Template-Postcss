<script>
  export let user;
</script>

<style>
  .button {
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--black);
    background-color: var(--primaryLight);
    font-weight: 400;
    text-align: center;
    margin-top: 0.5rem;
    border-radius: 1rem;
    transition: all 0.2s ease-in-out;
    font-size: 95%;
    padding: 0.5rem;

    &:hover {
      background-color: var(--primaryLight);
      border: 1px solid var(--black);
      box-shadow: inset 0 0 calc(var(--unit) / 6) 0 var(--primary);
    }
  }

  .button--paypal {
    background-color: var(--primary);
    width: 100%;
    margin: calc(var(--unit) / 4) 0;
    text-transform: uppercase;

    @media (--large) {
      width: 50%;
      justify-self: center;
    }
  }
</style>

{#if user.id}
  <a
    class="button button--paypal"
    href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&amp;hosted_button_id={user.id}"
  >
    comprar entrada
  </a>
{:else}
  <a class="button button--paypal" href={user.paypal}>comprar entrada</a>
{/if}
