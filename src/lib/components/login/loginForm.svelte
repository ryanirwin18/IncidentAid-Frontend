<script>
  import { goto } from "$app/navigation";
  import Card from "../../shared/Card.svelte";
  import loginStyles from "./loginStyles.css";

  export let title;

  function login(){
    goto("/captainDashboard");
  }
</script>

<head>
  <title>Incident Aid Sign-in</title>
</head>


<body>
  <div class="logo">
    <img src="logoWtextclearsmaller.png" alt="incidentaid logo">
  </div>
<div class="login">
  <Card>
    <div class="card-body login-form">
      <h1 class="card-title">{title}</h1>
      <form on:submit|preventDefault={login}>
        <div class="txt-field">
          <input 
            type="email"
            class="form-control"
            id="emailInput"
            aria-describedby="emailHelp"
            placeholder="email"
          />
        </div>
        {#if title!="Forgot Password"}
        <div class="txt-field">
          <input
            type="password"
            class="form-control"
            id="passInput"
            placeholder="password"
          />
        </div>
        {/if}
        {#if title=="Sign Up"}
        <div class="txt-field">
          <input
          type="password"
          class="form-control"
          id="passConfirm"
          placeholder="confirm password"
        />
        </div>
        <div class="txt-field">
          <input
            type="test"
            class="form-control"
            id="idInput"
            placeholder="id"
          />
        </div>
        {/if}
        <button type="submit" class="Submit">Submit</button>
      {#if title=="Login"}
        <a href="/forgotPassword" class="pass">Forgot password</a>
      {:else}
        <a href="/" class="back">Back</a>
      {/if}
      </form>
      {#if title=="Login"}
        <div class="new_user">
          <a href="/signup">New User</a>
        </div>
      {/if}
    </div>
  </Card>
</div>
</body>