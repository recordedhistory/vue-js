<template>
  <div class="contact">
    <h1>Contact</h1>
    <ContactForm />
  </div>
</template>


<script>
import ContactForm from '@/components/ContactForm.vue'

export default {
    name: 'Contact',
    components: { ContactForm }
}

</script>
