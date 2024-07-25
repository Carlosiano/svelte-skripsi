<script lang="ts">
  import { chevronUp } from "./assets/images";
  import { Header, Footer, Main } from "./lib";

  let scrollY: number;
</script>

<svelte:window bind:scrollY />

<Header {scrollY} />

<Main />

<Footer />

<!-- 
    - #BACK TO TOP
  -->

<a
  href="#top"
  class="back-top-btn"
  class:active={scrollY > 100}
  aria-label="back top top"
>
  <img src={chevronUp} alt="" class="ion-icon" aria-hidden="true" />
</a>