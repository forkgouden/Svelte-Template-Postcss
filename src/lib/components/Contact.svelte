<script>
  export let user;
  import Paypal from "./Paypal.svelte";
  import Capitular from "./Capitular.svelte";
</script>

<style>
  #contacto {
    display: flex;
    justify-content: center;
    width: 100%;
  }

  li {
    margin: 1rem 0;
  }

  .contact-info {
    width: 50%;
    padding: 0 1rem;
  }

  .contact-social {
    display: flex;
    justify-content: space-evenly;
    width: 100%;
    flex-direction: row;

    & li {
      width: 100%;
      display: flex;
      justify-content: center;
    }

    & .button {
      width: 95%;
      margin: 0;
    }

    & .button:hover {
      border: 0;
    }

    @media (--large) {
      width: 50%;
    }
  }

  .awesome {
    display: flex;
    align-items: center;
  }

  .button {
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--black);
    background-color: var(--primaryLight);
    font-size: 95%;
    font-weight: 400;
    text-align: center;
    margin-top: 0.5rem;
    padding: 0.5rem;
    border-radius: 1rem;
    transition: all 0.2s ease-in-out;

    &:hover {
      background-color: var(--primaryLight);
      border: 1px solid var(--black);
      box-shadow: inset 0 0 calc(var(--unit) / 6) 0 var(--primary);
    }
  }
</style>

<article class="gray" id="contacto">
  <Capitular>Contacto</Capitular>
  <ul class="contact-info">
    <li class="awesome">
      <i class="fas fa-user" />
      <span>{user.nombre}</span>
    </li>
    <li>
      <a class="awesome" href="tel:{user.telefono}" title="Llámame">
        <i class="fas fa-phone" />
        <span>{user.telefono}</span>
      </a>
    </li>
    <li>
      <a class="awesome" href="mailto:{user.mail}" title="Mándame un mail">
        <i class="fas fa-envelope" />
        <span>{user.mail}</span>
      </a>
    </li>
  </ul>
  <ul class="contact-social">
    <li>
      <a class="button awesome" href={user.facebook} target="_blank">
        <div class="wrapper">
          <i class="fab fa-facebook" aria-hidden="true" />
          <span class="contact-text">facebook</span>
        </div>
      </a>
    </li>
    <li>
      <a class="button awesome" href={user.instagram} target="_blank">
        <div class="wrapper">
          <i class="fab fa-instagram" aria-hidden="true" />
          <span class="contact-text">instagram</span>
        </div>
      </a>
    </li>
    <li>
      <a
        class="button awesome"
        href="https://wa.me/{user.telefono}?text=Hola%21%20Quiero%20saber%20m%C3%A1s%20sobre%20el%20Evento%20de%20Abril%20con%20Sergio%20Fernandez"
      >
        <div class="wrapper">
          <i class="fab fa-whatsapp" aria-hidden="true" />
          <span class="contact-text">whatsapp</span>
        </div>
      </a>
    </li>
  </ul>
  <Paypal {user} />
</article>
