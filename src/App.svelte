<script>
  import { onMount } from 'svelte';
  import MovieCard from './MovieCard.svelte';

  const apiKey = '2ffe2cefa3ecef9f33e2603f6f63936d';

  let movies = [];

  onMount(async () => {
    await fetch(`https://api.themoviedb.org/3/movie/popular?api_key=${apiKey}`)
      .then((r) => r.json())
      .then((data) => {
        movies = (data && data.results) || [];
        console.log(movies);
      });
  });
</script>

<main>
  <h2>Popular Movies</h2>

  <div class="grid">
    {#each movies as movie}
      <MovieCard {movie} />
    {/each}
  </div>
</main>

<style>
  main {
    --maxPrimaryPageWidth: 1000px;
    --numberOfDiscoverColumns: 1;
    --discoverColumnPadding: 30px;

	max-width: var(--maxPrimaryPageWidth);
	margin: 20px auto 0px;
  }

  h2 {
    font-size: 20px;
    margin: 0 0 20px;
  }

  .grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }

  @media only screen and (min-width: 700px) {
    main {
      --numberOfDiscoverColumns: 2;
    }
  }

  @media only screen and (min-width: 900px) {
    main {
      --numberOfDiscoverColumns: 3;
    }
  }

  @media only screen and (min-width: 1040px) {
    main {
      --numberOfDiscoverColumns: 4;
    }
  }

  @media only screen and (min-width: 1240px) {
    main {
      --numberOfDiscoverColumns: 5;
    }
  }
</style>
