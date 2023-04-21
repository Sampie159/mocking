<script lang="ts">
	let text = '';

	const mock = (text: string): string => {
		let upper = true;
		let out = '';
		for (let i = 0; i < text.length; i++) {
			if (text.charAt(i) === ' ') out += ' ';
			else {
				if (upper) {
					out += text.charAt(i).toUpperCase();
					upper = !upper;
				} else {
					out += text.charAt(i).toLowerCase();
					upper = !upper;
				}
			}
		}
		return out;
	};
</script>

<title>Mock your friends!</title>

<div class="bg-slate-500 flex flex-col h-screen">
	<p class="self-center font-bold text-slate-900">Enter text here!</p>
	<textarea class="mx-9 h-56 font-bold" name="henlo" bind:value={text} id="henlo" />
	<p class="self-center font-bold text-slate-900">See the output here</p>
	<p class="mx-9 bg-white font-bold h-56">{mock(text)}</p>
</div>
