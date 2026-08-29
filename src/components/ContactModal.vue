<template>
  <Teleport to="body">
    <div
      v-if="open"
      class="contact-options"
      role="presentation"
      @click.self="emitClose"
    >
      <div
        ref="dialogRef"
        class="contact-box"
        role="dialog"
        aria-modal="true"
        aria-labelledby="contact-modal-title"
        aria-describedby="contact-modal-description"
        tabindex="-1"
        @keydown="handleDialogKeydown"
      >
        <button
          ref="closeButtonRef"
          class="close-contact"
          type="button"
          @click="emitClose"
          aria-label="Close contact options"
        >
          ×
        </button>

        <h2 id="contact-modal-title">How would you like to contact us?</h2>

        <p id="contact-modal-description">Choose your preferred way to request a free quote.</p>

        <a
          href="https://wa.me/18623441728?text=Hello!%20I%20would%20like%20to%20get%20a%20free%20quote."
          target="_blank"
          rel="noopener noreferrer"
          class="contact-option whatsapp"
        >
          WhatsApp
        </a>

        <a href="sms:+18623441728" class="contact-option sms">Text Message</a>
      </div>
    </div>
  </Teleport>
</template>

<script setup>
import { nextTick, onBeforeUnmount, ref, watch } from 'vue'

const props = defineProps({
  open: {
    type: Boolean,
    required: true,
  },
})

const emit = defineEmits(['close'])

const dialogRef = ref(null)
const closeButtonRef = ref(null)
let previouslyFocusedElement = null

const emitClose = () => {
  emit('close')
}

const getFocusableElements = () =>
  Array.from(
    dialogRef.value?.querySelectorAll(
      'a[href], button:not([disabled]), textarea, input, select, [tabindex]:not([tabindex="-1"])',
    ) ?? [],
  )

const handleDialogKeydown = (event) => {
  if (event.key === 'Escape') {
    event.preventDefault()
    emitClose()
    return
  }

  if (event.key !== 'Tab') return

  const focusableElements = getFocusableElements()
  const firstElement = focusableElements[0]
  const lastElement = focusableElements[focusableElements.length - 1]

  if (!firstElement || !lastElement) return

  if (event.shiftKey && document.activeElement === firstElement) {
    event.preventDefault()
    lastElement.focus()
  } else if (!event.shiftKey && document.activeElement === lastElement) {
    event.preventDefault()
    firstElement.focus()
  }
}

const handleDocumentKeydown = (event) => {
  if (event.key === 'Escape' && props.open) {
    event.preventDefault()
    emitClose()
  }
}

watch(
  () => props.open,
  async (isOpen) => {
    if (isOpen) {
      previouslyFocusedElement = document.activeElement
      document.body.classList.add('modal-open')
      document.addEventListener('keydown', handleDocumentKeydown)
      await nextTick()
      closeButtonRef.value?.focus()
    } else {
      document.body.classList.remove('modal-open')
      document.removeEventListener('keydown', handleDocumentKeydown)
      previouslyFocusedElement?.focus?.()
    }
  },
)

onBeforeUnmount(() => {
  document.body.classList.remove('modal-open')
  document.removeEventListener('keydown', handleDocumentKeydown)
})
</script>
