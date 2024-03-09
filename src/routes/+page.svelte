<script>
    import Modal from './Components/Modal.svelte';
    
    let showModal = false;
    export let num1 = 0;
    export let num2 = 0; 
    let result = 0; 
  
    
    const calculateResult = () => {
      result = num1 + num2; 
      toggleModal();
    }
  
    const toggleModal = () => {
      showModal = !showModal;
    }
  </script>
  <Modal {showModal} {result} on:click={toggleModal}/>
  <main>
    <div class="form">
        <h3>Enter A Number To perform addition</h3>
        <div class="details">
            <span class="label-text">First Number:</span>
            <input type="number" class="input input-bordered input-success w-full max-w-xs" bind:value={num1}/>
        </div>
        <div class="details">
            <span class="label-text">Second Number:</span>
            <input type="number" class="input input-bordered input-success w-full max-w-xs" bind:value={num2}/>
        </div>
        <button class="btn btn-success" on:click={calculateResult}>CALCULATE</button>
    </div>
    
  </main>
  
  <style>
    .form{
        padding: 25px;
        border: 1px solid white;
        display: flex;
        flex-direction: column;
        align-items: center; 
    }
    span{
        padding: 10px;
    }
    h3{
        font-weight: bold;
        color: black;
        border-radius: 20px;
        text-transform: uppercase;
        padding: 20px;
        background: #d3fff4;
        margin-bottom: 10px;
    }
    main {
        padding: 180px;
        display: flex;
        flex-direction: column;
        align-items: center; 
    }

    .details {
        margin-bottom: 10px; /* Adjust margin between detail sections */
        display: flex;
        flex-direction: column;
        align-items: left; 
    }
    button{
        font-weight: bold;
        margin: 10px;
    }
</style>
