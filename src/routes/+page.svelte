<script lang="ts">
	import { open } from '@tauri-apps/plugin-dialog';

	let path: string = $state('No directory selected');

	async function selectDirectory() {
		const selected = await open({
			directory: true
		});

		path = selected ?? '';
	}
</script>

<main>
	<button onclick={selectDirectory} type="button" class="btn preset-filled-primary-500">
		Directory...
	</button>
	<span class="text text-primary-500">{path}</span>
</main>
