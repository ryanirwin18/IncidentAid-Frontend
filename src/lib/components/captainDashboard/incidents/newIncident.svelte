<script>
  import Tabs from "$lib/shared/Tabs.svelte";
  import IncidentMembers from "./incidentMembers.svelte";
  import CommandHistory from "./commandHistory.svelte";
  import Comms from "./comms/comms.svelte";

  export let address;
  export let date;

  function handleClick(){
    this.classList.toggle("plus");
    this.nextElementSibling.classList.toggle("inactive");
  }

  function defaultForm(){
    activeItem = 'default';
  }

  let items=['Incident Members', 'Command History', 'Comms']
  let activeItem = 'default';

  const tabChange = (e) => {
    activeItem = e.detail;
  }
</script>

<div class="accordion">
  <div class="contentBx">
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div class="label plus" on:click={handleClick}><b>{date}</b>{address}</div>
    <div class="content inactive">
      {#if activeItem === 'default'}
        <p>Address: {address}</p>
        <Tabs {activeItem} {items} on:tabChange={tabChange}/>
        <label for="freeform">Notes:</label>
        <br>
        <textarea id="freeform"
                  name="freeform"
                  rows="4"
                  cols="50"></textarea>
      {/if}
      {#if activeItem != 'default'}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <img src="arrow.png" alt="back arrow" on:click={()=>defaultForm()}>
      {/if}
      {#if activeItem === 'Incident Members'}
        <IncidentMembers />
      {/if}
      {#if activeItem === 'Command History'}
        <CommandHistory />
      {/if}
      {#if activeItem === 'Comms'}
        <Comms {address}/>
      {/if}
    </div>
  </div>
</div>

<style>
  b{
    margin-right: 5%;
  }
  .accordion{
    width: 94%;
    margin-top: 3%;
  }
  .accordion .contentBx{
    position: relative;
    margin: 20px 0px 10px 5%;
    overflow-x: scroll;
  }
  .accordion .contentBx .label{
    position: relative;
    background-color: #FFDBA6;
    color: #444;
    cursor: pointer;
    padding: 18px;
  }
  .accordion .contentBx .label.plus::before{
    content: "+";
    position: absolute;
    top: 50%;
    right: 20px;
    transform: translateY(-50%);
    font-size: 1.6em;
  }
  .accordion .contentBx .content.inactive{
    position: relative;
    padding: 0;
    height: 0;
    overflow: hidden;
    overflow-y: auto;
  }
  .accordion .contentBx .label::before{
    content: "-";
    position: absolute;
    top: 50%;
    right: 21px;
    transform: translateY(-58%);
    font-size: 1.9em;
  }
  .accordion .contentBx .content{
    height: auto;
    background-color: #FFF5E5;
    padding: 10px;
  }
  .accordion .contentBx .content p{
    text-align: center;
  }
  img{
    width: 4%;
    margin-left: 2%;
    margin-top: 1%;
    cursor: pointer;
  }
  label{
    margin-left: 2%;
  }
  textarea{
    margin-left: 2%;
  }
  </style>