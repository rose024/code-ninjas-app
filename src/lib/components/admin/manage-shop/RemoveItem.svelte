<script lang="ts">
	
	export let data;
	let showModal = false;
	import { blur, scale } from 'svelte/transition';
	
</script>

<button
	in:scale
	on:click={() => {
		showModal = true;
	}}
	class="modify-btn bold-9 cursor-pointer">Remove Item</button>

{#if showModal}
	<span>
		<div transition:blur>
			<button
				class="close-btn"
				on:click={() => {
					showModal = false;
				}}
			>
				<img src="/close-login.png" alt="" />
			</button>

			<form action="">

				<input type="text" name="username" placeholder="Item Name">
				<button class="primary-btn bold-9 cursor-pointer">Remove</button>	
			</form>
			
			
		</div>
	</span>
{/if}

<style lang="scss">
	span {
		position: absolute;
		height: 100vh;
		width: 100vw;
		top: 0;
		left: 0;
		display: flex;
		justify-content: center;
		align-items: center;
		backdrop-filter: blur(0.25em);
		z-index: 2;

		div {
			background-image: linear-gradient(#1ab7e5, #00619a);
			padding: 2.5em 4.5em;
			border-radius: 1em;
			display: flex;
			justify-content: center;
			align-items: center;
			flex-direction: column;
			gap: 1em;
			box-shadow: 0 0px 10px 0px rgba(74, 74, 74, 0.509);
			position: relative;

			.close-btn {
				position: absolute;
				border: none;
				top: 1em;
				right: 1em;
				background-color: transparent;
				img {
					height: 2.3em;
					cursor: pointer;
				}
			}

			div {
				background-image: none;
				flex-direction: row;
				gap: 0;
				padding: 0em;
				border-radius: 0;
				border: solid 1px black;
				box-shadow: none;
			}

			form {
				display: flex;
				justify-content: center;
				align-items: center;
				flex-direction: column;
				gap: 1em;
				input {
					text-align: center;
				}

				h5, small {
					color: white
				}
			}
		}
	}
</style>
