<script>
  import Button from "./Button.svelte";
  import Carousel from "./Carousel.svelte";
  let isShown = false;
  let images = [
    "https://static.wixstatic.com/media/038890_07ea1f5cc2b94873b3408831cf195a4c~mv2.jpg/v1/fill/w_789,h_526,al_c,q_85,usm_0.66_1.00_0.01/038890_07ea1f5cc2b94873b3408831cf195a4c~mv2.webp",
    "https://static.wixstatic.com/media/038890_e6f6851b4d0f4934b17dcf28a29674a8~mv2.jpg/v1/fill/w_789,h_526,al_c,q_85,usm_0.66_1.00_0.01/038890_e6f6851b4d0f4934b17dcf28a29674a8~mv2.webp",
    "https://static.wixstatic.com/media/038890_458d7857e21747938575c3abe681bebc~mv2.jpg/v1/fill/w_789,h_526,al_c,q_85,usm_0.66_1.00_0.01/038890_458d7857e21747938575c3abe681bebc~mv2.webp",
    "https://static.wixstatic.com/media/038890_38ef73d9d3f548068d3a235f59a626d0~mv2.jpg/v1/fill/w_789,h_526,al_c,q_85,usm_0.66_1.00_0.01/038890_38ef73d9d3f548068d3a235f59a626d0~mv2.webp"
  ];
  let hue = 4698;
  let carousel = Array(4),
    n = 0,
    perPage = 1;
  $: if (carousel[perPage - 1]) {
    carousel[perPage - 1].go(n);
  }
</script>

<main>
	<h1>Hello CodeSandbox</h1>
	<h2>Start editing to see some magic happen!</h2>
	<Button />
  <br>
  <br>
  {#if isShown}
  @Page: 
  {#each [1,2,3,4] as i}
    <input bind:group={perPage} type="radio" value={i} /> {i} 
  {/each}
  <br/>
  <input type="range" step="1" min="0" max="3" bind:value={n} />
  {#each [1,2,3,4] as i}
  <div 
    style="height:{i===perPage?"50vh":"0"}; visibility:{i===perPage?"visible":"hidden"}"
  >
  <Carousel perPage={i} bind:this={carousel[i - 1]}>
    {#each images as image, i}
    <div class="slide-content">
      <img alt={i} src={image}/>
    </div>
    {/each}
  </Carousel>
  </div>
  {/each}
  {:else}
    <div 
      on:click={() => isShown = true}
      on:mousemove={e => hue = e.clientX * e.clientY}
      style="background: hsl({hue / 500}, 100%, 50%); height:50vh" 
    />
  {/if}
</main>

<style>
  main {
    font-family: sans-serif;
    text-align: center;
  }
  img {
    height: 50vh;
  }
</style>