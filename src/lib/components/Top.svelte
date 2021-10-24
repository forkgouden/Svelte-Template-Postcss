<script>
  export let user;
  let n = user.telefono;
  let texto = encodeURIComponent("hola esto es un mensaje para ti especial :3");
  let num = n.split(" ").join("");
</script>

<style>
  .top {
    position: sticky;
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100%;
    top: 0;
    padding: 1rem;
    background-color: var(--primary);

    & p {
      display: flex;
      width: max-content;
    }

    @media (--medium) {
      padding: 0.25rem 0.25rem 0.25rem calc(var(--unit) / 4);
    }
  }
</style>

<div class="top">
  <p>¡QUIERO SABER MÁS!</p>
  <a class="awesome" href="https://wa.me/${num}?text=${texto}">
    <div class="wrapper">
      <i class="fab fa-whatsapp" aria-hidden="true" />
      <span class="contact-text">{user.telefono}</span>
    </div>
  </a>
</div>
