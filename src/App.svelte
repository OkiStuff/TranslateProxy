<script>
	let url = "";
	let prefix = "https://translate.google.com/translate?sl=en&tl=en&u=";
	let redirect_mode;

	const handleSubmit = () => {
		if (redirect_mode == 0) window.location.replace(`${prefix}${url}`); // Simulate HTTP redirect
		if (redirect_mode == 1) window.location.href = `${prefix}${url}`;
	};

</script>

<main>
	<h1>TranslateProxy</h1>
	<p>Use Google Translate to bypass website blocking</p>

	<form on:submit|preventDefault = {handleSubmit}>
		<input bind:value={url} placeholder="Enter URL here">
		<select bind:value={redirect_mode}>
			<option value=1>JS Redirect</option>
			<option value=0>HTTP Redirect</option>
		</select>


		<button on:click={() => {
			//window.location.replace(url);	
		}}>Submit</button>

	</form>

	<footer>
		<p>&copy; OkiStuff - 2021, All Rights Reserved. <br /><a href="https://mit-license.org/">View the license here</a></p>
	</footer>
</main>
<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: gray;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>