<script context="module">
	export const prerender = true;
</script>

<script>
	// import Counter from '$lib/Counter.svelte';
    import { Figure, Image } from 'sveltestrap';
    import { Button } from 'sveltestrap';
    import { connected, web3, selectedAccount, chainId, chainData } from 'svelte-web3'
    import {
    Carousel,
    CarouselControl,
    CarouselIndicators,
    CarouselItem
  } from 'sveltestrap';

  let activeIndex = 0;
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<div class="slideHome">
		<div >
			<Figure caption="PHOTOGRAPH: PAUL YEUNG/BLOOMBERG/GETTY IMAGES" style="font-size:80%;">
                <Image fluid alt="Landscape" src="https://media.wired.com/photos/622bde93d53a49d05c484009/16:9/w_2400,h_1350,c_limit/NFTs-Don't-Work-They-Way-You-Think-Gear-1239020052.jpg" style="display: flex;
                width: 100%;
                flex-wrap:nowrap;
                justify-content: space-between;
                align-items: center;
                flex-direction: row;
                align-content: center;
                "/>
            </Figure>
		
		</div>
        <div>
            <h3 style="margin: 3% 5%;">
                NFTs Don’t Work the Way You Might Think They Do <br>
                <br> We bust the biggest misconceptions about what "minting" actually means.
            </h3>
            
            <h2 style="
                text-align: justify;
                max-width: fit-content;
                display:flex
                justify-content: center;
                line-height: 1.5;
                margin: 0% 5%;
                align-items: center;
            ">
                “IT’S BEEN IMPOSSIBLE to avoid hearing about NFTs in recent months. Hype for the tokens—pitched as proof of ownership of a digital item—has reached a fever pitch, while billions of dollars have poured into the market for them. To some, these non-fungible tokens are the hottest new collectible hobby, to others a powerful investment tool, and still more, they’re the future of the internet.

                The reality is, as always, more complex. In their current state, NFTs aren’t actually capable of doing much of what they’re often claimed to do. The extremely technical nature of how NFTs, blockchains, and cryptocurrencies work means that it’s easy to simplify the explanation of the tech to the point of being misleading.
                
                Explaining the problems with NFTs is complicated, but we’re going to try to break down the issues as succinctly as we can. We have to tackle this with the understanding that no explanation, no matter how in-depth, can ever be totally comprehensive. With that in mind, there are some misconceptions about NFTs that are worth clearing up...”
            </h2>
        </div>

    </div>
</section>
<br> <br><br>
<section id="carousselPhoto">

    <div class="owl-carousel owl-padding-10 buttons-autohide controlls-over owl-theme owl-carousel-init"  style="opacity: 1; display: block;">
        <div class="owl-wrapper-outer">
                <div class="owl-wrapper" style="width: 2796px; left: 0px; display: block; transition: all 800ms ease 0s; ">
                    <div class="owl-item" style="width: 100%;">
                        <div class="img-hover">
                            <Image thumbnail alt="Dunes" src="https://picsum.photos/100/100?random=7" />

                            <Image thumbnail alt="Bicycle" src="https://picsum.photos/100/100?random=8" />
                            <Image thumbnail alt="Dunes" src="https://picsum.photos/100/100?random=9" />

                            <Image thumbnail alt="Bicycle" src="https://picsum.photos/100/100?random=6" />
                            <Image
                            thumbnail
                            alt="Television"
                            src="https://picsum.photos/100/100?random=3"
                            />
                            <Image thumbnail alt="Dunes" src="https://picsum.photos/100/100?random=4" />

                            <Image thumbnail alt="Bicycle" src="https://picsum.photos/100/100?random=5" />

                            <Image
                            thumbnail
                            alt="Television"
                            src="https://picsum.photos/100/100?random=1"/> 
                            <Image thumbnail alt="Dunes" src="https://picsum.photos/100/100?random=2" />

                            <Image thumbnail alt="Bicycle" src="https://picsum.photos/100/100?random=11" />
                    </div>
                </div>
            </div>
        </div> 
    </div>
</section>
<br><br><br>
<section style="background: #0c649c;">
    <Button block style="font-size:2em; padding: 2% 10% 2% 10%; color: #dae2ef;" href="/about"> NFT Minting</Button>
</section>

<style>
    #carousselPhoto {
        padding: 4% 3%;
        display: block;
        border: solid;
        margin: 0% 0%;
}
    .owl-carousel {
        overflow: hidden;
        margin-bottom: 0px;
        position: relative;
}
::after, ::before {
    box-sizing: border-box;
}
    #carousselPhoto{
        display: block;
    }
   .slideHome{
        /* display: flex; */
        flex-direction: row-reverse;
        flex-wrap: nowrap;
        align-content: center;
        justify-content: space-between;
        align-items: center;
    }
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
</style>
