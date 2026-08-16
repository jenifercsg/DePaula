<template>
  <div class="landing-page">
    <div class="section__landingPage">
      <nav class="navbar">
        <img src="../assets/imagens/LogodePaula.png" alt="logo" class="logo-perfil" />

        <ul class="nav-links">
          <li><a href="#hero">Home page</a></li>
          <li><a href="#about">About Us</a></li>
          <li><a href="#servicos">Works</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
          <a
            href="https://wa.me/18623441728"
            target="_blank"
            rel="noopener noreferrer"
            class="cta-button"
          >
            GET A FREE QUOTE
          </a>
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
            <li><a href="#hero" @click="toggleMenu">HOME PAGE</a></li>
            <li><a href="#about" @click="toggleMenu">ABOUT US</a></li>
            <li><a href="#servicos" @click="toggleMenu">WORKS</a></li>
            <li><a href="#contact" @click="toggleMenu">CONTACT</a></li>
            <li>
              <a
                href="https://wa.me/18623441728?text=Hello!%20I%20would%20like%20to%20get%20a%20free%20quote."
                target="_blank"
                rel="noopener noreferrer"
                class="cta-button-mobile"
              >
                GET A FREE QUOTE
              </a>
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

    <button
      class="seta-comentario esquerda"
      @click="comentarioAnterior"
      aria-label="Comentário anterior"
    >
      <ChevronLeft />
    </button>

        <div class="comentario-topo">

          <img
            :src="comentarios[comentarioAtual].foto"
            alt="foto do perfil de comentário"
            class="comentarista"
          />

          <div class="comentario-textos">

            <img
              src="../assets/imagens/stars.png"
              alt="Estrelas"
              class="estrela"
            />

            <p class="text__comentario">
              “{{ comentarios[comentarioAtual].texto }}”
            </p>

            <p class="nome-comentarista">
              {{ comentarios[comentarioAtual].nome }}
              <span class="cargo">
                {{ comentarios[comentarioAtual].empresa }}
              </span>
            </p>

          </div>
        </div>

    <button
      class="seta-comentario direita"
      @click="proximoComentario"
      aria-label="Próximo comentário"
    >
      <ChevronRight />
    </button>

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
            <li>
              <Check class="check-icon" />
              Plumbing & drainage lines
            </li>

            <li>
              <Check class="check-icon" />
              Electrical conduits & cabling
            </li>

            <li>
              <Check class="check-icon" />
              HVAC ductwork & ventilation
            </li>

            <li>
              <Check class="check-icon" />
              Structural anchoring & concrete sampling
            </li>
          </ul>
        </div>

        <div class="service-card">
          <h3>Concrete Cutting & Sawing</h3>

          <p>High-powered precision cutting with advanced diamond blade technology.</p>

          <ul>
            <li>
              <Check class="check-icon" />
              Slab & Flat Sawing
            </li>

            <li>
              <Check class="check-icon" />
              Wall Sawing
            </li>

            <li>
              <Check class="check-icon" />
              Demolition & structural modifications
            </li>

            <li>
              <Check class="check-icon" />
              Full slurry vacuuming & cleanup included
            </li>
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

                        <a
                href="https://wa.me/18623441728?text=Hello!%20I%20would%20like%20to%20get%20a%20free%20quote."
                target="_blank"
                rel="noopener noreferrer"
                class="footer-button"
              >
                GET A FREE QUOTE
              </a>
        </div>

        <div class="footer-middle">
          <h4>Contact Us</h4>

          <a
            href="https://wa.me/18623441728"
            target="_blank"
            rel="noopener noreferrer"
            class="contact-link"
          >
            <img src="../assets/imagens/icon_whats.png" alt="WhatsApp" />
            <span>(+1) 862 344-1728</span>
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

import { ChevronLeft, ChevronRight, Check  } from 'lucide-vue-next'

import modelo from '../assets/imagens/modelo.png'
import modelo2 from '../assets/imagens/modelo2.png'
import modelo3 from '../assets/imagens/modelo3.png'
import modelo4 from '../assets/imagens/modelo4.png'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const comentarioAtual = ref(0)

const comentarios = ref([
  {
    foto: modelo,
    texto:
      'I’ve worked with countless core drilling contractors throughout my career, and DePaula Services is truly different. Their commitment to quality, professionalism, and reliability is unmatched. They’re the kind of company you can trust to get the job done right every time.',
    nome: 'Piter Goes',
    empresa: 'Goes - Plumbing & Gas Piping',
  },

  {
    foto: modelo2,
    texto:
      'Whenever DePaula Services is on one of our projects, I know the job will be done right. They prioritize safety, deliver outstanding quality, follow all job site requirements, and always complete the work exactly as requested. Fast, precise, and reliable.',
    nome: 'Jeffrey Muniz',
    empresa: 'Project Manager',
  },

  {
    foto: modelo3,
    texto:
      'Having DePaula Services handle our core drilling makes our work much more efficient. It allows my crew to stay focused on plumbing while knowing the core drilling is in good hands. They’re fast, reliable, and always get the job done right',
    nome: 'Afonso Garcia',
    empresa: 'Foreman RIT Plumbing contractor',
  },

    {
    foto: modelo4,
    texto:
      'Having DePaula Services handle our core drilling makes our work much more efficient. It allows my crew to stay focused on plumbing while knowing the core drilling is in good hands. They’re fast, reliable, and always get the job done right',
    nome: 'Impacto core drilling',
    empresa: 'Impacto core drilling',
  },
])


function proximoComentario() {
  comentarioAtual.value =
    (comentarioAtual.value + 1) % comentarios.value.length
}

function comentarioAnterior() {
  comentarioAtual.value =
    (comentarioAtual.value - 1 + comentarios.value.length) %
    comentarios.value.length
}


</script>
