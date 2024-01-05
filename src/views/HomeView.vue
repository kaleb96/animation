<script setup>
import { ref } from 'vue'

const names = ref(['Selena Damo', 'Kevin JohnStone']);
const nameInput = ref('');
const addInvitee = () => {
  names.value.unshift(nameInput.value);
  nameInput.value = '';
}
// const showText = ref(true);
// const showGreet = ref(true);
</script>

<template>
    <main>
        <!-- <Transition name="bg">
          <h1 v-if="showText">Hello World</h1>
        </Transition> -->
        <!-- <div class="container">
          <Transition name="fade">
            <h1 v-if="showText">Hello World</h1>
            <h1 v-if="showGreet">Hello World</h1>
            <h1 v-else>GoodBye World</h1>
          </Transition>
        </div>-->
        <!-- <button @click="showText = !showText">toggle</button> -->
        <!-- <button @click="showGreet = !showGreet">toggle</button> -->
        <div class="container">
          <input 
            type="text" 
            placeholder="Add person to invite..."
            v-model="nameInput"
            @keypress.enter="addInvitee"
            >
            <ul>
              <TransitionGroup name="invitees">
                <li v-for="name in names" :key="name">{{ name }}</li>
              </TransitionGroup>
              <!-- <li>Selena Damo</li> -->
            </ul>
        </div>
    </main>
</template>

<style scoped>
/* .bg-enter-from {
  background-color: yellow;
}

.bg-enter-to {
  background-color : blue;
}

.bg-enter-active {
  transition: all 5s ease;
} */
/* .fade-enter-from {
  opacity: 0
} */

/* .fade-enter-to { 
  opacity: 1 default value
} */

/* .fade-enter-active {
  transition: all 1s ease;
} */
/* .fade-leave-from {
  opacity: 1 default value
} */

/* .fade-leave-to {
  opacity: 0
}

.fade-leave-active {
  transition: all 1s ease;
}

.container {
  position: relative;
}

h1 {
  position: absolute;
}

button {
  margin-top: 60px;
} */

.container {
  max-width: 300px;
  margin: 0 auto;
}

.container input {
  width: 100%;
  border-radius: 5px;
  border: 1px solid rgba(128,128,128, 0.13);
  padding: 10px;
  margin-bottom: 20px;
  box-shadow: 1px 1px 10px rgba(0,0,0,0.12);
}

ul {
  display: inline;
  list-style: none;
  margin: 0px;
  padding: 0px;
}

li {
  list-style: none;
  width: 300px;
  border-radius: 5px;
  padding: 5px 10px;
  margin-top: 10px;
  box-shadow: 1px 1px 10px rgba(0,0,0,0.12);
  text-align: center;
  cursor: pointer;
}

/* Transition Group */
.invitees-enter-from {
  opacity: 0;
  transform: scale(0.5);
}

.invitees-enter-to {
  opacity: 1;
  transform: scale(1);
}

.invitees-leave-active {
  transition: all 0.8s ease;
  position: absolute;
}

.invitees-move {
  transition: all 0.8 ease;
}
</style>