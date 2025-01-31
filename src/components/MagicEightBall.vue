<template>
  <div class="magic-eight-ball">
    <h1>Magic Eight Ball</h1>
    <input v-model="question" placeholder="Ask your question..." />
    <div class="buttons">
      <button @click="getAnswer('classic')">Classic</button>
      <button @click="getAnswer('sassy')">Sassy</button>
    </div>
    <p v-if="answer">{{ answer }}</p>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const question = ref('')
const answer = ref('')

const getAnswer = async (type: string) => {
  if (!question.value) {
    answer.value = 'Please ask a question!'
    return
  }

  const url = `https://wlqzjnzakh.execute-api.us-east-2.amazonaws.com/dev/${type}?question=${encodeURIComponent(question.value)}`
  console.log('the url iss', url)
  try {
    const response = await fetch(url)
    console.log('the response is', response)
    const data = await response.json()
    // answer.value = data.answer
  } catch (error) {
    answer.value = 'Error fetching answer. Please try again.'
  }
}
</script>

<style scoped>
.magic-eight-ball {
  text-align: center;
  margin-top: 2rem;
}

input {
  width: 80%;
  padding: 0.5rem;
  margin-bottom: 1rem;
}

.buttons {
  display: flex;
  justify-content: center;
  gap: 1rem;
}

button {
  padding: 0.5rem 1rem;
  cursor: pointer;
}

p {
  margin-top: 1rem;
  font-size: 1.2rem;
  font-weight: bold;
}
</style>