<script>
  import { user } from './user';

  let username;
  let password;

  function login() {
    user.auth(username, password, ({ err }) => err && alert(err));
  }

  function signup() {
    user.create(username, password, ({ err }) => {
      if (err) {
        alert(err);
      } else {
        login();
      }
    });
  }
</script>
<h4
style="color: white;"
>--CREATE AN ACCOUN TO PROCEED OR LOGIN WITH AN EXISTING ACCOUNT TO SEE MESSAGE HISTOTY,
  NOTE: THIS IS A PEER-TO-PEER COMMUNICATION SYSTEM THAT MEANS, THERE IS NO SERVER BEHIND THIS CHATROOM, THE TEXTS ARE ENCRYPTED AND HISTOTY IS STORED FOR 24HRS AS CLIENT BROWSER CACHE
</h4>
<h5
style="color: red;"
>Please respect others, be humble and enjoy the beauty of decentralization</h5>
<label for="username">Nickname🐋</label>
<input name="username" bind:value={username} minlength="3" maxlength="16" />

<label for="password">Password🔑</label>
<input name="password" bind:value={password} type="password" />

<button class="login" on:click={login}>Login</button>
<button class="login"  on:click={signup}>Sign Up</button>
  
