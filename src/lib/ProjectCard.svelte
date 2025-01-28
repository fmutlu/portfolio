<script lang="ts">
  export let title: string;
  export let description: string;
  export let techStack: string[];
  export let image: string;
  export let link: string;
</script>

<a href={link} class="project-card" target="_blank" rel="noopener noreferrer">
  <img src={image} alt={title} class="project-image" />
  <div class="project-content">
    <h3>{title}</h3>
    <p>{description}</p>
    <div class="tech-stack">
      {#each techStack as tech}
        <span class="tech-badge">{tech}</span>
      {/each}
    </div>
  </div>
</a>

<style>
  .project-card {
    display: block;
    background: white;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    transition: transform 0.2s;
    text-decoration: none;
    color: inherit;
  }

  .project-card:hover {
    transform: translateY(-4px);
  }

  .project-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
  }

  .project-content {
    padding: 1.5rem;
  }

  h3 {
    margin: 0 0 1rem 0;
    font-size: 1.25rem;
  }

  p {
    margin: 0 0 1rem 0;
    color: #666;
  }

  .tech-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .tech-badge {
    background: #f0f0f0;
    padding: 0.25rem 0.5rem;
    border-radius: 4px;
    font-size: 0.875rem;
    color: #666;
  }
</style>