<script>
	import Header from '$lib/header/Header.svelte';
	import '../app.css';
    
</script>

<Header />

<main>
	<slot />
    <div>
        <section id="services">
            <div class="container">

                <div class="row">
                    <div class="col-sm-4">
                        <img class="img-fluid" src="../../src/lib/header/rocket1.svg" alt="img" />
                        <h3 class="mt-10">Prices and Projects</h3>
                        <p>Rocket Elevator is a company that has overcome several challenges since its launch. Thanks to its dedicated team, it has several awards in its field.</p>
                        <a href="home.html#portfolio" class="btn btn-default">PORTFOLIO</a>
                    </div>

                    <div class="col-sm-4">
                        <img class="img-fluid" src="../../src/lib/header/rocket2.svg" alt="img" />
                        <h3 class="mt-10">Residential Buildings</h3>
                        <p>With our products and services, we are committed to making your home comfortable and safe with good quality. We are always ready to advise you.</p>
                        <a href="about.html" class="btn btn-default">RESIDENTIAL</a>
                    </div>

                    <div class="col-sm-4">
                        <img class="img-fluid" src="../../src/lib/header/rocket3.svg" alt="img" />
                        <h3 class="mt-10">Corporate Buildings</h3>
                        <p>Thanks to the skills of our teams, we are ready to take up the challenge of offering you a quality office in a short time as you wish or better.</p>
                    <a href="todos.html" class="btn btn-default">CORPORATE</a>
                    </div>

                </div>

            </div>
        </section>


    </div>
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
        margin-right: 0%;
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
    .row {
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -ms-flex-wrap: wrap;
        /* flex-wrap: wrap; */
        margin-right: -15px;
        margin-left: -15px;
    }
    .col-sm-4 {
        position: relative;
        width: 100%;
        min-height: 1px;
        padding-right: 15px;
        padding-left: 15px;
    }
    
	@media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
        .col-sm-4 {
            -webkit-box-flex: 0;
            -ms-flex: 0 0 33.333333%;
            flex: 0 0 33.333333%;
            max-width: 33.333333%;
        }
	}
    .container {
  width: 100%;
  padding-right: 15px;
  padding-left: 15px;
  margin-right: auto;
  margin-left: auto;
}

@media (min-width: 576px) {
  .container {
    max-width: 540px;
  }
}

@media (min-width: 768px) {
  .container {
    max-width: 720px;
  }
}

@media (min-width: 992px) {
  .container {
    max-width: 960px;
  }
}

@media (min-width: 1200px) {
  .container {
    max-width: 1140px;
  }
}
</style>
