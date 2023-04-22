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

<div class="bg-slate-500 flex-col flex h-screen justify-between">
	<div class="flex flex-col">
		<textarea
			class="m-9 h-56 font-bold outline-none text-slate-900 border-black border-2 rounded-xl text-center shadow-black shadow-sm"
			placeholder="Enter text here!"
			name="henlo"
			bind:value={text}
			id="henlo"
		/>
		<textarea
			readonly
			class="mx-9 h-56 font-bold outline-none border-black border-2 rounded-xl text-center text-slate-400 bg-slate-900 shadow-black shadow-sm"
			placeholder="Get output here">{mock(text)}</textarea
		>
	</div>
	<p class="text-center">It's just a joke 🥸</p>
</div>
