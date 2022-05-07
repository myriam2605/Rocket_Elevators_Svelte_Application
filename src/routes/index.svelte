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



//   const items = [
//     'Image thumbnail alt="Dunes" src="https://picsum.photos/100/100?random=7"',
//     'data:image/svg+xml;charset=UTF-8,%3Csvg%20width%3D%22800%22%20height%3D%22400%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20viewBox%3D%220%200%20800%20400%22%20preserveAspectRatio%3D%22none%22%3E%3Cdefs%3E%3Cstyle%20type%3D%22text%2Fcss%22%3E%23holder_15ba800aa20%20text%20%7B%20fill%3A%23444%3Bfont-weight%3Anormal%3Bfont-family%3AHelvetica%2C%20monospace%3Bfont-size%3A40pt%20%7D%20%3C%2Fstyle%3E%3C%2Fdefs%3E%3Cg%20id%3D%22holder_15ba800aa20%22%3E%3Crect%20width%3D%22800%22%20height%3D%22400%22%20fill%3D%22%23666%22%3E%3C%2Frect%3E%3Cg%3E%3Ctext%20x%3D%22247.3203125%22%20y%3D%22218.3%22%3ESecond%20slide%3C%2Ftext%3E%3C%2Fg%3E%3C%2Fg%3E%3C%2Fsvg%3E',
//     'data:image/svg+xml;charset=UTF-8,%3Csvg%20width%3D%22800%22%20height%3D%22400%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20viewBox%3D%220%200%20800%20400%22%20preserveAspectRatio%3D%22none%22%3E%3Cdefs%3E%3Cstyle%20type%3D%22text%2Fcss%22%3E%23holder_15ba800aa21%20text%20%7B%20fill%3A%23333%3Bfont-weight%3Anormal%3Bfont-family%3AHelvetica%2C%20monospace%3Bfont-size%3A40pt%20%7D%20%3C%2Fstyle%3E%3C%2Fdefs%3E%3Cg%20id%3D%22holder_15ba800aa21%22%3E%3Crect%20width%3D%22800%22%20height%3D%22400%22%20fill%3D%22%23555%22%3E%3C%2Frect%3E%3Cg%3E%3Ctext%20x%3D%22277%22%20y%3D%22218.3%22%3EThird%20slide%3C%2Ftext%3E%3C%2Fg%3E%3C%2Fg%3E%3C%2Fsvg%3E'
  
// ];

  let activeIndex = 0;
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<div class="slideHome">
		<div >
			<Figure caption="The 'Ahead AdScreen' from Schindler turns the cabin wall into a screen.
            Photo: Schindler" style="font-size:80%;">
                <Image fluid alt="Landscape" src="https://www.urban-hub.com/wp/wp-content/uploads/2020/11/AGILE_Touchpad.jpg" style="display: flex;
                width: 100%;
                flex-wrap:nowrap;
                justify-content: space-between;
                align-items: center;
                flex-direction: row;
                align-content: center;"/>
            </Figure>
				<!-- <source srcset="svelte-welcome.webp" type="image/webp" /> -->
				<!-- <img src="../../images/china.jpeg"  /> -->
		
		</div>
        <div>
            <h3>
                What forces are really driving innovation in elevator services today?
            </h3>
            
            <h2 style="
                text-align: justify;
                max-width: fit-content;
                display: flex;
                justify-content: center;
                align-items: center;
            ">
                “This is a great question. The answer is customer needs – combined with a shared vision across a competent team of people who are aligned and driven to solve the customer’s problem is the driving force behind a lot of innovation.

                Take, for example, one of our forward-looking customers in New York City. They asked if we could help them make our elevators ‘touchless’. We didn’t have a product, but with our experience in AGILE security and access control, as well as insights from robot integrations, we went from idea to an on-board solution in seven weeks.
                
                We accomplished it with a dynamic team of people that included our customer’s cybersecurity and IT team, a long-time industry technology partner, and our own dedicated and intelligent technologists.”
            </h2>
        </div>

    </div>
		


</section>
<br> <br><br>
<section id="carousselPhoto">

    <!-- <Carousel {items} bind:activeIndex>
        <CarouselIndicators bind:activeIndex {items} />
      
        <div class="carousel-inner">
          {#each items as item, index}
            <CarouselItem bind:activeIndex itemIndex={index}>
              <img src={item} class="d-block w-100" alt={`${item} ${index + 1}`} />
            </CarouselItem>
          {/each}
        </div>
      
        <CarouselControl direction="prev" bind:activeIndex {items} />
        <CarouselControl direction="next" bind:activeIndex {items} />
      </Carousel> -->

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

        display: flex;
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
