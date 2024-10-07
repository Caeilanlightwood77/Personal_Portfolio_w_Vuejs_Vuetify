<script>
export default {
  name: "AboutMe",
  data() {
    return {
      profileImage: require("@/assets/img/Me/1st_Edit.jpg"),
      skills: [
        { name: "Python", value: 100 },
        { name: "JavaScript", value: 80 },
        { name: "Cryptography", value: 80 },
        { name: "SQL", value: 85 },
      ],
      isVisible: false,
    };
  },
  mounted() {
    const options = {
      root: null,
      rootMargin: "0px",
      threshold: 0.1,
    };

    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          this.isVisible = true;
          observer.unobserve(entry.target);
        }
      });
    }, options);

    this.$refs.progressBars.forEach((bar) => {
      observer.observe(bar);
    });
  },
};
</script>

<template>
  <div class="about-container" id="about">
    <!-- Left Section -->
    <div class="left-section">
      <img :src="profileImage" alt="Profile Image" class="profile-image" />
      <div class="personal-info">
        <p><strong>Name:</strong> Billy Terante</p>
        <p><strong>Profile:</strong> Software Developer / Cryptanalyst</p>
        <p><strong>Email:</strong> billyterante77@outlook.com</p>
        <p><strong>Phone:</strong> +63 9876543212</p>
      </div>
    </div>

    <!-- Right Section -->
    <div class="right-section">
      <h2>About Me</h2>
      <p>
        I'm a passionate tech enthusiast with a strong background in Python,
        JavaScript, SQL, and Cryptography. I thrive on solving complex problems
        and enjoy exploring new technologies. My expertise in these areas allows
        me to build efficient and secure solutions, and I'm always eager to
        learn more and expand my skill set.
      </p>
      <br>
      <p>
        Beyond my technical abilities, I'm driven by a genuine curiosity about
        how things work. I love diving deep into challenges, whether it's
        optimizing code, designing databases, or enhancing security measures. My
        commitment to continuous learning keeps me at the forefront of the
        ever-evolving tech landscape.
      </p>
      <br>
      <p>
        In my free time, I find balance by engaging in sports and photography.
        Sports keep me active and focused, while photography allows me to
        capture the beauty of the world around me. These hobbies not only
        provide a creative outlet but also inspire me to approach my work with a
        fresh and dynamic perspective.
      </p>
      <br>
      <h3>Skills</h3>
      <div
        v-for="(skill, index) in skills"
        :key="index"
        class="progress"
        ref="progressBars"
      >
        <span class="skill"
          ><span>{{ skill.name }}</span>
          <i class="val">{{ skill.value }}%</i></span
        >
        <div class="progress-bar-wrap">
          <div
            class="progress-bar"
            role="progressbar"
            :style="{ width: isVisible ? skill.value + '%' : '0%' }"
            :class="{ animate: isVisible }"
            aria-valuenow="skill.value"
            aria-valuemin="0"
            aria-valuemax="100"
          ></div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  padding: 20px;
  padding-top: 110px;
  margin: 0px 30px 0px;
}

.left-section {
  flex: 1;
  max-width: 300px;
  text-align: center;
}

.profile-image {
  width: 100%;
  height: auto;
  border-radius: 8px;
}

.personal-info {
  text-align: left;
  margin-top: 20px;
}

.right-section {
  flex: 2; /* Allow to grow larger */
  min-width: 300px; /* Ensure it doesn't get too small */
}

.right-section h2,
.right-section h3 {
  color: #333;
  border-bottom: 2px solid #007bff;
  padding-bottom: 5px;
}

.right-section p {
  text-align: justify;
  font-size: large;
}

.progress {
  margin-top: 10px;
}

.skill {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.val {
  font-weight: bold;
}

.progress-bar-wrap {
  background-color: #e0e0e0;
  border-radius: 5px;
  overflow: hidden;
  height: 10px;
}

.progress-bar {
  height: 100%;
  background-color: #007bff;
  transition: width 0.5s;
  width: 0%;
}

.progress-bar.animate {
  transition: width 1s;
}

@media (max-width: 1024px) {
  .about-container {
    padding-top: 110px;
  }
}

@media (max-width: 768px) {
  .about-container {
    flex-direction: column;
    padding-top: 110px;
  }

  .left-section {
    margin-bottom: 20px;
  }
}

@media (max-width: 480px) {
  .about-container {
    padding-top: 110px;
  }
}

  
</style>
