<script>
  export let incidents;
  export let onCall;
  export let personnel;

  let items = ["data", "newUser"]
  let current = "data";

  function newUserForm(){
    current = "newUser";
    console.log(current);
  }
  
  function dataForm(){
    current = "data";
  }

  function add(){
    current = "data";
  }
</script>

<div class="content-1">
  {#if current === "data"}
    <h4>Santa Clara Fire Station 2</h4>
    <p>Incidents this week: { incidents }</p>
    <p>Firefighters on call: { onCall }</p>
    <p>Total personnel: { personnel }</p>
    <div class="new_user">
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <p on:click={()=>newUserForm()}>Add User</p>
    </div>
  {:else if current === "newUser"}
    <div class="newUserContent">
      <h4>Santa Clara Fire Station 2</h4>
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <img src="arrow.png" alt="back arrow" on:click={()=>dataForm()}>
      <p>Add User to Station</p>
      <form on:submit|preventDefault={add}>
        <div class="input-field">
          <input
            type="text"
            class="form-control"
            id="companyID"
            placeholder="companyID" required
          />
        </div>
        <div class="input-field">
          <input
            type="text"
            class="form-control"
            id="currentStationKey"
            placeholder="currentStationKey" required
          />
        </div>
        <div class="input-field">
          <input
            type="text"
            class="form-control"
            id="email"
            placeholder="email" required
          />
        </div>
        <div class="input-field">
          <input
            type="text"
            class="form-control"
            id="id"
            placeholder="id" required
          />
        </div>
        <div class="input-field">
          <input
            type="text"
            class="form-control"
            id="name"
            placeholder="name" required
          />
        </div>
        <div class="input-field">
          <input
            type="text"
            class="form-control"
            id="rank"
            placeholder="rank" required
          />
        </div>
        <div class="input-field">
          <input
            type="text"
            class="form-control"
            id="status"
            placeholder="status" required
          />
        </div>
        <button type="submit">Create</button>
      </form>
    </div>
  {/if}
</div>
  
  
  <style>
  .content-1{
    grid-area: content-1;
    background: #efecec;
    box-shadow: 2px 3px 3px #555252;
    margin: 10px 0px 8px 10px;
    overflow: scroll;
  }
  .content-1 h4{
    background: #E77933;
    color: white;
    display: inline-block;
    width: 80%;
    text-align: center;
    margin: 3% 3% 0% 3%;
    margin-left: 8%;
    padding: 10px;
  }
  .content-1 p{
    margin-left: 6%;
    padding: 2%;
  }
  .new_user p{
    /* display: block; */
    margin: 0px;
    padding: 0px;
    text-align: center;
    color: #555252;
    cursor: pointer;
  }
  .new_user p:hover{
    text-decoration: underline;
  } 
  img{
    width: 5%;
    margin-left: 9%;
    margin-top: 10px;
    cursor: pointer;
  }
  .newUserContent p{
    display: inline;
    text-align: top;
    font-size: 1.5em;
    margin: 0;
    /* margin-left: 1%; */
  }
  .newUserContent .input-field{
    margin: 20px;
  }
  .newUserContent .input-field input{
    width: 70%;
    margin-left: 12%;
    margin-right: 15%;
    padding: 1%;
    background-color: #F5F5F5;
  }
  .newUserContent form button{
    /* position: relative; */
    margin-left: 84%;
    margin-bottom: 20px;
    background: #AF94FD;
    border: none;
    padding: 15px;
    border-radius: 5px;
    cursor: pointer;
  }
  .newUserContent .input-field input::placeholder{
    font-size: 1em;
  }
  </style>
  