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
  data-back-top-btn
>
  <img src={chevronUp} alt="" class="ion-icon" aria-hidden="true" />
</a>

<style>
.back-top-btn .ion-icon{
  filter: invert(96%) sepia(86%) saturate(2%) hue-rotate(160deg) brightness(110%) contrast(100%);
}
</style>
