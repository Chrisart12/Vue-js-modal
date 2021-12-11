<template>
    <h1>{{ title }} </h1>

    <div v-if="showModal">
        <Modal :header="header" :lastname="lastname" theme="sale" @close="toggleModal"/>
    </div>
    <button @click.alt="toggleModal">Show Modal</button>

    <SlotElt>
      <template v-slot:links>
        <p><a href="https://wesead.dev.heliop.com" target="_blank" rel="noopener noreferrer">wesead.heliop.com</a></p>
        <p><a href="https://esa-foad.fr" target="_blank" rel="noopener noreferrer">esa-foad.fr</a></p>
      </template>
      <h1>Mon nom est Issifou</h1>
      <p>Vous êtes ici chez vous.</p>
    </SlotElt>
    
    <teleport to=".modals" v-if="showModalTwo">
      <ModalTwo @close="toggleModalTwo">
        <h1>Sign up to the newletter</h1>
        <p>For updates and promo codes!</p>
      </ModalTwo>
    </teleport>
    <button @click="toggleModalTwo">Open modal two</button>
</template>

<script>

import Modal from './components/Modal.vue'
import SlotElt from './components/SlotElt.vue'
import ModalTwo from './components/ModalTwo.vue'

export default {
    components: { Modal, SlotElt },
  
data() {
  return { 
    title: 'Je suis ici',
    header: "Je suis le modal",
    lastname: "Issifou",
    showModal: false,
    showModalTwo: false
  }
},

methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
     toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    },

  }

}
</script>

<style>
#app, .modal {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
