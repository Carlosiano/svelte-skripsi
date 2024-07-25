<script lang="ts">
  import { arrowForwardOutline, closeOutline, logoNav, menuOutline, personAddOutline } from "../assets/images";
  import { navLinks } from "../assets/js/data";

  let active = false;
  export let scrollY: number;
</script>

<header class="header" class:active={scrollY > 100} data-header>
  <div class="container">
    <a href={"#"} class="logo">
      <img src={logoNav} alt="UTC logo" />
    </a>

    <nav class="navbar" data-navbar class:active>
      <div class="wrapper">
        <a href={"#"} class="logo">
          <img src={logoNav} width="162" height="50" alt="UTC logo" />
        </a>

        <button
          class="nav-close-btn"
          aria-label="close menu"
          data-nav-toggler
          on:click={() => (active = !active)}
        >
          <img
            src={closeOutline}
            alt=""
            class="ion-icon"
            aria-hidden="true"
          />
        </button>
      </div>
      <ul class="navbar-list">
        {#each navLinks as item}
          <li class="navbar-item">
            <a
              href={`#${item.href}`}
              class="navbar-link"
              data-nav-link
              on:click={() => (active = !active)}>{item.title}</a
            >
          </li>
        {/each}
      </ul>
    </nav>

    <div class="header-actions">
      <a href={"#"} class="btn has-before">
        <img
          src={personAddOutline}
          alt=""
          class="ion-icon"
          aria-hidden="true"
        />
        <span class="span">Daftar</span>
      </a>
      <a href={"#"} class="btn-second has-before">
        <img
          src={arrowForwardOutline}
          alt=""
          class="ion-icon"
          aria-hidden="true"
        />
        <span class="span">Masuk</span>
      </a>

      <button
        class="header-action-btn"
        aria-label="open menu"
        data-nav-toggler
        on:click={() => (active = !active)}
      >
        <img
          src={menuOutline}
          alt=""
          class="ion-icon"
          aria-hidden="true"
        />
      </button>
    </div>

    <button
      class="overlay"
      data-nav-toggler
      data-overlay
      class:active
      on:click={() => (active = !active)}
    ></button>
  </div>
</header>
