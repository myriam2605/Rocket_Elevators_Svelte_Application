<script>
	import Header from '$lib/header/Header.svelte';
	import '../app.css';
    import logo from '../../src/lib/header/image-logo.svg';
    import { connected, web3, selectedAccount, chainId, chainData } from 'svelte-web3'

</script>

<Header />

<main>
	<slot />
    
</main>

<footer>
    <div id="wrapper">    
        <div class="container">
          <div class="row">
                <!-- col #1 -->
                    <div class="col-md-6">
                        <h3 class="letter-spacing-1">WHY US?</h3>

                        <!-- Small Description -->
                        <p >
                            We have the conviction that we create the most innovative and
                            reliable products on the market. Contact us today for any
                            questions you might have.
                        </p>
                        <h2 class="num">(418) 555-1234</h2>
                    </div>
                
                    <div class="corner col-md-6">
                        <a href="/">
                            <img src={logo} alt="Rocket-Elevator" style="width: 12em ; height: 6em"/>
                        </a>
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
		justify-content:space-between;
		align-items: center;
		/* padding: 20px; */
        padding: 2% 0px;
        background: #dae2ef;
	}

    footer h2 {
    font-size: 20px;
    text-shadow: rgb(0 0 0 / 30%) 3px 3px 5px;
    }
	footer a {
		font-weight: bold;
	}
    .container p {
        margin-right: 20%;
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
			padding: 2% 0;
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
.row {
    display: flex;
    align-items: center;
    justify-content: center;
}


</style>
