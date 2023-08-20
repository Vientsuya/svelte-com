<script lang='ts'>
	// The ordering of these imports is critical for app to work properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
	// floating ui imports for pop ups to work
	import { computePosition, autoUpdate, offset, shift, flip, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';

	import { popup } from '@skeletonlabs/skeleton';
    import type { PopupSettings } from '@skeletonlabs/skeleton';

	// populate skeleton's popup store
	storePopup.set({ computePosition, autoUpdate, offset, shift, flip, arrow });

	const popupClick: PopupSettings = {
        event: 'hover',
        target: "popupName",
        placement: 'bottom'
    }


	let searchTerm = '';
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<div class="app-bar flex flex-col justify-center items-center bg-surface-100-800-token space-y-4 p-4">
			<div class="w-4/5 grid grid-cols-3">
				<a href="/" class="text-xl uppercase font-bold">Svelte-Com</a>

				<input class="input w-96 px-4 py-2 text-sm" type="search" name="demo" bind:value={searchTerm} placeholder="Search..." />
				
				<div class="display flex justify-end">
					<button class="btn btn-sm px-4 font-bold">
						<img src="/language.png" alt="language icon" class="w-4">
						<span>EN</span>
					</button>

					<button class="btn btn-sm px-4 font-bold">
						<img src="/money.png" alt="money icon" class="w-4">
						<span>PLN</span>
					</button>
				</div>
			</div>

			<div class="w-4/5 flex justify-between">
				<div class="bg-red-400 col-span-2">Categories</div>

				<div>
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
				</div>
			</div>
		</div>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>

<!--<svelte:fragment slot="lead">
				<a href="/" class="text-xl uppercase font-bold">Svelte-Com</a>
			</svelte:fragment>

			<svelte:fragment slot="default">
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
-->