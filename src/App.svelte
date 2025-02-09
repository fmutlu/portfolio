<script lang="ts">
  import ProjectCard from './lib/ProjectCard.svelte';
  import profileImage from './assets/profile.jpg';
  import aircraftGif from './assets/aircraftraj.gif';
  import portfolioImage from './assets/svelte.png';
  import StockMarketImage from './assets/stockmarket.png';
  import earthquakeImage from './assets/earthquake.png';
  import musicVisualizationImage from './assets/music.png';
  let currentUrl = window.location.pathname;

  
const projects = [
  {
    title: "Portfolio",
    description: "This personal website showcasing my projects and skills.",
    techStack: ["Svelte", "Vite", "TypeScript"],
    image: portfolioImage,
    link: "#"
  },
  {
    title: "Master's Project: Aircraft Trajectory Prediction using Deep Learning",
    description: "Implementation of a state-of-the-art Transformer based model for predicting aircraft trajectories.",
    techStack: ["Pytorch", "Python", "PySpark", "AWS", "GCP", "Numpy", "Pandas"],
    image: aircraftGif,
    link: "https://www.fatihmutlu.com/assets/aircraftraj-XQcIs77I.gif"
  },
  {
    title: "Stock Markets & Google Trends",
    description: "Google Trends powered stock market prediction.",
    techStack: ["Sklearn", "Python", "Pandas", "Numpy"],
    image: StockMarketImage,
    link: "https://ecaquot.github.io/adache/"
  },
  {
    title: "Earthquake Prediction using Deep Learning Algorithms",
    description: "Developed LSTM-based models to forecast timing and magnitude of upcoming earthquakes.",
    techStack: ["LSTM", "TensorFlow", "PyTorch", "Python"],
    image: earthquakeImage, 
    link: `#`
  },
  {
    title: "22 Years of Music",
    description: "Interactive visualizations of songs and artists featured on the Billboard Chart.",
    techStack: ["JavaScript", "Python", "Spotify API", "Musixmatch API"],
    image: musicVisualizationImage,
    link: "https://com-480-data-visualization.github.io/datavis-project-2022-vizards/"
  },
];
</script>

<main>
  <section class="hero">
    <div class="profile-section">
      <div class="profile-container">
        <div class="left-side">
          <img src={profileImage} alt="Profile" class="profile-image" />
        </div>
        <div class="right-side">
          <div class="name">
            <h1>Fatih</h1>
            <h1>Mutlu</h1>
          </div>
          <div class="details">
            <p class="title"><strong>AI & Data Consultant</strong></p>
            <p>5+ years of experience in coding</p>
            <p style="position: relative;">Expertise in PyTorch &nbsp
              <img src="https://pytorch.org/assets/images/pytorch-logo.png" alt="Pytorch" class="tech-logo pytorch-logo" /> 
               &nbsp and Spark
              <img src="https://spark.apache.org/images/spark-logo-rev.svg" alt="Spark" class="tech-logo spark-logo" />
            </p>
            <p><strong>MSc in Computer Science, EPFL</strong></p>
            <p>Data Analytics track</p>
            <div class="social-links">
              <a href="https://linkedin.com/in/fatihml" target="_blank" rel="noopener noreferrer">
                <img src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" alt="LinkedIn" class="social-icon" />
              </a>
              <a href="https://github.com/fmutlu" target="_blank" rel="noopener noreferrer">
                <img src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/github.svg" alt="GitHub" class="social-icon" />
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="projects" class="projects">
    <h2>Projects</h2>
    <div class="projects-grid">
      {#each projects as project}
        <ProjectCard {...project} />
      {/each}
    </div>
  </section>
</main>

<style>
  main {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
  }

  .hero {
    min-height: auto;
    padding: 4rem 0 2rem;
  }

  .profile-section {
    display: flex;
    justify-content: center;
    margin-bottom: 2rem;
  }

  .profile-container {
    display: grid;
    grid-template-columns: 40% 60%;
    gap: 2rem;
    max-width: 1000px;
    width: 100%;
  }

  .left-side {
    display: flex;
    justify-content: flex-end;
    align-items: flex-start;
    padding-right: 2rem;
  }

  .right-side {
    padding-left: 2rem;
  }

  .profile-image {
    width: 250px;
    height: 250px;
    border-radius: 50%;
    object-fit: cover;
  }

  .name h1 {
    font-size: 3.5rem;
    line-height: 1;
    margin: 0;
    font-weight: bold;
  }

  .details {
    margin-top: 1rem;
  }

  .details p {
    margin: 0.5rem 0;
    font-size: 1.1rem;
  }

  .title {
    font-size: 1.3rem !important;
    color: #333;
  }

  .small {
    font-size: 0.9em;
  }

  .tech-logo {
    height: 20px;
    vertical-align: middle;
    margin: 0 0.3rem;
    position: absolute;
    z-index: -1;
  }

  .pytorch-logo {
    transform: translate(-1em, 0.17em) scale(1.15);
  }

  .spark-logo {
    transform: translate(-1.4em, 0.32em) scale(1.15);
  }

  .social-links {
    display: flex;
    gap: 1rem;
    margin-top: 1rem;
  }

  .social-icon {
    width: 24px;
    height: 24px;
    filter: invert(0.5);
    transition: filter 0.2s;
  }

  .social-icon:hover {
    filter: invert(0.7);
  }

  .projects {
    padding: 2rem 0;
  }

  .projects h2 {
    text-align: center;
    margin-bottom: 2rem;
  }

  .projects-grid {
    display: grid;
    gap: 2rem;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  }

  @media (max-width: 768px) {
    .profile-container {
      grid-template-columns: 1fr;
      gap: 2rem;
    }

    .left-side {
      justify-content: center;
      padding-right: 0;
    }

    .right-side {
      padding-left: 0;
      text-align: center;
    }

    .name h1 {
      font-size: 2.5rem;
    }

    .social-links {
      justify-content: center;
    }

    .hero {
      padding: 2rem 0 1rem;
    }
  }
</style>
