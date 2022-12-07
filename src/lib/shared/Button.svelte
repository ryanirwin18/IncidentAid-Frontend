<script>
  export let type; // could be type, class, etc...
  // export let commData;

  function handleClick(){
    this.classList.toggle("plus");
    this.nextElementSibling.classList.toggle("inactive");
  }


</script>

<div class="accordion">
  <div class="contentBx">
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div class="{type} label plus" on:click={handleClick}>{type}</div>
    <div class="content {type} inactive">
      <p><b>Request Sent:</b> 10/28/22 08:42:11 AM</p>
      <ul>
        <li><b>First Responder Alexander Carr-Locke</b> 10/28/22 08:43:12 AM</li>
        <li><b>First Responder Brett Gardner</b> 10/28/22 08:43:32 AM</li>
        <li><b>First Responder Derek Jeter</b> 10/28/22 08:43:52 AM</li>
      </ul>
    </div>
  </div>
</div>

<style>
.accordion{
  margin-top: 0%;
  text-align: center;
}
.accordion .contentBx{
  position: relative;
  margin: 20px 0px 10px 5%;
}
.accordion .contentBx .PAR{
  position: relative;
  background-color: #57C784;
  color: white;
  cursor: pointer;
  padding: 18px;
  margin: auto;
}
.accordion .contentBx .VACATE{
  position: relative;
  background-color: #D53D36;
  color: white;
  cursor: pointer;
  padding: 18px;
  margin: auto;
}
.accordion .contentBx .UTIL-ON{
  position: relative;
  background-color: #E0C35B;
  color: white;
  cursor: pointer;
  padding: 18px;
  margin: auto;
}
.accordion .contentBx .UTIL-OFF{
  position: relative;
  background-color: #A58D3A;
  color: white;
  cursor: pointer;
  padding: 18px;
  margin: auto;
}
.accordion .contentBx .ALL-CLEAR{
  position: relative;
  background-color: #4DBFC7;
  color: white;
  cursor: pointer;
  padding: 18px;
  margin: auto;
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
.accordion .contentBx .content {
  height: auto;
  padding: 10px;
  color: black;
  opacity: 88%;
  cursor: default;
  overflow-y: scroll;
  max-height: 240px;
}
.accordion .content p{
  font-size: 1.3em;
  margin: 0;
}
.accordion .content ul{
  padding-left: 1%;
}
.accordion .content li{
  list-style-type: none;
  text-align: left;
}
</style>