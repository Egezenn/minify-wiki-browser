<script lang="ts">
  const wikiUrl = "https://egezenn.github.io/dota2-minify/wiki/";
  let frame: HTMLIFrameElement;

  function reloadWiki() {
    frame.src = wikiUrl;
  }
</script>

<div class="wiki-browser">
  <header class="toolbar">
    <strong>Minify Wiki</strong>
    <span class="address">{wikiUrl}</span>
    <button type="button" on:click={reloadWiki}>Reload</button>
    <a href={wikiUrl} target="_blank" rel="noreferrer">Open in browser</a>
  </header>
  <iframe bind:this={frame} src={wikiUrl} title="Dota 2 Minify Wiki"></iframe>
</div>

<style>
  :global(html),
  :global(body) {
    width: 100%;
    height: 100%;
    margin: 0;
    overflow: hidden;
    background: transparent;
    color: var(--text-primary, #e0e0e0);
    font: 13px var(--font-sans, system-ui, sans-serif);
  }

  .wiki-browser {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100vh;
    background: transparent;
  }

  .toolbar {
    display: flex;
    align-items: center;
    gap: 8px;
    min-height: 38px;
    padding: 0 8px;
    border-bottom: 1px solid var(--border-color, #333);
    background: var(--bg-secondary, #1a1a1a);
  }

  .address {
    flex: 1;
    overflow: hidden;
    color: var(--text-secondary, #aaa);
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  button,
  a {
    padding: 4px 8px;
    border: 1px solid var(--btn-border, #333);
    border-radius: 6px;
    background: var(--btn-bg, #1e1e1e);
    color: var(--btn-text, #e0e0e0);
    font: inherit;
    text-decoration: none;
    cursor: pointer;
  }

  button:hover,
  a:hover {
    background: var(--btn-hover-bg, #282828);
    border-color: var(--btn-hover-border, var(--accent, #17bebe));
  }

  iframe {
    flex: 1;
    width: 100%;
    border: 0;
    background: transparent;
  }
</style>
