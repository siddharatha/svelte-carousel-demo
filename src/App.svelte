<script>
  import { data } from "./data.js";
  import Carousel from "@siddharatha/svelte-interactive-carousel";
  import CarouselItem from "./CarouselItem.svelte";
  import Paginator from "./Paginator.svelte";

  export let visibleindex = 0;
  let carousel;
</script>

<Carousel items={data} let:blah bind:visibleindex>
  <CarouselItem {...blah} />
</Carousel>
<p>showing Index {visibleindex}</p>
<Paginator items={data} bind:visibleindex />
<button on:click={() => visibleindex--}>&lt-</button>
<button on:click={() => visibleindex++}>-&gt</button>
