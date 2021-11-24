<script>
  export let movie;

  const posterBasePath = 'https://image.tmdb.org/t/p/w400';
</script>

<article>
  <div class="poster">
    <img loading="lazy" src={posterBasePath + movie.poster_path} alt={movie.title} />
  </div>
  <div class="title">
    {movie.title}
  </div>
</article>

<style>
  article {
    margin-bottom: 20px;
    width: calc((100vw - (var(--discoverColumnPadding) * var(--numberOfDiscoverColumns))) / var(--numberOfDiscoverColumns));
    max-width: calc((var(--maxPrimaryPageWidth) - (var(--discoverColumnPadding) * var(--numberOfDiscoverColumns))) / var(--numberOfDiscoverColumns));
    box-shadow: 0 2px 8px rgb(0 0 0 / 10%);
    border: 1px solid #e3e3e3;
    background-color: #fff;
    border-radius: 8px;
    overflow: hidden;
  }

  .poster {
    width: 100%;
    height: calc((100vw - (var(--discoverColumnPadding) * var(--numberOfDiscoverColumns))) / var(--numberOfDiscoverColumns) * 1.5);
    max-height: calc((var(--maxPrimaryPageWidth) - (var(--discoverColumnPadding) * var(--numberOfDiscoverColumns))) / var(--numberOfDiscoverColumns) * 1.5);
  }

  .title {
    padding: 10px;
    font-size: 16px;
    font-weight: 500;
    text-align: center;
  }

  img {
    width: 100%;
    height: 100%;
  }
</style>
