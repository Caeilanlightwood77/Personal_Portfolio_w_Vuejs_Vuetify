<script>
export default{
  name: "AppFooter",
  data() {
    return {
      links: ['https://www.facebook.com/caeilan.lightwood', 'https://www.linkedin.com/in/billy-terante-b0304b307', ] 
    }
  }
}
</script>

<template>
  <v-container class="accent-background text-center py-4" fluid>
    <div class="copyright">
      <p>
        © <span>Copyright</span>
        <strong class="px-1 sitename">Billy S. Terante</strong>
        <span>All Rights Reserved</span>
      </p>
    </div>
    <div class="social-links">
      <v-btn icon href="#" aria-label="Twitter">
        <v-icon>
          <i class="bi bi-twitter"></i>
          <!-- Changed to bi-twitter -->
        </v-icon>
      </v-btn>
      <v-btn
        icon
        href="https://www.facebook.com/caeilan.lightwood"
        aria-label="Facebook"
      >
        <v-icon>
          <i class="bi bi-facebook"></i>
          <!-- Changed to bi-facebook -->
        </v-icon>
      </v-btn>
      <v-btn icon href="#" aria-label="Instagram">
        <v-icon>
          <i class="bi bi-instagram"></i>
          <!-- Changed to bi-instagram -->
        </v-icon>
      </v-btn>
      <v-btn
        icon
        href="https://www.linkedin.com/in/billy-terante-b0304b307"
        aria-label="LinkedIn"
      >
        <v-icon>
          <i class="bi bi-linkedin"></i>
          <!-- Changed to bi-linkedin -->
        </v-icon>
      </v-btn>
    </div>
  </v-container>
</template>

<style scoped>
.accent-background{
  background-color: #0077FF;
}

</style>