<script setup lang="ts">
import TheWelcome from '../components/TheWelcome.vue'

function openLink(url: string) {
  window.open(url, '_blank')
}

// function downloadResume() {
//   const link = document.createElement('a')
//   link.href = 'path/to/your/resume.pdf'
//   link.download = 'Dallin_Resume.pdf'
//   link.click()
// }
</script>

<template>
  <main>
    <div class="container">
      <div class="half-section text-and-button">
        <div class="intro-text">
          <h3 class="hi-text">Hi!</h3>
          <h1 class="iam-text">I'm <span class="name-text">Dallin</span></h1>
          <h4 class="role-text">Software DevOps Engineer</h4>
        </div>
        <br />
        <div class="buttons-container">
          <button class="home-button button-rectangle-strong">
            <font-awesome-icon :icon="['far', 'circle-down']" class="icon-large" /> Resume
          </button>
          <button class="home-button button-rectangle-weak">
            <font-awesome-icon :icon="['far', 'envelope']" class="icon-large" /> Email
          </button>
        </div>
        <br />
        <div class="socials-container">
          <font-awesome-icon
            :icon="['fab', 'linkedin']"
            class="icon-social"
            @click="openLink('https://www.linkedin.com/in/dallin-stevens/')"
          />
          <font-awesome-icon
            :icon="['fab', 'github']"
            class="icon-social"
            @click="openLink('https://github.com/dkstevens2000')"
          />
          <font-awesome-icon
            :icon="['fab', 'medium']"
            class="icon-social"
            @click="openLink('https://medium.com/@stevens.dallin23')"
          />
          <font-awesome-icon
            :icon="['fab', 'goodreads']"
            class="icon-social"
            @click="openLink('https://www.goodreads.com/user/show/182246266-dallin-stevens')"
          />
        </div>
      </div>
      <div class="half-section image-container">
        <img src="../assets/DallinDude2.png" alt="Profile Picture" class="profile-image" />
        <!-- <div class="ellipse"></div> -->
        <!-- Add this div for the ellipse -->
      </div>
    </div>
    <!-- About This Website Section -->
    <section class="about-website-section full-width">
      <h2>About This Website</h2>
      <!-- Add more content here if needed -->
    </section>
    <!-- New Placeholder Section -->
    <section class="placeholder-section full-width">
      <h2>Placeholder</h2>
      <!-- Add more content here if needed -->
    </section>
  </main>
</template>

<style scoped>
.role-text {
  font-size: 20px;
}

.icon-social {
  font-size: 25px;
  padding: 5pt;
}

.icon-social:hover {
  cursor: pointer;
}

.hi-text {
  font-size: 20px;
}

.iam-text {
  font-size: 80px;
}

.name-text {
  color: var(--color-accent);
}

.container {
  display: flex;
  padding-bottom: 40px;
}

.half-section {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: left;
  position: relative; /* Add this to position the ellipse */
}

.image-container {
  position: relative; /* Ensure the ellipse is positioned relative to this container */
  user-select: none; /* Prevent text selection and caret appearance */
}

.profile-image {
  max-width: 100%;
  height: auto;
  position: relative; /* Ensure the image is positioned relative to the container */
  z-index: 1; /* Bring the image above the ellipse */
  pointer-events: none; /* Prevent the cursor from appearing on click */
  user-select: none; /* Prevent text selection and caret appearance */
}

.ellipse {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 500px; /* Adjust size as needed */
  height: 250px; /* Adjust size as needed */
  background-color: #fca15d;
  border-radius: 50%;
  transform: translate(-5%, 10%) rotate(15deg); /* Adjust position and tilt */
  z-index: 0; /* Place the ellipse behind the image */
}

.text-and-button {
  flex-direction: column;
  align-items: flex-start; /* Align items to the left */
  padding-left: 20px; /* Add padding to create space from the left */
  margin-left: 120px; /* Add margin to create space between image and text sections */
}

.intro-text {
  text-align: left; /* Align text to the left */
  width: 100%; /* Ensure the text block takes full width */
}

.buttons-container {
  display: flex;
  flex-direction: row;
  gap: 25px;
}

button {
  width: 140px; /* Set width to make it square */
  height: 60px; /* Set height to make it square */
  font-size: 16px; /* Adjust font size if needed */
  margin-top: 10px; /* Space between text and button */
  align-self: flex-start; /* Align button to the left */
  border-radius: 15px; /* Add rounded corners */
  display: inline-flex;
  align-items: center; /* Vertically center the content */
  justify-content: center; /* Horizontally center the content */
  gap: 8px; /* Add some space between the text and the icon */
}

.about-website-section {
  background-color: var(--color-background-soft);
  padding: 20px; /* Add padding for spacing */
  text-align: center; /* Center the text */
  width: 100vw; /* Extend the section to full viewport width */
  margin-left: calc(-50vw + 50%);
  height: 100vh;
}

.placeholder-section {
  background-color: var(--color-background-soft); /* Use the original color */
  padding: 20px; /* Add padding for spacing */
  text-align: center; /* Center the text */
  width: 100vw; /* Extend the section to full viewport width */
  margin-left: calc(-50vw + 50%); /* Center the section horizontally */
}
</style>
