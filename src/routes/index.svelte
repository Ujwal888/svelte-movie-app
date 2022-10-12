<script>
    import PopularMovies from '../Components/PopularMovies.svelte';
    export let popular;
        
</script>
<script context ="module">
    export async function load({ fetch}) {
      const res = await fetch (
      `https://api.themoviedb.org/3/movie/popular?api_key=7ae0738adbf8622547048ce7c01b80af&language=en-US&page=1`
  
    );
    const data = await res.json();
    console.log(data);
    if (res.ok){
      return {
        props: {popular: data.results}
      };
    }
  } 
 
    </script>

    <section><PopularMovies {popular}/></section>
    
    