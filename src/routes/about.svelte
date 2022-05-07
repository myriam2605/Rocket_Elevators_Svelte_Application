<script>
    import {onMount} from 'svelte'
	import { browser, dev } from '$app/env';

	// we don't need any JS on this page, though we'll load
	// it in dev so that we get hot module replacement...
	export const hydrate = dev;

	// ...but if the client-side router is already loaded
	// (i.e. we came here from elsewhere in the app), use it
	export const router = browser;

	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	export const prerender = true;

    export let myData;
    export let myData2;
    export let message;

    import { defaultEvmStores, web3, selectedAccount, connected, chainId, chainData } from 'svelte-web3';
    import RocketTokenContract from './todos/RocketToken.json';
    import Image from 'sveltestrap/src/Image.svelte';
    import { dataset_dev } from 'svelte/internal';
import { Button } from 'sveltestrap';

    const CONTRACT_ADDRESS = '0x4D266d91e6bf8f111f0068E8990d43093FDA1b27';

    let contractInstance;
    $: checkAccount = $selectedAccount || '0x0000000000000000000000000000000000000000'
  


    onMount(
      async () => {
        message = 'Connecting...'
        await defaultEvmStores.setBrowserProvider()
        message = ''
        contractInstance = await getContract(CONTRACT_ADDRESS)
        contractInstance.options.address = CONTRACT_ADDRESS;

        console.log("onMount contractInstance:", contractInstance)

        const response = await fetch(`https://rocket-elevators-express-api.herokuapp.com/NFT/gift/${checkAccount}`, {
            method: "GET",
            headers: { 
                "Content-Type":"RocketToken/json",
            }
        });
        const userData = await response.json();
        myData = userData;

        console.log("onMount userData: ", myData);
        
        const response2 = await fetch(`https://rocket-elevators-express-api.herokuapp.com/NFT/allowance/${checkAccount}`, {
            method: "GET",
            headers: { 
                "Content-Type":"RocketToken/json",
            }
        });
        const userData2 = await response2.json();
        myData2 = userData2;

        console.log("onMount userData2: ", myData2);
      }

    )

    async function getContract(address) {
      const networkId = await $web3.eth.net.getId();
      const deployedNetwork = RocketTokenContract.networks[networkId];
      return new $web3.eth.Contract(
          RocketTokenContract.abi,
        deployedNetwork && deployedNetwork.address, {
          from: address,
          gas: 2000000
        }
      );
    }

    const getFreeNFT = async () => {
        const response3 = await fetch(`https://rocket-elevators-express-api.herokuapp.com/NFT/gift/${checkAccount}`, {
            method: "POST",
            headers: { 
                "Content-Type":"application/json",
            }
        });
        alert("New NFT is Received! You can see it on the Portfolio page.")
    }

    const allowance = async () => {
        console.log() 
        await contractInstance.methods.approve("0xB16dB76BC1b994b5Da6edB14bCd4c2883A6772Bf", 1).send({
            from: checkAccount,
        });
        myData2 = true
    }

    const BuyNFT = async () => {
        const response4 = await fetch(`https://rocket-elevators-express-api.herokuapp.com/NFT/buyWithRocket/${checkAccount}`, {
            method: "POST",
            headers: { 
                "Content-Type":"application/json",
            }
        });
        if(response4.status == 200) {
            alert("New NFT is correctly purchased! You can see it on the Portfolio page.");
            window.location.href = "/todos";
        } else {  
            alert("Ooops, please try again")
        }
        
    }

</script>

<svelte:head>
	<title>NFT Minting </title>
	<meta name="description" content="About this app" />
</svelte:head>

<div class="content">
	<h1>NFT Minting </h1>
        <ul>
           
    

            {#if myData == true}
                <button class="btn btn-secondary d-block w-100" on:click={getFreeNFT}  href='https://rocket-elevators-express-api.herokuapp.com/NFT/gift/0x178625C9EBdD61307e0d63643aF7D1612B99408d' style="    display: flex;
                font-size: 2em;
                width: 100%;
                padding: 2% 0%;
                cursor: pointer;
                align-items: center;
                justify-content: center;
                align-content: space-between;
                flex-wrap: nowrap;
                flex-direction: row;);"> Get Free NFT</button>
                {:else } 
                        
                        {#if myData2 }
                        <button class="btn btn-secondary d-block w-100" on:click={BuyNFT}  href='https://rocket-elevators-express-api.herokuapp.com/NFT/gift/0x178625C9EBdD61307e0d63643aF7D1612B99408d' style="    display: flex;
                        font-size: 2em;
                        width: 100%;
                        padding: 2% 0%;
                        cursor: pointer;
                        align-items: center;
                        justify-content: center;
                        align-content: space-between;
                        flex-wrap: nowrap;
                        flex-direction: row;);">Payment Required</button>

                            {:else}


                            <button class="btn btn-secondary d-block w-100" on:click={allowance}  href='https://rocket-elevators-express-api.herokuapp.com/NFT/gift/0x178625C9EBdD61307e0d63643aF7D1612B99408d' style="    display: flex;
                            font-size: 2em;
                            width: 100%;
                            padding: 2% 0%;
                            cursor: pointer;
                            align-items: center;
                            justify-content: center;
                            align-content: space-between;
                            flex-wrap: nowrap;
                            flex-direction: row;);">Please approve transaction</button>

                        
                        {/if}

                               
            {/if}
        </ul>
	

	<p style='margin-left:16%'>
		The <a href="/todos">Portfolio</a> page illustrates all details about NFTs purchased.
        <br> Use the corresponding link!
	</p>
</div>


<style>
	.content {
		width: 100%;
		max-width: var(--column-width);
		margin: var(--column-margin-top) auto 0 auto;
	}
</style>
