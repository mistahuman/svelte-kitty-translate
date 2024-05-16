<script>
	import logo from '$lib/assets/kitty-translate.png'
	let textToTranslate = "";
	let textTranslated = "Meow translation here";
 	
	function translate() {
		let splittedWords = textToTranslate.split(" ")
		splittedWords = splittedWords.filter((word) => {
			if (!word.trim()) {
				return false
			}
			return true
		})
		
		textTranslated = splittedWords.map((word) => {
			if (word.length > 3) {
				return "miao"
			}
			return "mia"	
		}).join(" ")
	}
	
	$: console.log(textToTranslate)
</script>

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-5">
		<h1 class="h1">Kitty Translate</h1>
		<img alt="ciao" src={logo} />
		<label class="label">
			<span>Textarea</span>
			<textarea class="textarea" rows="4" bind:value={textToTranslate} placeholder="" />
		</label>
			<button type="button" class="btn variant-filled" on:click={translate}>
				<!-- <span>(icon)</span> -->
				<span>Translate</span>
			</button>
		<p>
			{textTranslated}
		</p>
	</div>
</div>

