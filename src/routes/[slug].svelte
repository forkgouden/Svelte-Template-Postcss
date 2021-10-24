<script context="module">
  export const load = async ({ page, fetch }) => {
    const slug = page.params.slug;
    const post = await fetch(`users/${slug}.json`).then((r) => r.json());
    return {
      props: { post },
    };
  };
</script>

<script>
  export let post;
</script>

<svelte:head>
  <title>{post.evento}</title>
</svelte:head>

<Funnel user={post} />
