<template>
  <section class="h-screen w-full text">
    <Navbar />
    <div class="landing bg-[var(--bg)] w-full h-full relative">
      <div
        class="containerr h-full flex flex-col justify-center items-center gap-10"
      >
        <img
          src="../assets/imgs/Vector.png"
          class="absolute left-0 top-0 w-full h-72"
          alt=""
        />
        <img
          src="../assets/imgs/Pattern.png"
          class="absolute left-0 bottom-0 w-full h-72"
          alt=""
        />
        <h1 class="text-6xl font-bold text-[var(--primary)]">
          Learn, Quiz,<span class="gradient-text"> Earn Rewards</span>
        </h1>
        <p
          class="text-[var(--secondary)] text-xl font-medium max-w-[600px] text-center"
        >
          Join thousands of students and teachers on the ultimate quiz platform.
          Test your knowledge, compete with peers, and win exciting rewards
        </p>
        <div class="flex justify-center items-center gap-8">
          <div class="btn1 text-white !px-8 !py-4 !rounded-2xl">Get Started</div>
          <div class="btn1 !bg-white !bg-none text-black !px-8 !py-4 !rounded-2xl">Explore Quizzes</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Navbar from "./Navbar.vue";

export default {
  components: {
    Navbar,
  },
};
</script>

<style lang="scss" scoped>

</style>
