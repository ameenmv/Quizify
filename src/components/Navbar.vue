<template>
  <section class="bg-[var(--primary)] text-[var(--white)] py-3">
    <div class="containerr">
      <div class="flex justify-between items-center">
        <p class="font-medium text-xl">Home</p>
        <h1 class="font-bold text-2xl">Quizify</h1>
        <div class="flex justify-center items-center">
          <div class="btn1">Signup</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.btn1 {
  background-color: var(--secondary);
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 8px;
  padding: 5px 15px;
  font-weight: 500;
}
</style>
