<script>
  export let imageUrl;
  export let description;
  export let buttons;

  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();
  export let moveRight;

  function buttonclick(button) {
    button.type === "continue" ? moveRight() : console.log("Do Nothing");
  }
</script>

<style>
  .cardbox {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    border: 1px solid grey;
    width: 313px;
    height: 313px;
    border-radius: 2px;
    box-shadow: 0 2px 8px 0 rgba(0, 0, 0, 0.1);
    background-color: #ffffff;
    margin: 20px;
  }

  .description {
    text-align: center;
    flex-grow: 1;
    border-bottom: 1px solid grey;
  }
  .imgcontainer {
    background-color: rgba(61, 205, 88, 0.27);
    flex-grow: 2;
    width: 100%;
  }
  .imgcontainer img {
    width: 296px;
    height: 130px;
    opacity: 1;
  }
  .flexcenter {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .footbutton {
    color: #42b4e6;
    height: 50px;
    font-size: 16px;
    cursor: pointer;
  }
  .separator-bottom {
    border-bottom: 1px solid #e7e6e6;
  }
  .separator-top {
    border-top: 1px solid #e7e6e6;
  }
</style>

<div class="cardbox">
  <div class="imgcontainer flexcenter">
    <img src={imageUrl} alt={description} />
  </div>
  <div class="description flexcenter separator-bottom separator-top">
    {@html description}
  </div>
  <div class="buttons">
    {#if buttons}
      {#each buttons as button}
        <div
          class="footbutton flexcenter separator"
          on:click={() => buttonclick(button)}>
          {button.label}
        </div>
      {/each}
    {/if}
  </div>
</div>
