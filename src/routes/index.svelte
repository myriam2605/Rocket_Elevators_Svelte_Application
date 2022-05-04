<script context="module">
	export const prerender = true;
</script>

<script>
	// import Counter from '$lib/Counter.svelte';

    import { Figure, Image } from 'sveltestrap';
    
  </script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>




<section id="services">
  <div class="container">
        <div class="row row-cols-2">
            <div class="col">
                <h2>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Tenetur, blanditiis voluptatum aperiam suscipit corrupti porro ratione voluptate enim expedita voluptatem omnis, quisquam animi laboriosam. Eius, architecto. Temporibus unde tenetur ea.
                </h2>
            </div>
            <div class="col">
                <h2>
                    <Figure caption="I believe this is a cow needing a haircut">
                        <Image fluid alt="Landscape" src="https://picsum.photos/id/200/800/600" />
                    </Figure>
                </h2>
            </div>
        </div>

    </div>    
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}
    h2 {
    margin: 0% 15% 0% 15%;
    text-align: center;
    }
	.welcome {
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
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
