<script>
export default {
  name: "FaqSection",
  data() {
    return {
      faqs: [
        {
          question: "What technologies do you specialize in?",
          answer:
            "I specialize in Python, JavaScript, SQL, and Cryptography. These technologies allow me to develop robust software solutions, create efficient databases, and ensure secure communication.",
        },
        {
          question: "How do you approach custom software development projects?",
          answer:
            "Each custom software development project starts with understanding the client's unique needs and goals. I then design and build tailored solutions using the latest technologies and best practices to ensure the software is scalable, efficient, and user-friendly.",
        },
        {
          question:
            "What is included in your Data Analysis and Visualization service?",
          answer:
            "The Data Analysis and Visualization service includes turning raw data into actionable insights through advanced analytical techniques and intuitive visualizations.",
        },
        {
          question:
            "Can you help with integrating third-party APIs into my existing systems?",
          answer:
            "Yes, I offer API Development & Integration services that include both building custom APIs and integrating existing third-party APIs into your systems.",
        },
        {
          question: "What do you offer in your Automation & Scripting service?",
          answer:
            "The Automation & Scripting service focuses on streamlining repetitive tasks and processes through custom scripts and automation solutions.",
        },
      ],
    };
  },
};
</script>

<template>
  <v-container class="faqSection" fluid>
    <v-row class="d-flex align-center justify-center" no-gutters>
      <v-col cols="12" md="8" class="text-center mb-5">
        <h2>Frequently Asked <strong>Questions</strong></h2>
        <p>
          Have questions? Here you'll find answers to some of the most common
          inquiries about my services. If you need more information or have
          specific questions, feel free to reach out!
        </p>
      </v-col>
      <v-col cols="12" md="8">
        <v-expansion-panels focusable inset>
          <v-expansion-panel v-for="(faq, index) in faqs" :key="index">
            <v-expansion-panel-title>
              <span class="num">{{ index + 1 }}.</span> {{ faq.question }}
            </v-expansion-panel-title>
            <v-expansion-panel-text>
              <p>{{ faq.answer }}</p>
            </v-expansion-panel-text>
          </v-expansion-panel>
        </v-expansion-panels>
      </v-col>
    </v-row>
  </v-container>
</template>

<style scoped>
.faqSection {
  padding: 20px; 
}

.text-center {
  text-align: center;
}

.num {
  font-weight: bold;
  margin-right: 5px;
}

@media (max-width: 600px) {
  .faqSection {
    padding: 10px; 
  }
}
</style>
