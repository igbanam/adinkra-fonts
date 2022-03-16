<script context='module'>
  export async function load({ fetch }) {

    const res = await fetch(`names.json`)
    const adinkra = await res.json()

    return {
      props: {
        adinkra
      }
    }
  }
</script>

<script>
  import Thumbnail from '$lib/Thumbnail.svelte'

  export let adinkra

  function generateColor() {
    return `#${Math.floor(Math.random()*16777215).toString(16)}`
  }
</script>

<svelte:head>
  <title>Adinkra</title>
</svelte:head>

<div id="site">
</div>

<header>
  <h1>Adinkra</h1>
  <p>...as fonts!</p>
</header>

<section>
  <h2>How to install</h2>

  <ol>
    <li>Add the <code>adinkra.css</code> style to your project</li>
  </ol>
</section>

<section>
  <h2>How to use</h2>

  <pre>
    {`<i class="adk adk-<name>"></i>`}
  </pre>

  <p>
    You may also wrap this in container elements and style those elements to
    your heart's content.
  </p>

  <pre>
    {`
    <span class="my-custom-class">
      <i class="adk adk-<name>"></i>
    </span>
    `}
  </pre>

  <p>
    This icon set works well with already existing CSS frameworks like
    <a href="https://getbootstrap.com">Bootstrap</a>, <a
       href="https://bulma.io">Bulma</a>, and <a
       href="https://tailwindcss.com">Tailwind</a>.
  </p>

</section>

<section id="showcase">
  <header>
    <h2>The Showcase</h2>
  </header>

  <symbols>
  {#each Object.values(adinkra) as name}
    <Thumbnail {name} icon_color={generateColor()} />
  {/each}
  </symbols>
</section>

<style>
  * {
    font-family: Georgia, serif;
    margin: 0;
  }

  header, section {
    padding: 10px 20px;
  }

  pre, p, ol {
    margin: 20px 0;
  }

  :not(section) header {
    height: 20vh;
  }

  header {
    vertical-align: middle;
    text-align: center;
    padding: 10px 20px;
  }

  header h1 {
    font-size: 4rem;
  }

  header p {
    font-size: 1.2rem;
    font-style: italic;
  }

  pre, code {
    font-family: monospace;
    font-size: 1rem;
    background-color: #eee;
    border-radius: 5px;
    padding: 0;
  }

  li code {
    padding: 2px 5px;
  }

  #showcase .header {
    display: flex;
    justify-content: between;
  }

  #showcase symbols {
    text-align: center;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }

  #showcase symbols div {
    display: block;
  }
</style>
