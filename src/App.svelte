<script>
	let url = "";
	let search = "";

	let prefix = "https://translate.google.com/translate?sl=en&tl=en&u=";

	let bing_redirect_mode;
	let prefix_bing = "https://bing.com/search?q=";

	let blocked_urls = [
		"https://www.buzzfeed.com",
		"https://buzzfeed.com",
		"http://www.buzzfeed.com",
		"http://buzzfeed.com"
	];
	let redirect_mode;

	const handleSubmit = () => {
		//blocked_urls.forEach(element => {
		//	if (url == element) alert("no");
		//});

		if (redirect_mode == 0) window.location.replace(`${prefix}${url}`); // Simulate HTTP redirect
		if (redirect_mode == 1) window.location.href = `${prefix}${url}`;
	};

	const handleSearch = () => {
		if (redirect_mode == 0) window.location.replace(`${prefix}${prefix_bing}${search}`); // Simulate HTTP redirect
		if (redirect_mode == 1) window.location.href = `${prefix}${prefix_bing}${search}`;
	}

</script>

<main>
	<h1>TranslateProxy v2</h1>
	<p>Use Google Translate to bypass website blocking</p>

	<form on:submit|preventDefault = {handleSubmit}>
		<input bind:value={url} placeholder="Enter URL here">
		<select bind:value={redirect_mode}>
			<option value=1>JS Redirect</option>
			<option value=0>HTTP Redirect</option>
		</select>


		<button>Submit</button>

	</form>

	<p>or</p>

	<form on:submit|preventDefault = {handleSearch}>
		<input bind:value={search} placeholder="Search on Bing (beta)">
		<select bind:value={bing_redirect_mode}>
			<option value=1>JS Redirect</option>
			<option value=0>HTTP Redirect</option>
		</select>

		<button>Submit</button>

	</form>

	<footer>
		<p>&copy; OkiStuff - 2021, All Rights Reserved. <br /><a href="https://mit-license.org/">View the license here</a><br /><a href="/learn_more.html">Learn More</a></p>
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