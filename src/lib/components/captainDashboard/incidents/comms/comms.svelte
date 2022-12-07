<script>
  import Button from "$lib/shared/Button.svelte";
  export let address;
</script>

<div class="header">
  <p><b>10/18</b> {address}</p>
</div>
<h2>Comms</h2>
<div class="comms">
  <Button type='PAR'/>
  <Button type='VACATE'/>
  <Button type='UTIL-ON'/>
  <Button type="UTIL-OFF" />
  <Button type="ALL-CLEAR" />
</div>

<style>
  .header{
    text-align: center;
    display: inline-block;
    margin: 0% 24% 2% 23%;
  }
  .header p{
    text-align: center;
    margin: 0;
    color: #555252;
  }
  .header b{
    color: black;
  }
  h2{
    text-align: center;
    margin: 0;
    color: #933D00;
  }
  .comms{
    text-align: center;
    margin-right: 4%;
  }
  
</style>