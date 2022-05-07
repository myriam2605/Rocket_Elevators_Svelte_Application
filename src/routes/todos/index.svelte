<script>
	import { enhance } from '$lib/form';
	import { scale } from 'svelte/transition';
	import { flip } from 'svelte/animate';
    import {onMount} from 'svelte'

	/**
	 * @typedef {{
	 *   uid: string;
	 *   created_at: Date;
	 *   text: string;
	 *   done: boolean;
	 *   pending_delete: boolean;
	 * }} Todo
	 */

	/** @type {Todo[]} */
	export let todos;
    export let message;
    export let myData = [];

    import { defaultEvmStores, web3, selectedAccount, connected, chainId, chainData } from 'svelte-web3'
    import RocketTokenContract from './RocketToken.json';
    import Image from 'sveltestrap/src/Image.svelte';
    import { dataset_dev } from 'svelte/internal';
    import About from '../about.svelte';

    const CONTRACT_ADDRESS = '0x4D266d91e6bf8f111f0068E8990d43093FDA1b27';

    let contractInstance;
    $: checkAccount = $selectedAccount || '0x0000000000000000000000000000000000000000'

    onMount(
      async () => {
        message = 'Connecting...'
        await defaultEvmStores.setBrowserProvider()
        message = ''
        contractInstance = await getContract(CONTRACT_ADDRESS)

        console.log("onMount contractInstance:", contractInstance)

        // const response = await fetch("https://rocket-elevators-express-api.herokuapp.com/NFT/getWalletTokens/${checkAccount}", {
        const response = await fetch(`https://rocket-elevators-express-api.herokuapp.com/NFT/getWalletTokens/${checkAccount}`, {
            method: "GET",
            headers: { 
                "Content-Type":"RocketToken/json",
            }
        });
        const userData = await response.json();
        myData = userData;

        console.log("onMount userData: ", myData);     
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
</script>

<svelte:head>
	<title>Portfolio</title>
	<meta name="description" content="A todo list app" />
</svelte:head>
<br><br><br><br>

<body>
    <h1> NFT 's Details *</h1>
    <ul>
        {#if myData.length !== 0}
            {#each myData as data, i}
            <div>
                <li><a href="https://rocket-elevators-express-api.herokuapp.com/NFT/getWalletTokens/${checkAccount}">
                    {i + 1}:<br><Image src= {data.image}/> <br><br>
                    {data.description} <br><br> {data.name}<br><br>
                </a></li>
            </div>
            {/each}
        {/if}

    </ul>
</body>
<style>
	.todos {
		width: 100%;
		max-width: var(--column-width);
		margin: var(--column-margin-top) auto 0 auto;
		line-height: 1;
	}

	.new {
		margin: 0 0 0.5rem 0;
	}

	input {
		border: 1px solid transparent;
	}

	input:focus-visible {
		box-shadow: inset 1px 1px 6px rgba(0, 0, 0, 0.1);
		border: 1px solid #ff3e00 !important;
		outline: none;
	}
	.new input {
		font-size: 28px;
		width: 100%;
		padding: 0.5em 1em 0.3em 1em;
		box-sizing: border-box;
		background: rgba(255, 255, 255, 0.05);
		border-radius: 8px;
		text-align: center;
	}
	.todo {
		display: grid;
		grid-template-columns: 2rem 1fr 2rem;
		grid-gap: 0.5rem;
		align-items: center;
		margin: 0 0 0.5rem 0;
		padding: 0.5rem;
		background-color: white;
		border-radius: 8px;
		filter: drop-shadow(2px 4px 6px rgba(0, 0, 0, 0.1));
		transform: translate(-1px, -1px);
		transition: filter 0.2s, transform 0.2s;
	}

	.done {
		transform: none;
		opacity: 0.4;
		filter: drop-shadow(0 0 1px rgba(0, 0, 0, 0.1));
	}

	form.text {
		position: relative;
		display: flex;
		align-items: center;
		flex: 1;
	}

	.todo input {
		flex: 1;
		padding: 0.5em 2em 0.5em 0.8em;
		border-radius: 3px;
	}

	.todo button {
		width: 2em;
		height: 2em;
		border: none;
		background-color: transparent;
		background-position: 50% 50%;
		background-repeat: no-repeat;
	}

	button.toggle {
		border: 1px solid rgba(0, 0, 0, 0.2);
		border-radius: 50%;
		box-sizing: border-box;
		background-size: 1em auto;
	}

	.done .toggle {
		background-image: url("data:image/svg+xml,%3Csvg width='22' height='16' viewBox='0 0 22 16' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M20.5 1.5L7.4375 14.5L1.5 8.5909' stroke='%23676778' stroke-width='1.5' stroke-linecap='round' stroke-linejoin='round'/%3E%3C/svg%3E");
	}

	.delete {
		background-image: url("data:image/svg+xml,%3Csvg width='24' height='24' viewBox='0 0 24 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M4.5 5V22H19.5V5H4.5Z' fill='%23676778' stroke='%23676778' stroke-width='1.5' stroke-linejoin='round'/%3E%3Cpath d='M10 10V16.5' stroke='white' stroke-width='1.5' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M14 10V16.5' stroke='white' stroke-width='1.5' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M2 5H22' stroke='%23676778' stroke-width='1.5' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M8 5L9.6445 2H14.3885L16 5H8Z' fill='%23676778' stroke='%23676778' stroke-width='1.5' stroke-linejoin='round'/%3E%3C/svg%3E%0A");
		opacity: 0.2;
	}

	.delete:hover,
	.delete:focus {
		transition: opacity 0.2s;
		opacity: 1;
	}

	.save {
		position: absolute;
		right: 0;
		opacity: 0;
		background-image: url("data:image/svg+xml,%3Csvg width='24' height='24' viewBox='0 0 24 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M20.5 2H3.5C2.67158 2 2 2.67157 2 3.5V20.5C2 21.3284 2.67158 22 3.5 22H20.5C21.3284 22 22 21.3284 22 20.5V3.5C22 2.67157 21.3284 2 20.5 2Z' fill='%23676778' stroke='%23676778' stroke-width='1.5' stroke-linejoin='round'/%3E%3Cpath d='M17 2V11H7.5V2H17Z' fill='white' stroke='white' stroke-width='1.5' stroke-linejoin='round'/%3E%3Cpath d='M13.5 5.5V7.5' stroke='%23676778' stroke-width='1.5' stroke-linecap='round'/%3E%3Cpath d='M5.99844 2H18.4992' stroke='%23676778' stroke-width='1.5' stroke-linecap='round'/%3E%3C/svg%3E%0A");
	}

	.todo input:focus + .save,
	.save:focus {
		transition: opacity 0.2s;
		opacity: 1;
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
