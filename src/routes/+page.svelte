<script lang="ts">
  import Button from "$lib/components/ui/button/button.svelte";
  import { Input } from "$lib/components/ui/input";
  import { invoke } from "@tauri-apps/api/core";
  import * as Card from "$lib/components/ui/card";
  let name = $state("");
  let greetMsg = $state("");

  async function greet(event: Event) {
    event.preventDefault();
    // Learn more about Tauri commands at https://tauri.app/develop/calling-rust/
    greetMsg = await invoke("greet", { name });
  }
</script>

<main class="container p-20">
  <Card.Root>
    <Card.Header>
      <h1>Welcome to Tauri + Svelte</h1>
    </Card.Header>

    <Card.Content>
      <form class="row" onsubmit={greet}>
        <div class="flex gap-4">
          <Input
            id="greet-input"
            placeholder="Enter a name..."
            bind:value={name}
          />
          <Button type="submit">Greet</Button>
        </div>
        <p>{greetMsg}</p>
      </form>
    </Card.Content>
  </Card.Root>
</main>
