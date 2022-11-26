<template >

  <div id="app">


    <body>
    <!--- #### THE HEAD #### -->
    <div id="header">

      <div class="subHeader">
        <div class="container-fluid" style="padding-top:1ex">

          <div class="row">

            <div class="col-4">

              <nav style="--bs-breadcrumb-divider: '/';" aria-label="breadcrumb">
                <ol class="breadcrumb">
                  {if isset($USER)}
                  <li class="breadcrumb-item active" aria-current="page">/{$USER.name}</li>
                  {else}
                  <li class="breadcrumb-item active" aria-current="page">/home</li>
                  {/if}
                </ol>
              </nav>
            </div>

            <div class="col-8" style="text-align:right;">

              {if isset($USER)}
              <a href="./logout_action.php">logout</a>
              <a href=#>post blog</a>
              {else}
              <a href="./login.php">login</a>
              <a href="./register.php">register</a>
              {/if}
              <a href=#>Welcome {$USER.name|default:"anon"}</a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class ="wrapper">
      <div class="container">
        <h1 class="blogName">Inside the Walls</h1>
          <Microposts/>
      </div>
    </div>

    <footer class="footer bg-light text-center">

      <div class="text-center p-3" style="background-color: rgba(0, 0, 0, 0.2)">
        © 2022 Copyright:
        Quevin Protsenko IPM
      </div>

    </footer>
    </body>
  </div>
</template>

<script>
  import Microposts from "@/views/Microposts";
  export default {
    components: {Microposts}
  }

</script>

<style scoped>
	#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 100px;
	}
</style>