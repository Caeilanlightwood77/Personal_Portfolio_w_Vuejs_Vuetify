<script>
export default {
  name: "ContactSection",
  data() {
    return {
      contactInfo: [
        {
          title: "Address",
          content:
            "Purok 1B Ampayon, Butuan City, Agusan Del Norte, The Philippines",
          icon: "mdi-map-marker", // Use Material Design Icons
        },
        {
          title: "Call Me",
          content: "+63 9876543212",
          icon: "mdi-phone",
        },
        {
          title: "Email Me",
          content: "billlyterante77@outlook.com",
          icon: "mdi-email",
        },
      ],
      formData: {
        name: "",
        email: "",
        subject: "",
        message: "",
      },
      loading: false,
      errorMessage: false,
      sentMessage: false,
    };
  },
  methods: {
    submitForm() {
      this.loading = true;
      this.errorMessage = false;
      this.sentMessage = false;

      // Simulating an API call
      setTimeout(() => {
        // Replace this with an actual API call
        const isSuccess = true; // Simulate success or failure

        if (isSuccess) {
          this.sentMessage = true;
        } else {
          this.errorMessage = true;
        }
        this.loading = false;
      }, 2000);
    },
  },
};
</script>

<template>
  <v-container id="contact" class="contact section" fluid>
    <!-- Section Title -->
    <v-row class="section-title" data-aos="fade-up" justify="center">
      <v-col cols="12" md="8" class="text-center">
        <h2 class="display-2 font-weight-bold">Contact</h2>
        <p class="subtitle-1" style="text-align: justify">
          Get in touch! Whether you have a question, need more information, or
          want to discuss a potential project, I'm here to help. Reach out using
          the contact form below or through my email, and I'll get back to you
          as soon as possible.
        </p>
      </v-col>
    </v-row>

    <v-row
      class="info-wrap"
      data-aos="fade-up"
      data-aos-delay="100"
      justify="center"
    >
      <v-col v-for="(item, index) in contactInfo" :key="index" cols="12" md="4">
        <v-card
          class="d-flex align-items-start pa-4 rounded-lg elevation-2"
          min-height="100"
        >
          <v-icon class="mr-3" large>{{ item.icon }}</v-icon>
          <div>
            <h3 class="headline mb-0">{{ item.title }}</h3>
            <p class="body-2 mb-0">{{ item.content }}</p>
          </div>
        </v-card>
      </v-col>
    </v-row>

    <v-form @submit.prevent="submitForm" class="php-email-form mt-5">
      <v-row class="gy-4" justify="center">
        <v-col cols="12" md="6">
          <v-text-field
            v-model="formData.name"
            label="Your Name"
            outlined
            required
            color="primary"
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="6">
          <v-text-field
            v-model="formData.email"
            label="Your Email"
            outlined
            required
            color="primary"
          ></v-text-field>
        </v-col>

        <v-col cols="12">
          <v-text-field
            v-model="formData.subject"
            label="Subject"
            outlined
            required
            color="primary"
          ></v-text-field>
        </v-col>

        <v-col cols="12">
          <v-textarea
            v-model="formData.message"
            label="Message"
            rows="6"
            outlined
            required
            color="primary"
          ></v-textarea>
        </v-col>

        <v-col cols="12" class="text-center">
          <v-btn type="submit" color="primary" class="mt-3">Send Message</v-btn>
          <v-alert v-if="loading" type="info" class="mt-2" dismissible>
            Loading...
          </v-alert>
          <v-alert v-if="errorMessage" type="error" class="mt-2" dismissible>
            An error occurred. Please try again.
          </v-alert>
          <v-alert v-if="sentMessage" type="success" class="mt-2" dismissible>
            Your message has been sent. Thank you!
          </v-alert>
        </v-col>
      </v-row>
    </v-form>
  </v-container>
</template>

<style scoped>
.contact.section {
  padding: 110px 10px 50px 10px;
  background-color: #f9f9f9;
  border-radius: 8px;
}

.section-title h2 {
  font-weight: bold;
  color: #333;
}

.info-wrap {
  margin: 30px 0;
}

.v-card {
  transition: box-shadow 0.3s ease;
  display: flex;
  align-items: center; /* Center items vertically */
  height: 100%; /* Ensures all cards are the same height */
}

.v-card:hover {
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

.v-icon {
  font-size: 36px; /* Increase icon size for better visibility */
}
</style>
