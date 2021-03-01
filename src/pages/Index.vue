<template>
  <Layout>
    <About />
    <Project />
    <Education />
    <Contact />
  </Layout>
</template>

<script>
import About from "@/components/About"
import Project from "@/components/Project"
import Education from "@/components/Education"
import Contact from "@/components/Contact"

export default {
  metaInfo: {
    title: 'Suho Kang'
  },
  components: {
    About,
    Project,
    Education,
    Contact
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
