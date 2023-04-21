<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear()
    }
  }
}
</script>

<template>
    <footer class="footer">
      <div class="container">
        <p>&copy; {{ currentYear }} Created by Vahid</p>
      </div>
    </footer>
</template>
  
  
<style scoped>
  .footer {
    background-color: #f8f8f8;
    padding: 20px;
    text-align: center;
    margin-top: 10% ;
  }
</style>
  