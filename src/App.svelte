<script>

	let top = "";
	let bot = "";
	let img_url = "https://cdn.discordapp.com/attachments/816011914206511165/916927953781260348/unknown.png";
	let mime_url = `https://cdn.nathanferns.xyz/memes/default?image=${img_url}&top=${top}&bottom=${bot}`;

	async function cat(){
		let response = await fetch("https://api.thecatapi.com/v1/images/search");
		let data = await response.json();
		img_url = data[0].url;
		mime_url = `https://cdn.nathanferns.xyz/memes/default?image=${img_url}&top=${top}&bottom=${bot}`;
	}

</script>

<main>
	<h1>Random Cat Meme Generator</h1>
	<div class = "class1">
		<label>
			<h2>Top Text</h2>
			<input bind:value={top}>
		</label>
		
		<label>
			<h2>Bottom Text</h2>
			<input bind:value={bot}>
		</label>
	</div>

	<br>
	<img src = {mime_url} alt="meme"> <br> <br>
	<button on:click={cat} class="button1">Submit</button>

</main>

<style>
	.class1{
		display: flex;
		justify-content: center;
	}

	.class1 * {margin:0.5rem}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		font-size: 4em;
		font-weight: 100;
		font-family: Arial, Helvetica, sans-serif;
	}

	.button1{
		font-size: 24px; 
		background-color:red; 
		color:white; 
		padding: 15px 32px; 
		text-align: center; 
		border-radius: 12px;
		transition-duration: 0.4s;
	}

	.button1:hover{
		background-color: #4CAF50;
  		color: white;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	} 
</style>