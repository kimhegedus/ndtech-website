<script context="module">
  export async function preload(page, session){
    const res = await this.fetch('/getEnv/GITHUB_CLIENT_ID.json');
    const envVar = await res.json();
		const githubClientId = envVar.GITHUB_CLIENT_ID;
    return {githubClientId}
  }
</script>

<script>
  export let githubClientId;
	
	import Nav from '../components/Nav.svelte'
  	import LoadingBar from './_components/LoadingBar.svelte'
 	import Footer from '../components/Footer.svelte'
</script>

<LoadingBar/>

<Nav githubClientId={githubClientId}/>
<head>
	<script data-ad-client="ca-pub-6882490618446355" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
</head>


<main>
	<slot></slot>
</main>

<Footer />
