<template>
  <div id="app">
    <ResumeForm @submit="addResume" />
    <ResumeView v-for="resume in resumes" :key="resume.id" :resume="resume" />
  </div>
</template>

<script>
import ResumeForm from './components/ResumeForm.vue'
import ResumeView from './components/ResumeView.vue'

export default {
  name: 'App',
  components: {
    ResumeForm,
    ResumeView
  },
  data() {
    return {
      resumes: []
    }
  },
  methods: {
    addResume(resume) {
      this.resumes.push(resume)
      localStorage.setItem('resumes', JSON.stringify(this.resumes))
    }
  },
  created() {
    localStorage.clear();
    const resumes = localStorage.getItem('resumes')
    if (resumes) {
      this.resumes = JSON.parse(resumes).filter(resume => resume !== null)
    }
  }
}
</script>




