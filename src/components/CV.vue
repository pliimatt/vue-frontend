<template>
  <personal-info-panel
    :name="pInfo.name"
    :addr="pInfo.addr"
    :postPlace="pInfo.postiPaikka"
    :phone="pInfo.puhNro"
    :email="pInfo.email"
  />
  <button id="EnterBtn" @click="showCovLetter = !showCovLetter">
    Show cover letter
  </button>
  <cover-letter-comp
    v-if="showCovLetter"
    :addr="mailAddr"
    :covLetterText="covLetterText"
    :motivText="motivText"
    @exit="showCovLetter = !showCovLetter"
  />
  <list-comp :edu="eduList" :jobs="jobList" :ITs="itList" />
</template>

<script>
import CoverLetterComp from "./CoverLetterComp.vue";
import PersonalInfoPanel from "./PersonalInfoPanel.vue";
import ListComp from "./ListComp.vue";
export default {
  components: { PersonalInfoPanel, CoverLetterComp, ListComp },
  data() {
    return {
      pInfo: {
        name: "Petri Liimatta",
        addr: "Tietolinja 9 B 75",
        postiPaikka: "90570 Oulu",
        puhNro: "040-050 5780",
        email: "petri.liimatta95@gmail.com",
      },
      mailAddr: "mailto:petri.liimatta95@gmail.com?subject=Job%offer",
      covLetterText:
        "I am a recent graduate form the University of Oulu with M.Sc. focusing on theoretical physics. My Pro Gradu -thesis dealt with a topic close to quantum computers and I have completed university courses regarding quantum computation, physics, mathematics and programming.",
      motivText:
        "I would be interested to work with React in a full stack project or in data analysis. My background on React includes the course Full Stack Open 2018 from Univeristy of Helsinki, full stack course with Opiframe and some independent projects.",
      showCovLetter: false,
      eduList: [
        {
          title: "University of Oulu, M.Sc.",
          desc: 'The degree of master of Science from Univerity of Oulu, majoring in physics with orientation being molecular and material physics. Pro gradu -thesis titled "Single qubit dephasing in the many-body localization phase transition" can be found at http://urn.fi/URN:NBN:fi:oulu-202105208042',
          date: "09/2019 - 05/2021",
        },
        {
          title: "University of Oulu, physics bachelor's degree programme",
          desc: "The degree of physics bachelor from Univerity of Oulu. Primary subject being physics with secondary subjects being mathematics and theoretical physics.",
          date: "09/2015 - 05/2019",
        },
        {
          title: "Matriculation examination",
          desc: "The matriculation examination from Taivalkoski high school: advanced mathematics (L), physics (E), english (M).",
          date: "08/2011 - 05/2014",
        },
      ],
      jobList: [
        {
          title: "University of Oulu, research group nanomo",
          desc: "Trainee producing and analyzing large amount of quantum mechanical simulation data.",
          date: "05/2019 - 08/2019",
        },
        {
          title: "University of Oulu",
          desc: "Lecturer’s assistant guiding excercises.",
          date: "01/2019 - 05/2019",
        },
        {
          title: "University of Oulu, research group MIPT",
          desc: "Trainee producing and analyzing large amount of molecular simulation data.",
          date: "06/2017 - 07/2017",
        },
      ],
      itList: [
        {
          title: "Python",
          desc: "Intermediate Plus",
        },
        {
          title: "C/C++",
          desc: "Basics Plus",
        },
        {
          title: "Java",
          desc: "Basics Plus",
        },
        {
          title: "HTML/CSS/Javascript",
          desc: "Intermediate Plus",
        },
        {
          title: "React",
          desc: "Intermediate",
        },
        {
          title: "Bash",
          desc: "Basics",
        },
        {
          title: "Microsoft-package",
          desc: "Basics",
        },
      ],
    };
  },
};
</script>
