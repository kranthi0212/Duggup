<!-- Card.svelte -->
<script>
  export let imageUrl = '';
  export let description = '';
</script>

<div class="card">
  <div class="image-container">
    <img src={imageUrl} alt="Card Image">
  </div>
  <div class="description">
    <p>{description}</p>
  </div>
</div>

<style>
  .card {
    background-color: #fff;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    margin: 16px;
    max-width: 344px;
    overflow: hidden;
  }

  .image-container {
    height: 136px; /* Max height for the image */
    width: 100%;
    overflow: hidden;
  }

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 8px 8px 0 0;
  }

  .description {
    padding: 16px;
  }

  p {
    font-size: 16px;
    line-height: 1.5;
    margin: 0;
  }
</style>
