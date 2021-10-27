<script>
  import Button from "./Button.svelte";
  import Carousel from "./Carousel.svelte";
</script>

<style>
  main {
    font-family: sans-serif;
    text-align: center;
  }
  .slide-content {
    aspect-ratio: 1/1;
  }
</style>

<main>
	<h1>Hello CodeSandbox</h1>
	<h2>Start editing to see some magic happen!</h2>
	<Button />
  <br>
  <br>
  <Carousel perPage="1">
    <div class="slide-content">
      <img alt="1" src="https://static.wixstatic.com/media/038890_c00c8a1dbe0c4b22807c6ff749bb54fa~mv2.png/v1/fill/w_1349,h_611,al_c,q_90,usm_0.66_1.00_0.01/038890_c00c8a1dbe0c4b22807c6ff749bb54fa~mv2.webp" height="100%" />
    </div>
    <div class="slide-content">
      <img alt="1" src="https://static.wixstatic.com/media/038890_e6f6851b4d0f4934b17dcf28a29674a8~mv2.jpg/v1/fill/w_789,h_526,al_c,q_85,usm_0.66_1.00_0.01/038890_e6f6851b4d0f4934b17dcf28a29674a8~mv2.webp" height="100%" />
    </div>
    <div class="slide-content">
      <img alt="1" src="https://static.wixstatic.com/media/038890_458d7857e21747938575c3abe681bebc~mv2.jpg/v1/fill/w_789,h_526,al_c,q_85,usm_0.66_1.00_0.01/038890_458d7857e21747938575c3abe681bebc~mv2.webp" height="100%" />
    </div>
    <div class="slide-content">
      <img alt="1" src="https://static.wixstatic.com/media/038890_38ef73d9d3f548068d3a235f59a626d0~mv2.jpg/v1/fill/w_789,h_526,al_c,q_85,usm_0.66_1.00_0.01/038890_38ef73d9d3f548068d3a235f59a626d0~mv2.webp" height="100%" />
    </div>
  </Carousel>

</main>