<script>
	import ThemeSwitch from '../lib/components/ThemeSwitch.svelte';
    import { theme } from '../lib/stores'
</script>

<svelte:head>
    <meta name='color-scheme' content={$theme == 'system' ? 'light dark' : $theme}/>
    <link rel="stylesheet" href={`/theme/${$theme}.css`} />
</svelte:head>

<ThemeSwitch />
<slot />