<template>
  <form @submit.prevent="submit">
    <h2>Personal Information</h2>
    <div>
      <label for="name">Name:</label>
      <input id="name" v-model="resume.name" type="text" required>
    </div>
    <div>
      <label for="surname">Surname:</label>
      <input id="surname" v-model="resume.surname" type="text" required>
    </div>
    <div>
      <label for="contacts">Contacts:</label>
      <input id="contacts" v-model="resume.contacts" type="text" required>
    </div>

    <h2>Education</h2>
    <div>
      <label for="education">Education:</label>
      <textarea id="education" v-model="resume.education" required></textarea>
    </div>

    <h2>Work Experience</h2>
    <div>
      <label for="workExperience">Work Experience:</label>
      <textarea id="workExperience" v-model="resume.workExperience" required></textarea>
    </div>

    <h2>Skills</h2>
    <div>
      <label for="skills">Skills:</label>
      <textarea id="skills" v-model="resume.skills" required></textarea>
    </div>

    <h2>Additional Sections</h2>
    <div>
      <label for="additionalSections">Additional Sections:</label>
      <textarea id="additionalSections" v-model="resume.additionalSections"></textarea>
    </div>

    <button type="submit">Submit</button>
  </form>
</template>

<script>
export default {
  name: 'ResumeForm',
  data() {
    return {
      resume: {
        id: 0,
        name: '',
        surname: '',
        contacts: '',
        education: '',
        workExperience: '',
        skills: '',
        additionalSections: ''
      }
    }
  },
  methods: {
    submit() {
      this.$emit('submit', this.resume)
      this.resume = {
        id: this.id + 1,
        name: '',
        surname: '',
        contacts: '',
        education: '',
        workExperience: '',
        skills: '',
        additionalSections: ''
      }
    }
  }
}
</script>
