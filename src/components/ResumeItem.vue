<template>
  <div id="app">
    
    <header>
        <img :src="pro" alt="Profile Image" style="max-width: 170px; float: left;" />
        <h4>{{ name }}</h4>
        <h3 >{{ title }}</h3>
    </header>
    <h1>ข้อมูลส่วนตัว</h1>
    <ul>
        <li v-for="personal in personal" :key="personal.id" >
            <p >{{ personal.sname}}</p>
            <p >{{ personal.birthday }}</p>
            <p >{{ personal.sex}}</p>
            <p >{{ personal.Nationality}}</p>
            <p >{{ personal.Blood_type}}</p>
        </li>
    </ul>
    <h1>การศึกษา</h1>
    <ul>
      <li v-for="education in education" :key="education.id">
        <p>{{ education.school }}</p>
        <p>{{ education.degree }}</p>
      </li>
    </ul>
    <h1>ทักษะ</h1>
    <ul>
      <li v-for="skill in skills" :key="skill.id">
        <h2>ภาษา</h2>
        <p>{{ skill.Languages }}</p>
        <h2>เครื่องมือ</h2>
        <p>{{ skill.Tools }}</p>
        <h2>เฟรมเวิร์ค</h2>
        <p>{{ skill.Framework }}</p>
      </li>
    </ul>
    <h2>ความสนใจ</h2>
    <p>{{ Interest }}</p>
    <h1>ช่องทางการติดต่อ</h1>
    <ul>
        <li v-for="Contact in Contact" :key="Contact.id">
            <h2>เบอร์ติดต่อ</h2>
            <p>{{ Contact.Telephone_number }}</p>
            <h2>อีเมลล์</h2>
            <p>{{ Contact.email }}</p>
            <h2>ที่อยู่</h2>
            <p>{{ Contact.address }}</p>
        </li>
    </ul>
    <h1>ภาษา</h1>
    <p>{{ language }}</p>  
    <h1>ผลงาน</h1>
    <div class="performance-container">
        <div v-for="(item, index) in performance" :key="index" class="performance-item">
            <h6>{{ Object.keys(item)[0] }}</h6>
        <img
         v-if="item[Object.keys(item)[0]]"
         :src="item[Object.keys(item)[0]]"
         alt="Performance Image"
         style="max-width: 100%; max-height: 100%;"
        />
        </div>
    </div>
    
  </div>
</template>

<script setup>
import { ref } from "vue";

const name = ref("กิตติภัฎ ชูบัว");
const title = ref("Front End Developer");
const pro  = '/image/01.jpg'
const Interest = ref(
  "ชอบในการเขียนโปรแกรมและออกแบบพัฒนาเว็บไซค์ให้สวยงามตามความต้องการของผู้ใช้ ชอบทำงานร่วมกันกับผู้อื่น ชอบที่ได้แชร์ไอเดีย พูดคุยกับคนอื่น เพื่อหาข้อผิดพลาดของตนเองได้ และชอบงานที่มีการพัฒนาให้ทันต่อยุคสมัย"
);

const education = ref([
  {
    id: 1,
    degree: "หลักสูตรวิทยาการคอมพิวเตอร์",
    school: "มหาวิทยาลัยราชภัฎสงขลา ",
  },
]);
const skills = ref([
  {
    Languages: "HTML, CSS, JavaScript,C, Pyton, SQL",
    Tools: "MySQL, Visual Studio Code,Vite.js, Git,Figma",
    Framework: "Vue.js",
  },
]);

const personal = ref([
  {
    sname: "ชื่อเล่น: ต้น",
    birthday: "วันเกิด: 20  กรกฎาคม 2544",
    sex: "เพศ: ชาย",
    Nationality: "สัญชาติ: ไทย",
    Blood_type: "กรุ๊ปเลือด: B",
  },
]);

const Contact = ref([
  {
    Telephone_number: "064-861-3125",
    email: "kittipat3210@gmail.com",
    address: "45/3 Thetsaban Road 16, Na Yong District, Trang Province 92170",
  },
]);
const language = "English";
const performance = ref([{github:'/image/github.jpg'},
                     {Google_Drive:'/image/drive.jpg'},
 ])
 
</script>


