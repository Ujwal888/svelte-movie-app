<script context "module">
	export async function load({ fetch, params }) {
		console.log(params.id);
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/{movie_id}?api_key=7ae0738adbf8622547048ce7c01b80af&language=en-US`
		);
		const data = await res.json();
		console.log(data);
		if (res.ok) {
			return {
				props: { popular: data.results }
			};
		}
	}
</script>
