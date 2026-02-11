<script>
	import { onMount } from 'svelte'
	import Post from "./lib/Post.svelte";
  	import Login from './lib/Login.svelte';
	import UserProfile from './lib/UserProfile.svelte';
	let name = $state('world');
	let count = $state(0);
	const url = `https://dummyjson.com/posts/`;
	/**
     * @type {any[] | null | undefined}
     */
	let posts = $state([]);
	async function getPosts() {
		const res = await fetch(url);
		if(res.ok) {
			const data = await res.json();
			posts = data.posts;
			console.log(posts);
		}
	}
	onMount(async() => {
		await getPosts()
	})
</script>

<h1>Hello {name}!</h1>

<input bind:value={name} />
<button onclick={() => count += 1}>
	clicks: {count}
</button>
<br>
<Login></Login>
<UserProfile></UserProfile>

{#each posts as post}
	<Post {post}></Post>
{/each}
{JSON.stringify(posts)}