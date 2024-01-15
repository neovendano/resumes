<template>
  <div class="cv">
    <h2>Personal Information</h2>
    <p>Name: {{ resume.name }}</p>
    <p>Surname: {{ resume.surname }}</p>
    <p>Contacts: {{ resume.contacts }}</p>

    <h2>Education</h2>
    <p>{{ resume.education }}</p>

    <h2>Work Experience</h2>
    <p>{{ resume.workExperience }}</p>

    <h2>Skills</h2>
    <p>{{ resume.skills }}</p>

    <h2>Additional Sections</h2>
    <p>{{ resume.additionalSections }}</p>
  </div>
</template>

<script>
export default {
  name: 'ResumeView',
  props: {
    resume: {
      type: Object,
      required: true
    }
  }
}
</script>

<style>
.cv {
  border: dodgerblue 1px solid;
  margin: 5px;
}
</style>