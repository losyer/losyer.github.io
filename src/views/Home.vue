<template>
  <section class="home">
    <img src="@/assets/icons/home.png" alt="Profile" class="profile-img" />

    <div class="content">
      <h1 class="name">Shota Sasaki</h1>
      <ul class="bullet-points-top">
        <li>Research Scientist at SB Intuitions Corp. <code>(shota.sasaki@sbintuitions.co.jp)</code></li>
        <li>Visiting Researcher at Tohoku University FaiLab.</li>
        <li>Visiting Scientist at RIKEN Center for Advanced Intelligence Projects.</li>
      </ul>

      Research Interests: Word embeddings, Short Answer Scoring, Commonsense reasoning, Information Retrieval.

      <h2 class="headline">Job</h2>
      <ul class="bullet-points">
        <li v-for="(job, i) in jobs" :key="i">{{ job }}</li>
      </ul>

      <h2 class="headline">Education</h2>
      <ul class="bullet-points">
        <li v-for="(edu, i) in educations" :key="i">{{ edu }}</li>
      </ul>

      <h2 class="headline">Publications & Presentations (International)</h2>
      <ul class="bullet-points">
        <li v-for="(pub, i) in publications_int" :key="i">{{ pub }}</li>
      </ul>

      <h2 class="headline">Publications & Presentations (Domestic)</h2>
      <ul class="bullet-points">
        <li v-for="(pub, i) in publications_dom" :key="i">{{ pub }}</li>
      </ul>

      <h2 class="headline">Activity</h2>
      <ul class="bullet-points">
        <li v-for="(act, i) in activities" :key="i">{{ act }}</li>
      </ul>

    </div>
  </section>
</template>

<style scoped>
.home {
  display: flex;
  flex-direction: column;
  justify-content: center; /* 縦方向の中央寄せ */
  align-items: center;     /* 横方向の中央寄せ */
  min-height: 100vh;
  padding: 2rem;
}

.profile-img {
  width: 180px;
  height: 180px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 1.5rem;
  box-shadow: 0 4px 10px rgba(0,0,0,0.2);
}

.content {
  max-width: 750px;   /* テキストの折り返し幅 */
  width: 100%;        /* 画面が狭い場合は縮む */
  margin: 0 auto;     /* 中央寄せ */
  text-align: left;   /* 左寄せ */
  color: #555;        /* 全体の文字をグレーに */
  line-height: 1.8;   /* 行間も少し広めに */
}

.name {
  font-size: 2.2rem;
  margin: 0.5rem 0;
}

.headline {
  font-size: 1.4rem;
  color: #666;
  margin: 1.5rem 0 0.5rem;
}

.bullet-points-top {
  list-style: disc;
  padding-left: 1.5rem;
  line-height: 1.6;
}

.bullet-points {
  list-style: disc;
  padding-left: 1.5rem;
  line-height: 1.6;
}

.bullet-points li {
  margin-bottom: 0.75rem; /* 各 li の間に余白を追加 */
}

</style>

<script>
import jobData from "@/assets/data/job.json";
import educationData from "@/assets/data/education.json";
import publications_intData from "@/assets/data/publications_international.json";
import publications_domData from "@/assets/data/publications_domestic.json";
import activitiesData from "@/assets/data/activity.json";


export default {
  data() {
    return {
      jobs: jobData,
      educations: educationData,
      publications_int: publications_intData,
      publications_dom: publications_domData,
      activities: activitiesData,
    };
  }
};
</script>
