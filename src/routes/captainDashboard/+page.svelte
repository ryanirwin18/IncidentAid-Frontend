<script>
  import { goto } from "$app/navigation";
  import Content_1 from "$lib/components/captainDashboard/content_1.svelte";
  import Incidents from "$lib/components/captainDashboard/incidents/incidents.svelte";
  import Content_2 from "$lib/components/captainDashboard/content_2.svelte";

  function logout(){
    goto("/");
  }
</script>

<body>
  <img src="logoWtextclearsmaller.png" alt="Incident Aid logo">
  <h1 class="header">Captain Dashboard</h1>
  <a class="logout" on:click|preventDefault={logout} href="/">Sign Out</a>
  <div class="container">
    <Content_1 incidents={10} onCall={15} personnel={28}/>
    <Incidents />
    <Content_2 />
  </div>
</body>


<style>
img{
  width: 15%;
  margin-left: 1%;
  margin-top: 5px;
}
.header{
  position: relative;
  display: inline-block;
  margin: 0 0 0 0;
  top: 50%;
  left: 31%;
  transform: translate(-40%, 60%);
  color: #E77933;
}
.logout{
  position: absolute;
  top: 0px;
  right: 0px;
  margin-top: 10px;
  margin-right: 10px;
  text-decoration: none;
  color: grey;
}
.logout:hover{
  opacity: .8;
}
body{
  margin: 0;
  padding: 0;
  font-family: 'Arial';
  background: #313131;
  letter-spacing: 2px;
}
.container{
  background: #D9D9D9;
  position: relative;
  left: 50%;
  top: 50%;
  transform: translate(-50%, 5%);
  display: grid;
  grid-template-columns: 1.4fr 2fr;
  grid-template-rows: 1fr 1fr;
  grid-template-areas:
    "content-1 incidents"
    "content-2 incidents";
  width: 95%;
  height: 88vh;
  grid-gap: 0.5em;
  border-radius: 10px;
  overflow: scroll;
}

</style>
