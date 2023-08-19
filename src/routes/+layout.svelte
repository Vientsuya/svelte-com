<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';

	let searchTerm = '';
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
			<svelte:fragment slot="lead">
				<a href="/" class="text-xl uppercase font-bold">Svelte-Com</a>
			</svelte:fragment>

			<svelte:fragment>
				<input class="input w-96 px-4 py-2 text-sm" type="search" name="demo" bind:value={searchTerm} placeholder="Search..." />
			</svelte:fragment>

			<svelte:fragment slot="trail">
				<a href="/favorites" class="btn btn-sm px-4 variant-filled-secondary">
					<img src="/star.png" alt="star icon" class="w-4">
					<span>Saved Items</span>
				</a>
				<a
					class="btn btn-sm px-4 variant-filled"
					href="/login"
					data-sveltekit-preload-data="hover"
				>
				<img src="/login.png" alt="login icon" class="w-4">
					<span>Sign in</span>
				</a>
				<a
					class="btn btn-sm px-4 variant-filled-primary"
					href="/register"
					data-sveltekit-preload-data="hover"
				>
				<img src="/register.png" alt="register icon" class="w-4">
					<span>Sign up</span>
				</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
