<script lang="ts">
	import { page } from "$app/state";
</script>

<main class="page">
	<h1>Unexpected Status: {page.status}</h1>
	<p>{page.error?.message ?? "An issue has occurred within Finakets."}</p>
	<a href="/">Return to Dashboard</a>
</main>
