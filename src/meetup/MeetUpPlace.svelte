<script>
  import Button from "../UI/Button.svelte";

  export let title;
  export let imageUrl;
  export let description;
  export let address;
  export let email;
</script>

<article>
  <header>
    <h1>{title}</h1>
    <p>{address}</p>
  </header>
  <div class="img">
    <img src={imageUrl} alt={title} />
  </div>
  <div class="content">
    <p>{description}</p>
  </div>
  <footer>
    <Button href="mailto:{email}" caption="Contact" />
    <Button mode="outline" buttonType="submit" caption="Favorite" />
    <Button buttonType="submit" caption="Show details" />
  </footer>
</article>

<style>
  article {
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
    border-radius: 5px;
    background: white;
    margin: 1rem;
  }

  header,
  .content,
  footer {
    padding: 1rem;
  }

  .content {
    height: 4rem;
  }
  .img {
    width: 100%;
    height: 15rem;
  }

  .img img {
    width: 100%;
    height: 100%;
    background-size: cover;
  }

  h1 {
    font-size: 1.25rem;
    margin: 0.5rem 0;
    font-family: "Times New Roman", Times, serif;
  }
  p {
    font-size: 1.25rem;
    margin: 0;
  }

  div {
    text-align: center;
  }
</style>
