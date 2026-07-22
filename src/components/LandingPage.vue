<template>
  <div class="landing-page">
    <div class="section__landingPage">
      <nav class="navbar">
        <img src="../assets/imagens/LogodePaula.png" alt="logo" class="logo-perfil" />

        <ul class="nav-links">
          <li><a href="#about">Home page</a></li>
          <li><a href="#work">Works</a></li>
          <li><a href="#about">About Us</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
        <button class="cta-button">GET A FREE QUOTE</button>
      </nav>
      <nav id="hamburger-nav">
        <img src="../assets/imagens/LogodePaula.png" alt="logo" class="logo-perfil" />
        <div class="hamburger-menu">
          <div class="hamburger-icon" @click="toggleMenu">
            <span></span>
            <span></span>
            <span></span>
          </div>
          <div class="menu-links" :class="{ open: isMenuOpen }">
            <li><a href="#about" @click="toggleMenu">HOME PAGE</a></li>
            <li><a href="#work" @click="toggleMenu">WORKS</a></li>
            <li><a href="#about" @click="toggleMenu">ABOUT US</a></li>
            <li><a href="#contact" @click="toggleMenu">CONTACT</a></li>
            <li>
              <a href="tel:+18623441728" class="cta-button-mobile"> GET A FREE QUOTE </a>
            </li>
          </div>
        </div>
      </nav>
      <section class="hero">
        <div class="hero-text">
          <p class="section__text__p1">DE PAULA CORE DRILLING SERVICES</p>
          <h1 class="title">
            Your trusted partner for high-precision concrete cutting and drilling in
            <span>New York, New Jersey and Pennsylvania.</span>
          </h1>
          <p class="section__text__p2">MORE THAN DRILLING. WE DELIVER <strong>RESULTS.</strong></p>
        </div>
        <div class="section__pic-profile">
          <img src="../assets/imagens/trabalho.png" alt="Produtos" />
        </div>
      </section>
    </div>
    <section id="about" class="sobre-studio">
      <h2 class="text__p1__sobre">ABOUT US</h2>
      <p class="text__p2__sobre">Welcome to Our Home</p>
      <div class="fundador">
        <div class="fundador-img-container">
          <img src="../assets/imagens/fundador.png" alt="Fundador" class="fundador-img" />
        </div>
        <div class="fundador-texto">
          <h3 class="fundador_text">MEET OUR FOUNDER & CEO</h3>
          <h4 class="fundador_text2">Silvio Luciano de Paula</h4>
          <p class="fundador_text3">
            Silvio is the driving force behind the company’s reputation for excellence. As an
            industry specialist with years of hands-on expertise in concrete cutting and core
            drilling, he has built the business on three unshakeable pillars: honesty, absolute
            precision, and strict punctuality. Unlike companies where ownership is disconnected from
            the field, Silvio brings deep technical knowledge to every project, ensuring that safety
            standards are met and deadlines are respected. When you work with us, you are partnering
            with a leader dedicated to keeping your job site safe, efficient, and on schedule.
          </p>
          <div id="redes">
            <div class="rede-1">
              <a
                href="https://www.instagram.com/depaulaservices/"
                target="_blank"
                rel="noopener noreferrer"
                class="instagram-link"
              >
                <img src="../assets/imagens/preto_instagram.png" alt="Instagram" class="icon" />
                <p class="text-redes">
                  <strong>Follow Our Work on Instagram</strong>
                </p>
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section id="equipe" class="sobre-equipe">
      <div class="equipe-container">
        <div class="equipe-texto">
          <h2 class="text__equipe">THE TEAM</h2>
          <p class="text__equipe__descricao">
            At De Paula Core Drilling, we deliver clean, precise, and efficient concrete cutting
            services for residential and commercial projects across NY and NJ. Armed with
            professional-grade equipment and a commitment to safety, our team handles everything
            from deep core drilling to precise slab and wall sawing. We know that construction
            schedules are tight, which is why we pride ourselves on punctuality, pristine job site
            cleanup, and reliable emergency availability. No job is too complex. Contact us today
            for a fast, free quote and get your project moving forward.
          </p>
        </div>
        <div class="equipe-imagem">
          <img src="../assets/imagens/time.png" alt="Equipe de mulheres" class="imagem-equipe" />
        </div>
      </div>
    </section>
    <section id="classificacao" class="comentario">
      <div class="comentario-container">
        <div class="comentario-topo">
          <img
            src="../assets/imagens/modelo.png"
            alt="foto do perfil de comentário"
            class="comentarista"
          />
          <div class="comentario-textos">
            <img src="../assets/imagens/stars.png" alt="Estrelas" class="estrela" />
            <p class="text__comentario">
              “Very punctual, fairly priced, and the quality of the work exceeded my expectations!”
            </p>
            <p class="nome-comentarista">
              Magno Bennett <span class="cargo">CEO of Bennett Constructs</span>
            </p>
          </div>
        </div>
      </div>
      <div class="estatisticas">
        <div class="estatistica">
          <h3 class="valor__estatistica">100</h3>
          <p class="clientes__estatisticas">clientes fixas por mês</p>
        </div>
        <div class="estatistica">
          <h3 class="valor__estatistica">+2.000</h3>
          <p class="clientes__estatisticas">clientes atendidas por ano</p>
        </div>
        <div class="estatistica">
          <h3 class="valor__estatistica">+20</h3>
          <p class="clientes__estatisticas">serviços ofertados</p>
        </div>
      </div>
    </section>
    <section id="servicos" class="nossos__servicos">
      <div class="servicos-container">
        <h3 class="text__servico">OUR SERVICES</h3>
        <h2 class="text__agende">Book Your De Paula Core drilling Experience Today.</h2>
        <div class="cards-servicos">
          <div class="card-servico">
            <h4 class="titulo">CONCRETE CUTTING</h4>
            <video :src="video1" autoplay muted loop playsinline class="video-card"></video>
            <p class="descricao">
              Concrete Cutting & Sawing High-powered precision cutting for horizontal and vertical
              concrete structures.
            </p>
          </div>
          <div class="card-servico">
            <h4 class="titulo">Core Drilling</h4>

            <video :src="video2" autoplay muted loop playsinline class="video-card"></video>
            <p class="descricao">
              Core Drilling Clean, precise, and dust-controlled circular openings through reinforced
              concrete, brick, block, and asphalt.
            </p>
          </div>
        </div>
      </div>
    </section>
    <section class="expertise">
      <span class="subtitle">OUR EXPERTISE</span>

      <h2>
        Professional Core Drilling &
        <span>Concrete Cutting</span>
      </h2>

      <p class="intro">
        Delivering clean, precise, and professional concrete cutting solutions with state-of-the-art
        equipment and experienced operators.
      </p>

      <div class="expertise-grid">
        <div class="service-card">
          <h3>Core Drilling</h3>

          <p>
            Clean, precise, and dust-controlled circular openings through reinforced concrete,
            brick, block, and asphalt.
          </p>

          <ul>
            <li>✔ Plumbing & drainage lines</li>
            <li>✔ Electrical conduits & cabling</li>
            <li>✔ HVAC ductwork & ventilation</li>
            <li>✔ Structural anchoring & concrete sampling</li>
          </ul>
        </div>

        <div class="service-card">
          <h3>Concrete Cutting & Sawing</h3>

          <p>High-powered precision cutting with advanced diamond blade technology.</p>

          <ul>
            <li>✔ Slab & Flat Sawing</li>
            <li>✔ Wall Sawing</li>
            <li>✔ Demolition & structural modifications</li>
            <li>✔ Full slurry vacuuming & cleanup included</li>
          </ul>
        </div>
      </div>
    </section>

    <footer id="contact" class="footer">
      <div class="footer-container">
        <div class="footer-left">
          <img src="../assets/imagens/certificado.png" alt="Logo OSHA" class="footer-logo" />

          <h3>OSHA Compliant</h3>

          <p>
            We follow OSHA safety standards to ensure every project is completed safely,
            efficiently, and professionally.
          </p>

          <a href="tel:+18623441728" class="footer-button"> GET A FREE QUOTE </a>
        </div>

        <div class="footer-middle">
          <h4>Contact Us</h4>

          <a href="tel:+18623441728" class="contact-link">
            <img src="../assets/imagens/icon_whats.png" alt="WhatsApp" />
            <span>(+1) 86234-41728</span>
          </a>

          <a href="mailto:depaulaservicesllc@outlook.com" class="contact-link">
            <img src="../assets/imagens/icon_gmail.png" alt="Email" />
            <span>depaulaservicesllc@outlook.com</span>
          </a>
        </div>

        <div class="footer-right">
          <h4>Follow Us!</h4>

          <a
            href="https://www.instagram.com/depaulaservices"
            target="_blank"
            rel="noopener noreferrer"
            class="contact-link"
          >
            <img src="../assets/imagens/logoinstagram.png" alt="Instagram" />
            <span>@depaulaservices</span>
          </a>
        </div>
      </div>
    </footer>
    <div class="footer-bottom">
      <p>Developed by Jenifer de Paula. © 2026. All rights reserved.</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import video1 from '../assets/videos/video1.mp4'
import video2 from '../assets/videos/video2.mp4'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>
