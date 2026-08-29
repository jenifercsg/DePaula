<template>
  <div class="landing-page">
    <div class="section__landingPage" id="hero">
      <header class="site-header">
        <nav class="navbar" aria-label="Primary navigation">
          <a href="#hero" class="brand-link" aria-label="De Paula Core Drilling home">
            <img
              src="../assets/optimized/LogodePaula-340.png"
              alt="De Paula Core Drilling Services logo"
              class="logo-perfil"
              width="170"
              height="113"
            />
          </a>

          <ul class="nav-links">
            <li><a href="#hero">Home page</a></li>
            <li><a href="#about">About Us</a></li>
            <li><a href="#servicos">Works</a></li>
            <li><a href="#contact">Contact</a></li>
          </ul>

          <button class="cta-button" type="button" @click="openContactOptions">
            GET A FREE QUOTE
          </button>
        </nav>

        <nav id="hamburger-nav" aria-label="Mobile navigation">
          <a href="#hero" class="brand-link" aria-label="De Paula Core Drilling home">
            <img
              src="../assets/optimized/LogodePaula-340.png"
              alt="De Paula Core Drilling Services logo"
              class="logo-perfil"
              width="116"
              height="77"
            />
          </a>

          <div class="hamburger-menu">
            <button
              class="hamburger-icon"
              :class="{ open: isMenuOpen }"
              type="button"
              :aria-expanded="isMenuOpen"
              aria-controls="mobile-menu"
              aria-label="Toggle navigation menu"
              @click="toggleMenu"
            >
              <span></span>
              <span></span>
              <span></span>
            </button>

            <ul id="mobile-menu" class="menu-links" :class="{ open: isMenuOpen }">
              <li><a href="#hero" @click="closeMenu">HOME PAGE</a></li>
              <li><a href="#about" @click="closeMenu">ABOUT US</a></li>
              <li><a href="#servicos" @click="closeMenu">WORKS</a></li>
              <li><a href="#contact" @click="closeMenu">CONTACT</a></li>
              <li>
                <button class="cta-button-mobile" type="button" @click="openContactOptions">
                  GET A FREE QUOTE
                </button>
              </li>
            </ul>
          </div>
        </nav>
      </header>

      <section class="hero reveal-section" aria-labelledby="hero-title">
        <div class="hero-text reveal-item">
          <p class="section__text__p1">DE PAULA CORE DRILLING SERVICES</p>
          <h1 id="hero-title" class="title">
            Your trusted partner for high-precision concrete cutting and drilling in
            <span>New York, New Jersey and Pennsylvania.</span>
          </h1>
          <p class="section__text__p2">MORE THAN DRILLING. WE DELIVER <strong>RESULTS.</strong></p>
        </div>
        <div class="section__pic-profile reveal-item">
          <img
            src="../assets/imagens/trabalho.png"
            alt="Concrete cutting and drilling work performed by De Paula Core Drilling"
            width="1200"
            height="628"
          />
        </div>
      </section>
    </div>

    <main>
      <section id="about" class="sobre-studio reveal-section" aria-labelledby="about-title">
        <h2 id="about-title" class="text__p1__sobre reveal-item">ABOUT US</h2>
        <p class="text__p2__sobre reveal-item">Welcome to Our Home</p>
        <div class="fundador">
          <div class="fundador-img-container reveal-item">
            <img
              src="../assets/optimized/fundador-620.jpg"
              alt="Silvio Luciano de Paula, founder and CEO of De Paula Core Drilling"
              class="fundador-img"
              width="1020"
              height="1542"
              loading="lazy"
            />
          </div>
          <div class="fundador-texto reveal-item">
            <h3 class="fundador_text">MEET OUR FOUNDER & CEO</h3>
            <h4 class="fundador_text2">Silvio Luciano de Paula</h4>
            <p class="fundador_text3">
              Silvio is the driving force behind the company's reputation for excellence. As an
              industry specialist with years of hands-on expertise in concrete cutting and core
              drilling, he has built the business on three unshakeable pillars: honesty, absolute
              precision, and strict punctuality. Unlike companies where ownership is disconnected
              from the field, Silvio brings deep technical knowledge to every project, ensuring that
              safety standards are met and deadlines are respected. When you work with us, you are
              partnering with a leader dedicated to keeping your job site safe, efficient, and on
              schedule.
            </p>
            <div id="redes">
              <div class="rede-1">
                <a
                  href="https://www.instagram.com/depaulaservices/"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="instagram-link"
                >
                  <img
                    src="../assets/imagens/preto_instagram.png"
                    alt=""
                    class="icon"
                    width="40"
                    height="40"
                    loading="lazy"
                  />
                  <span class="text-redes">
                    <strong>Follow Our Work on Instagram</strong>
                  </span>
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section id="equipe" class="sobre-equipe reveal-section" aria-labelledby="team-title">
        <div class="equipe-container">
          <div class="equipe-texto reveal-item">
            <h2 id="team-title" class="text__equipe">THE TEAM</h2>
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
          <div class="equipe-imagem reveal-item">
            <img
              src="../assets/imagens/time.png"
              alt="De Paula Core Drilling field team"
              class="imagem-equipe"
              width="1600"
              height="1271"
              loading="lazy"
            />
          </div>
        </div>
      </section>

      <section
        id="classificacao"
        class="comentario reveal-section"
        aria-labelledby="feedback-title"
      >
        <div class="comentario-container">
          <h2 id="feedback-title" class="feedback reveal-item">FEEDBACKS</h2>

          <button
            class="seta-comentario esquerda"
            type="button"
            @click="comentarioAnterior"
            aria-label="Previous testimonial"
          >
            <ChevronLeft aria-hidden="true" />
          </button>

          <article class="comentario-topo reveal-item" aria-live="polite">
            <img
              :src="comentarios[comentarioAtual].foto"
              :alt="`Profile photo of ${comentarios[comentarioAtual].nome}`"
              class="comentarista"
              width="120"
              height="120"
              loading="lazy"
            />

            <div class="comentario-textos">
              <img src="../assets/optimized/stars-250.png" alt="Five star rating" class="estrela" />

              <blockquote class="text__comentario">
                "{{ comentarios[comentarioAtual].texto }}"
              </blockquote>

              <p class="nome-comentarista">
                {{ comentarios[comentarioAtual].nome }}
                <span class="cargo">
                  {{ comentarios[comentarioAtual].empresa }}
                </span>
              </p>
            </div>
          </article>

          <button
            class="seta-comentario direita"
            type="button"
            @click="proximoComentario"
            aria-label="Next testimonial"
          >
            <ChevronRight aria-hidden="true" />
          </button>
        </div>
      </section>

      <section id="servicos" class="nossos__servicos reveal-section" aria-labelledby="services-title">
        <div class="servicos-container">
          <p class="text__servico reveal-item">OUR SERVICES</p>
          <h2 id="services-title" class="text__agende reveal-item">
            Book Your De Paula Core drilling Experience Today.
          </h2>
          <div class="cards-servicos">
            <article class="card-servico reveal-item">
              <h3 class="titulo">CONCRETE CUTTING</h3>
              <video
                :src="video2"
                autoplay
                muted
                loop
                playsinline
                preload="metadata"
                poster="../assets/imagens/trabalho.png"
                class="video-card"
                aria-label="Concrete cutting service video"
              ></video>
              <p class="descricao">
                Concrete Cutting & Sawing High-powered precision cutting for horizontal and vertical
                concrete structures.
              </p>
            </article>
            <article class="card-servico reveal-item">
              <h3 class="titulo">Core Drilling</h3>

              <video
                :src="video1"
                autoplay
                muted
                loop
                playsinline
                preload="metadata"
                poster="../assets/imagens/trabalho.png"
                class="video-card"
                aria-label="Core drilling service video"
              ></video>
              <p class="descricao">
                Core Drilling Clean, precise, and dust-controlled circular openings through
                reinforced concrete, brick, block, and asphalt.
              </p>
            </article>
          </div>
        </div>
      </section>

      <section class="expertise reveal-section" aria-labelledby="expertise-title">
        <span class="subtitle reveal-item">OUR EXPERTISE</span>

        <h2 id="expertise-title" class="reveal-item">
          Professional Core Drilling &
          <span>Concrete Cutting</span>
        </h2>

        <p class="intro reveal-item">
          Delivering clean, precise, and professional concrete cutting solutions with
          state-of-the-art equipment and experienced operators.
        </p>

        <div class="expertise-grid">
          <article class="service-card reveal-item">
            <h3>Core Drilling</h3>

            <p>
              Clean, precise, and dust-controlled circular openings through reinforced concrete,
              brick, block, and asphalt.
            </p>

            <ul>
              <li>
                <Check class="check-icon" aria-hidden="true" />
                Plumbing & drainage lines
              </li>

              <li>
                <Check class="check-icon" aria-hidden="true" />
                Electrical conduits & cabling
              </li>

              <li>
                <Check class="check-icon" aria-hidden="true" />
                HVAC ductwork & ventilation
              </li>

              <li>
                <Check class="check-icon" aria-hidden="true" />
                Structural anchoring & concrete sampling
              </li>
            </ul>
          </article>

          <article class="service-card reveal-item">
            <h3>Concrete Cutting & Sawing</h3>

            <p>High-powered precision cutting with advanced diamond blade technology.</p>

            <ul>
              <li>
                <Check class="check-icon" aria-hidden="true" />
                Slab & Flat Sawing
              </li>

              <li>
                <Check class="check-icon" aria-hidden="true" />
                Wall Sawing
              </li>

              <li>
                <Check class="check-icon" aria-hidden="true" />
                Demolition & structural modifications
              </li>

              <li>
                <Check class="check-icon" aria-hidden="true" />
                Full slurry vacuuming & cleanup included
              </li>
            </ul>
          </article>
        </div>
      </section>
    </main>

    <footer id="contact" class="footer reveal-section">
      <div class="footer-container">
        <div class="footer-left reveal-item">
          <img
            src="../assets/optimized/certificado-160.png"
            alt="OSHA compliant certification badge"
            class="footer-logo"
            width="1024"
            height="1024"
            loading="lazy"
          />

          <h2>OSHA Compliant</h2>

          <p>
            We follow OSHA safety standards to ensure every project is completed safely,
            efficiently, and professionally.
          </p>

          <button class="footer-button" type="button" @click="openContactOptions">
            GET A FREE QUOTE
          </button>
        </div>

        <div class="footer-middle reveal-item">
          <h2>Contact Us</h2>

          <a
            href="https://wa.me/18623441728"
            target="_blank"
            rel="noopener noreferrer"
            class="contact-link"
          >
            <img src="../assets/optimized/icon_whats-80.png" alt="" width="40" height="40" />
            <span>(+1) 862 344-1728</span>
          </a>

          <a href="mailto:depaulaservicesllc@outlook.com" class="contact-link">
            <img src="../assets/optimized/icon_gmail-80.png" alt="" width="40" height="40" />
            <span>depaulaservicesllc@outlook.com</span>
          </a>
        </div>

        <div class="footer-right reveal-item">
          <h2>Follow Us!</h2>

          <a
            href="https://www.instagram.com/depaulaservices"
            target="_blank"
            rel="noopener noreferrer"
            class="contact-link"
          >
            <img src="../assets/optimized/logoinstagram-80.png" alt="" width="40" height="40" />
            <span>@depaulaservices</span>
          </a>
        </div>
      </div>
    </footer>

    <div class="footer-bottom">
      <p>Developed by Jenifer de Paula. © 2026. All rights reserved.</p>
    </div>

    <ContactModal :open="showContactOptions" @close="closeContactOptions" />
  </div>
