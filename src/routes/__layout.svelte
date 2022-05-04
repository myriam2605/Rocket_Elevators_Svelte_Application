<script>
	import Header from '$lib/header/Header.svelte';
	import '../app.css';
    
</script>

<Header />

<main>
	<slot />
</main>

<footer>
	<p>visit <a href="https://https://rocketelevatormyrasofia.com/">Rocketelevatormyrasofia.com</a> to learn SvelteKit</p>
    <div id="wrapper">    
    <div class="container">
          <div class="row">
            <!-- col #1 -->
            <div class="col-md-8">
              <h3 class="letter-spacing-1">WHY US?</h3>

              <!-- Small Description -->
              <p >
                We have the conviction that we create the most innovative and
                reliable products on the market. Contact us today for any
                questions you might have.
              </p>
              <h2 class="num">(418) 555-1234</h2>
            </div>
            <!-- /col #1 -->
          </div>
        </div>

        <div class="copyright">
          <div class="container">
           
            &copy; All Rights Reserved, Rocket Elevator LTD
          </div>
        </div>
    </div>
</footer>

<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 1024px;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 40px;
	}

    footer h2 {
    font-size: 20px;
    text-shadow: rgb(0 0 0 / 30%) 3px 3px 5px;
    }
	footer a {
		font-weight: bold;
	}
    .container p {
        margin-right: 50%;
    }
    .num {
        font-weight: 100;
        font-size: 16px;
    }
    .container {
        
    position: relative;
    width: 100%;
    min-height: 1px;
    padding-right: 15px;
    padding-left: 15px;
    }
    
    .container {
        position: relative;
    }
    .copyright {
        text-align: center;
    }
    
	@media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
	}
</style>
