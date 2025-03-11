<script lang="ts">
	import Button from "$lib/components/ui/button/button.svelte";
	import { Input } from "$lib/components/ui/input";
	import { invoke } from "@tauri-apps/api/core";

	let name = $state("");
	let greetMsg = $state("");

	async function greet(event: Event) {
		event.preventDefault();
		// Learn more about Tauri commands at https://tauri.app/develop/calling-rust/
		greetMsg = await invoke("greet", { name });
	}
</script>

<main class="container p-20">
	<h1>Welcome to Tauri + Svelte</h1>

	<form class="row" onsubmit={greet}>
		<div class="flex gap-4">
			<Input id="greet-input" placeholder="Enter a name..." bind:value={name} />
			<Button type="submit">Greet</Button>
		</div>
	</form>
	<p>{greetMsg}</p>
</main>