</template>

<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue'
import video1 from '../assets/videos/video1.mp4'
import video2 from '../assets/videos/video2.mp4'
import ContactModal from './ContactModal.vue'

import { ChevronLeft, ChevronRight, Check } from 'lucide-vue-next'

import modelo from '../assets/imagens/modelo.png'
import modelo2 from '../assets/imagens/modelo2.png'
import modelo3 from '../assets/imagens/modelo3.png'
import modelo4 from '../assets/imagens/modelo4.png'

const isMenuOpen = ref(false)
const showContactOptions = ref(false)
let revealObserver

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}

const openContactOptions = () => {
  showContactOptions.value = true
  closeMenu()
}

const closeContactOptions = () => {
  showContactOptions.value = false
}

const comentarioAtual = ref(0)

const comentarios = ref([
  {
    foto: modelo,
    texto:
      "I've worked with countless core drilling contractors throughout my career, and DePaula Services is truly different. Their commitment to quality, professionalism, and reliability is unmatched. They're the kind of company you can trust to get the job done right every time.",
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
      "Having DePaula Services handle our core drilling makes our work much more efficient. It allows my crew to stay focused on plumbing while knowing the core drilling is in good hands. They're fast, reliable, and always get the job done right",
    nome: 'Afonso Garcia',
    empresa: 'Foreman RIT Plumbing contractor',
  },

  {
    foto: modelo4,
    texto:
      "Having DePaula Services handle our core drilling makes our work much more efficient. It allows my crew to stay focused on plumbing while knowing the core drilling is in good hands. They're fast, reliable, and always get the job done right",
    nome: 'Impacto core drilling',
    empresa: 'Impacto core drilling',
  },
])

function proximoComentario() {
  comentarioAtual.value = (comentarioAtual.value + 1) % comentarios.value.length
}

function comentarioAnterior() {
  comentarioAtual.value =
    (comentarioAtual.value - 1 + comentarios.value.length) % comentarios.value.length
}

function handleGlobalKeydown(event) {
  if (event.key === 'Escape') {
    closeMenu()
  }
}

onMounted(() => {
  window.addEventListener('keydown', handleGlobalKeydown)

  if (!window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
    revealObserver = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            entry.target.classList.add('is-visible')
            revealObserver.unobserve(entry.target)
          }
        })
      },
      { rootMargin: '0px 0px -12% 0px', threshold: 0.12 },
    )

    document.querySelectorAll('.reveal-item, .reveal-section').forEach((element) => {
      revealObserver.observe(element)
    })
  }
})

onBeforeUnmount(() => {
  window.removeEventListener('keydown', handleGlobalKeydown)
  revealObserver?.disconnect()
})
</script>
