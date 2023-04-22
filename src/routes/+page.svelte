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

	const copy_to_clipboard = (text: string): null => {
		navigator.clipboard.writeText(text);
		return null;
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
		<p
			class="text-center mt-2 mx-auto cursor-pointer active:text-slate-400"
			on:click={copy_to_clipboard(mock(text))}
		>
			Click here to copy to clipboard
		</p>
	</div>
	<p class="text-center hover:text-pink-600 mx-auto">It's just a joke 🥸</p>
</div>
