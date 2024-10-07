<script>
export default {
  name: "ResumeSection",
};
</script>

<template>
  <v-container id="resume" class="resume section">
    <!-- Section Title -->
    <v-row
      class="section-title"
      align="center"
      justify="center"
    >
      <v-col cols="12" md="8" class="text-center">
        <h2>Resume</h2>
        <p><em>Code. Create. Innovate.</em></p>
      </v-col>
    </v-row>

    <!-- Resume Content with Divider -->
    <v-row class="resume-content">
      <!-- Left Column: Summary and Education -->
      <v-col cols="12" md="5" data-aos="fade-up" data-aos-delay="100">
        <!-- Summary Section -->
        <h1 class="resume-title">Summary</h1>
        <div class="resume-item pb-0">
          <h4>Billy S. Terante</h4>
          <br>
          <p class="text-justify">
            <em>
              Results-driven IT professional with expertise in Python,
              JavaScript, SQL, and Cryptography. Adept at developing custom
              software solutions, designing efficient databases, and ensuring
              robust security measures.
            </em>
          </p>
          <br>
          <ul>
            <li>
              Purok 1B Ampayon, Butuan City, Agusan Del Norte, The Philippines
            </li>
            <li>+63 9876543212</li>
            <li>billlyterante77@outlook.com</li>
          </ul>
        </div>

        <!-- Education Section -->
        <h2 class="resume-title">Education</h2>
        <div class="resume-item">
          <h4>Bachelor Of Science In Information &amp; Technology</h4>
          <h5>August 2022 - Present</h5>
          <p><em>Caraga State University, Butuan City, The Philippines</em></p>
          <ul>
            <li>Academic Scholar (2022 - Present)</li>
          </ul>
        </div>

        <div class="resume-item">
          <h4>French Language</h4>
          <h5>August 2016 - July 2019</h5>
          <p><em>University Of Strasbourg, Strasbourg, France</em></p>
          <ul>
            <li>
              Achieved native speaker proficiency in French through advanced
              coursework and immersive learning.
            </li>
          </ul>
        </div>

        <div class="resume-item">
          <h4>High School</h4>
          <h5>August 2009 - July 2015</h5>
          <p><em>Westmills British School, Lagos, Nigeria</em></p>
          <ul>
            <li>Graduated with honors</li>
          </ul>
        </div>
      </v-col>

      <!-- Divider Line for Large Screens -->
      <v-col
        cols="12"
        md="2"
        class="d-none d-md-flex justify-center align-center"
      >
        <div class="divider-line"></div>
      </v-col>

      <!-- Right Column: Experience and Languages -->
      <v-col cols="12" md="5" data-aos="fade-up" data-aos-delay="200">
        <!-- Professional Experience Section -->
        <h1 class="resume-title">Professional Experience</h1>
        <div class="resume-item">
          <h4><em>Hack4Gov</em> | CyberKnights</h4>
          <h5>August 8, 2024</h5>
          <p><em>Almont Inland, Butuan City, The Philippines</em></p>
          <p class="text-justify">
            Participated in Hack4Gov as a member of the CyberKnights team, where
            I contributed to developing innovative solutions for
            government-related challenges within a 24-hour hackathon.
          </p>
        </div>

        <div class="resume-item">
          <h4><em>Olivier</em> | Co-Owner</h4>
          <h5>July 2023 - July 2024</h5>
          <p><em>Ampayon, Butuan City, The Philippines</em></p>
          <p class="text-justify">
            As a co-owner in a restaurant, I shared ownership responsibilities
            and decision-making authority.
          </p>
        </div>

        <div class="resume-item">
          <h4><em>Oxfam</em> | Shop Clerk</h4>
          <h5>April 2017 - August 2017</h5>
          <p><em>Strasbourg, France</em></p>
          <p class="text-justify">
            As a shop clerk for a non-governmental organization, I provided
            excellent customer service, assisted customers with their purchases,
            maintained inventory, and handled transactions.
          </p>
        </div>

        <div class="resume-item">
          <h4>
            <em>French International School</em> | Assistant French Teacher
          </h4>
          <h5>April 2016 - July 2016</h5>
          <p><em>Kaduna, Nigeria</em></p>
          <p class="text-justify">
            As an assistant French teacher, I supported the lead teacher in
            delivering lessons, helped students with their language skills, and
            provided one-on-one tutoring.
          </p>
        </div>

        <!-- Languages Section -->
        <h3 class="resume-title">Languages</h3>
        <div class="resume-item">
          <ul>
            <li>English - English as a Second Language</li>
            <li>French - C2 in French Proficiency</li>
            <li>Visayan Dialect - Mother Tongue</li>
          </ul>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<style scoped>
body {
  overflow-x: hidden;
}

*,
*::before,
*::after {
  box-sizing: border-box;
}

.resume {
  padding: 110px 5px 40px 5px;
  margin: 0 auto;
  max-width: auto;
  overflow-x: hidden; 
}

@media (max-width: 1024px) {
  .resume{
    padding-top: 110px;
  }
}

@media (max-width: 768px) {
  .resume {
    padding-top: 110px;
    padding-bottom: 20px;
    border-width: 3px;
  }

  .resume p {
    padding: 0px 5px 0px 5px;
  }

  .divider-line {
    display: none; 
  }
}

@media (max-width: 480px) {
  .resume{
    padding-top: 110px;
  }
}

.resume-title {
  margin-top: 24px;
  font-weight: bold;
}

.resume-item {
  margin-bottom: 16px;
}

.text-justify {
  text-align: justify;
}

.divider-line {
  width: 2px;
  height: 100%;
  background-color: blue;
}

ul li {
  margin-left: 20px;
}
</style>
