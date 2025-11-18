<template>
  <div class="timeline-container">
    <div class="timeline-line"></div>

    <div
      v-for="({ year, duration, title, industry, location, description, tags}, index) in timeline"
      :key="index"
      class="timeline-entry"
      :class="index % 2 === 0 ? 'left' : 'right'"
    >
      <div class="timeline-content">
        <div class="timeline-year">
          <h2>{{ year }} <span>{{ duration }}</span></h2>
        </div>
        <h3 class="timeline-title">{{ title }}</h3>
        <p class="industry">{{ industry }} • {{ location }}</p>
        <p class="description">{{ description }}</p>

        <div class="tags">
          <span v-for="(tag, j) in tags" :key="j" class="tag">{{ tag }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const timeline = ref([
  {
    year: '2026',
    duration: 'Present',
    title: 'Student',
    industry: 'University',
    location: 'Germany, Berlin',
    description: 'Studying Computer Science in IU International University of Applied Sciences (IU)',

    tags: ['Math', 'English', 'German', 'Team building']
  },
  {
    year: '2023',
    duration: '2 years',
    title: 'Student',
    industry: 'University',
    location: 'Iran',
    description: 'Studying Computer Enginering in Eqbal University of Mashhad',

    tags: ['Math', 'Physics', 'C++', 'Java']
  },
   {
    year: '2022',
    duration: '3 years',
    title: 'Full Stack Developer',
    industry: 'Website Design',
    location: 'Iran',
    description: 'Worked with a company to design and create websites for customers.',

    tags: ['WordPress', 'PHP', 'JavaScript','CSS']
  },
  {
    year: '2020',
    duration: '3 years',
    title: 'Student',
    industry: 'High School',
    location: 'Iran',
    description: 'Started my educational journey with early exposure to technology.',

    tags: ['Math', 'Basic Computing', 'Problem Solving']
  }
]);
</script>

<style scoped>
.timeline-container {
  position: relative;
  background-color: #19181a;
  color: #fff;
  font-family: 'Segoe UI', sans-serif;
  padding: 6rem 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;

  left: 50%;
  transform: translateX(-50%);
  width: 100vw;
  box-sizing: border-box;
}

.light-mode .timeline-container {
  background-color: #fbfafb;
  color: #0d0d0d;
}

.timeline-line {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 50%;
  width: 2px;
  background: linear-gradient(to bottom, #ff0080, #7928ca);
  box-shadow: 0 0 20px rgba(255, 0, 128, 0.7);
  transform: translateX(-50%);
  z-index: 0;
}

.timeline-entry {
  width: 100%;
  max-width: 1000px;
  padding: 2rem 0;
  display: flex;
  position: relative;
  z-index: 2;
}

.timeline-entry.left {
  justify-content: flex-end;
}

.timeline-entry.right {
  justify-content: flex-start;
}

.timeline-content {
  background: rgba(255, 255, 255, 0.03);
  backdrop-filter: blur(6px);
  padding: 1.75rem;
  border-radius: 1rem;
  border: 1px solid rgba(255, 255, 255, 0.08);
  box-shadow: 0 0 20px rgba(255, 0, 128, 0.2);
  max-width: 460px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.timeline-content:hover {
  transform: translateY(-4px);
  box-shadow: 0 0 30px rgba(255, 94, 0, 0.6);
}

.timeline-year h2 {
  font-size: 2rem;
  font-weight: 700;
  color: #00ffff;
  text-shadow: 0 0 20px #00ffff;
  margin: 0;
}

.timeline-year span {
  font-size: 0.875rem;
  color: #aaa;
  margin-left: 0.25rem;
}

.timeline-title {
  font-size: 1.3rem;
  margin: 0.75rem 0 0.3rem;
  position: relative;
  display: inline-block;
  transition: color 0.3s ease;
}

.timeline-title::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  left: 0;
  bottom: -4px;
  background: #ff6a00;
  transition: width 0.3s ease;
}

.timeline-content:hover .timeline-title {
  color: #ff6a00;
}

.timeline-content:hover .timeline-title::after {
  width: 100%;
}

.industry {
  color: #aaa;
  font-size: 0.85rem;
  font-weight: bold;
  margin-bottom: 0.75rem;
}

.description {
  font-style: italic;
  margin-bottom: 0.5rem;
  color: #ddd;
}

.light-mode .description,
.light-mode .industry {
  color: #0d0d0d;
}

ul {
  list-style-type: '→ ';
  padding-left: 1.5rem;
  margin-bottom: 0.75rem;
  color: #ccc;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tag {
  background: linear-gradient(to right, #7928ca, #ff0080);
  padding: 0.35rem 0.75rem;
  border-radius: 999px;
  font-size: 0.75rem;
  color: white;
  box-shadow: 0 0 10px rgba(255, 0, 128, 0.4);
}

.timeline-entry:nth-child(2) .timeline-year h2 {
  color: #11b680;
  text-shadow: 0 0 20px #11b680;
}
.timeline-entry:nth-child(3) .timeline-year h2 {
  color: #06b7d5;
  text-shadow: 0 0 20px #06b7d5;
}
.timeline-entry:nth-child(4) .timeline-year h2 {
  color: #4f45e3;
  text-shadow: 0 0 20px #4f45e3;
}

.light-mode .timeline-year h2 {
  text-shadow: 0 0 4px rgba(0,0,0,0.08);
}

@media screen and (max-width: 768px) {
 
  .timeline-container {
    padding: 3rem 1rem;
  }

  .timeline-line {
    left: 1rem;
    transform: none;
  }

  
  .timeline-entry {
    justify-content: flex-start !important;
    padding-left: 3rem;
    text-align: left;
  }

  .timeline-content {
    max-width: none;
    width: calc(100% - 4rem);
    margin-top: 0;
    background: rgba(255,255,255,0.03); 
    box-shadow: none; 
    border: none;
    border-radius: 0.75rem;
  }

  .timeline-year h2 { font-size: 1.5rem; }
  .timeline-title { font-size: 1.1rem; }
  .description { font-size: 0.95rem; line-height: 1.4; }
  .industry { font-size: 0.8rem; }

  .tags { gap: 0.35rem; }
  .tag { padding: 0.25rem 0.5rem; font-size: 0.7rem; }
}

@media screen and (max-width: 480px) {
  .timeline-container { padding: 2rem 0.5rem; }
  .timeline-line { left: 0.75rem; }
  .timeline-entry { padding-left: 2.25rem; }
  .timeline-content { width: calc(100% - 3rem); padding: 1rem; }
  .timeline-year h2 { font-size: 1.25rem; }
  .timeline-title { font-size: 1rem; }
  .description { font-size: 0.85rem; }
}
</style>
