<script>
    let num1 = 0;
    let num2 = 0;
    export let result = num1 + num2;
    export let showModal = false;
    export let isPromo = false;
  
    // Watch for changes in num1 and num2 to update the result
    $: result = num1 + num2;
  </script>
  
  {#if showModal}
    <div class="show" class:promo={isPromo}  on:click>
      <div class="backdrop"  >
      <kbd class="kbd kbd-lg">The answer is: {result}</kbd>
     </div>
  </div>
  
  {/if}
  <style>
    
    .kbd-lg{
          background-color: #b5ffee;
          color: black;
          border: 2px solid black;
          font-weight: bold;
      }
    .show{
      background-color: rgba(128, 128, 128, 0.5);
      position: fixed;
      height: 100%;
      width: 100%;
    }
    .backdrop{
      display: flex;
      justify-content: center;
      padding-top: 300px;
    }
  </style>