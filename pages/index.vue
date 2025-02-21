<template>
  <div class="homebg bg-cover">
    <div class="text-left">
      <h1 class="text-4xl font-bold">LION WITH A MIC</h1>
      <p class="text-gray-400">Welcome to an elite offering</p>
      <p class="text-gray-400">Unique luxury and experiences</p>
    </div>
    <button class="cta-button uppercase text-2xl px-8 py-4 rounded-full">
      CALL TO ACTION
    </button>
  </div>
</template>

<style scoped>
.homebg {
  background-image: url("/assets/images/homebg.png"); /* Update with your image path */
  height: 80vh;
  display: flex;
  flex-direction: column;
  justify-content: center; /* Center content vertically */
  align-items: center; /* Center content horizontally */
  padding: 20px;
  color: white;
  position: relative; /* Allow absolute positioning of children */
}

h1 {
  color: #dd9f2c;
}

.text-left {
  position: absolute;
  top: 50%;
  left: 20px; /* Adjust as needed */
  transform: translateY(-50%); /* Center vertically */
}

.cta-button {
  background-color: #a96f05;
  color: white;
  border: none;
  cursor: pointer;
  position: absolute;
  bottom: 15vh; /* Adjust this value to move the button up */
  transition: all 0.3s ease-in-out;
}

.cta-button:hover {
  background-color: #c0810d;
}
</style>
