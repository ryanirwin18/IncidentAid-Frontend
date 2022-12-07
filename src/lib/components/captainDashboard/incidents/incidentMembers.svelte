<script>

  let crews = [
    { station: 'station-004-companyA', members: ['judge', 'rizzo', 'stanton'], id: 1 }
  ];
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<h2>Incident Members</h2>
<div class="membersCard">
  {#each crews as crew (crews.id)}
    <h1>{crew.station}</h1>
    <ul>
      <li>Captain Steve</li>
      <li>First Responder Kyle</li>
      <li>First Responder Bill</li>
      <li>First Responder George</li>
    </ul>
  {/each}
 
</div>

<style>
  h2{
    font-size: 1.3em;
    display: inline-block;
    margin: 2px;
    margin-left: 25%;
    margin-right: 25%;
    text-align: center;
  }
  .membersCard{
    background: #FFE4BD;
    position: relative;
    width: 90%;
    margin: 4% 5% 4% 5%;
    border-radius: 10px;
    text-align: center;
    overflow-y: scroll;
    max-height: 260px;
  }
  .membersCard h1{
    margin: 3% 0 0 4%;
    font-size: 1.3em;
    text-align: left
  }
  .membersCard ul{
    text-align: left;
    display: inline-block;
  }
  .membersCard li{
    list-style-type: none;
    text-align: left;
    font-size: 0.9em;
  }
</style>