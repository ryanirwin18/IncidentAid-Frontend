<script>
  import DateForm from "./dateForm.svelte";
  import IncidentList from "./incidentList.svelte";
</script>

<div class="incidents">
  <h1>Incidents</h1>
  <DateForm />
  <IncidentList />
</div>

<style>
.incidents{
  grid-area: incidents;
  position: relative;
  background: #efecec;
  box-shadow: 2px 3px 3px #555252;
  margin: 10px 10px 10px 0;
  overflow: scroll;
}
.incidents h1{
  position: relative;
  display: inline-block;
  margin-left: 2%;
  margin-bottom: 10%;
  text-decoration: underline;
}
</style>
