<script>
  import { contentinfo } from "./content.js";
  import Carousel from "./Carousel.svelte";
  import CarouselItem from "./CarouselItem.svelte";
  import Paginator from "./Paginator.svelte";

  export let visibleindex = 0;
</script>

<Carousel items={contentinfo} let:blah bind:visibleindex>
  <CarouselItem {...blah} />
</Carousel>
<p>showing Index {visibleindex}</p>
<Paginator items={contentinfo} bind:visibleindex />
