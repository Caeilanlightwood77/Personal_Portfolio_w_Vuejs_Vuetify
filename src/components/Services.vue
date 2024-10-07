<script>
export default {
  name: "MyServices",
  data() {
    return {
      services: [
        {
          icon: "mdi-chart-line",
          title: "Data Analysis & Visualization",
          description:
            "By leveraging advanced analytical techniques and intuitive visualization tools, I help clients uncover trends, patterns, and actionable information. Whether you need to make data-driven decisions or present complex data in a clear, visually engaging way, I provide solutions that make your data work for you.",
        },
        {
          icon: "mdi-connection",
          title: "API Development & Integration",
          description:
            "My API Development & Integration service focuses on creating seamless connections between systems, enabling smooth data exchange and enhanced functionality. Whether you're looking to build a custom API from scratch or integrate existing third-party APIs into your application, I ensure reliable, secure, and efficient communication between your software components.",
        },
        {
          icon: "mdi-pencil-box-outline",
          title: "Custom Software Development",
          description:
            "The Custom Software Development service provides tailored solutions designed to meet specific business needs. By utilizing the latest technologies and best practices, this service delivers robust, scalable, and user-friendly applications that align perfectly with the unique requirements of each project.",
        },
        {
          icon: "mdi-database",
          title: "Database Design & Management",
          description:
            "The Database Design & Management service offers expert solutions for creating, optimizing, and maintaining databases. This service ensures efficient data storage, retrieval, and management, tailored to support the specific needs of any application.",
        },
        {
          icon: "mdi-security",
          title: "Cryptography & Security Solutions",
          description:
            "My Cryptography & Security Solutions service is dedicated to protecting your data and ensuring secure communication. I implement advanced encryption techniques, secure protocols, and data protection strategies tailored to your specific needs.",
        },
        {
          icon: "mdi-code-brackets",
          title: "Automation & Scripting",
          description:
            "The Automation & Scripting service streamlines repetitive tasks and processes through custom scripts and automation solutions. By leveraging scripting languages like Python, this service enhances efficiency and reduces manual effort, allowing businesses to focus on more strategic activities.",
        },
      ],
    };
  },
};
</script>

<template>
  <section id="services" class="services section">
    <v-container class="section-title">
      <v-fade-transition>
        <h2>Services</h2>
      </v-fade-transition>
      <v-fade-transition>
        <p><em>Empowering Solutions, One Line of Code at a Time.</em></p>
      </v-fade-transition>
    </v-container>

    <v-container>
      <v-row class="gy-4">
        <v-col
          cols="12"
          md="6"
          lg="4"
          v-for="(service, index) in services"
          :key="index"
          :data-aos-delay="100 * (index + 1)"
        >
          <v-fade-transition>
            <v-card class="service-item" elevation="3">
              <v-sheet class="icon-container">
                <v-icon size="40" class="mr-2">{{ service.icon }}</v-icon>
              </v-sheet>
              <v-card-title class="text-truncate">{{
                service.title
              }}</v-card-title>
              <v-card-text class="text-justify">{{
                service.description
              }}</v-card-text>
              <v-card-actions>
                <v-btn class="stretched-link" text>Learn More</v-btn>
              </v-card-actions>
            </v-card>
          </v-fade-transition>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<style scoped>
.services.section {
  padding: 40px 0;
  padding-top: 110px;
}

.section-title {
  text-align: center;
}

.service-item {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  min-height: 300px;
  padding: 20px;
}

.service-item .v-icon {
  color: #42a5f5;
}

.icon-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 60px;
}

.text-truncate {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.v-card-title {
  font-weight: bold;
  margin-bottom: 10px;
  text-align: center;
}

.v-card-actions {
  display: flex;
  justify-content: center;
}
</style>
