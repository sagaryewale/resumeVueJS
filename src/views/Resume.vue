<template>
  <div class="Resume">
    <a
      href="/public/files/Sagar_Yewale.pdf" 
      download
      class="download-cv-btn btn btn-primary pb-3"
    >
      Download Sagar_Yewale's <strong>CV</strong>
      <span class="material-icons">
        get_app
      </span>
    </a>
    <div class="text-center pt-15vh" id="first-Page-15vh">
      <div class="container">
        <h2 class="text-white mb-5">Education & Polyxer System Work Experience</h2>
        <div class="row">
          <ul class="timeline mt-5 col-lg-8 col-md-10 col-12 m-auto text-left">
            <li>
              <h5>Post Graduate Diploma in Advananced Computing PG-DAC from C-DAC Bangalore</h5>
              <a target="_blank" href="https://cdac.in/"
                ><sup
                  >The Centre for Development of Advanced Computing (C-DAC) is an Indian autonomous scientific society, operating under the Ministry of Electronics and Information Technology.</sup
                ></a
              >
              <br />
              <sup>Jan 2022 ~ Dec 2022</sup>
            </li>


            <li>
              <h5>PRE-CAT Preparatory course From SUNBEAM INSTITUTE OF INFORMATION TECHNOLOGY, PUNE</h5>
              <a target="_blank" href="https://www.sunbeaminfo.com/index"
                ><sup
                  >Sunbeam: One of the best Computer Training Institute in Pune</sup
                ></a
              >
              <br />
              <sup>Oct 2022 ~ Jan 2022</sup>
            </li>


            <li>
              <h5>BE (Bachelor of Engineering from SHIVAJI UNIVERSITY KOLHAPUR, Maharashtra) </h5>
              <a target="_blank" href="https://www.unishivaji.ac.in/"
                ><sup
                  >Padmabhooshan Vasantraodada Patil Institute of Technology Budhgaon, Sangli</sup
                ></a
              >
              <br />
              <sup>June 2014 ~ may 2018</sup>
            </li>

          </ul>
        </div>
      </div>
    </div>
    <div class="text-center" id="second-Page">
      <div class="container vertical-middle pt-v-sm-20vh">
        <h2 class="text-white pb-3">Skills in IT</h2>
        <div class="row mt-5">
          <ul class="timeline col-lg-4 col-md-6 col-8 m-auto text-left">
            <li>
              <h5 class="pb-2">Programming Languages</h5>
              <ul>
                <li>C#, Java</li>
                <li>HTML, CSS, JavaScript</li>
                <li>jQuery, Bootstrap</li>
                <li>SQL (MS-SQL, MySQL)</li>
              </ul>
            </li>
            <li class="mt-5">
              <h5 class="pb-2">Frameworks</h5>
              <ul>
                <li>Asp.Net FrameWork / Asp.Net Core</li>
                <li>Web API</li>
                <li>MVC (Model View Controller)</li>
                <li>Entity Framework</li>
                <li>Vue.js</li>
              </ul>
            </li>
            <li class="mt-5">
              <h5 class="pb-2">Tools</h5>
              <ul>
                <li>Visual Studio</li>
                <li>VS Code</li>
                <li>SSMS</li>
                

              </ul>
            </li>
            <div></div>
          </ul>
        </div>
      </div>
    </div>

    <div>

    </div>


    <!-- <div class="text-center" id="third-Page">
      <div class="container vertical-middle pt-v-sm-20vh">
        <div class="pt-5">
          <div class="card mb-5 pb-5 bg-none m-auto border-0">
            <span class="material-icons card-img-top pt-4 font-88px text-wheat"
              >military_tech</span
            >
            <div class="card-body">
              <h5 class="card-title text-white">Top Student Award</h5>
              <p class="card-text">
                I was awarded the Year 2 Bachelor of Information Technology Top
                Student in 2019.
              </p>
              <div class="text-center border-div-trigger w-220px m-auto">
                <a
                  class="text-decoration-none"
                  target="_blank"
                  href="/img/top-student-certificate.png"
                  >See my award certificate</a
                >
                <div class="border-div"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div> -->



    <!-- <div class="text-center pb-5" id="forth-Page">
      <div class="container vertical-middle pt-v-sm-20vh">
        <div class="pt-5">
          <div class="card mb-5 pb-5 bg-none m-auto border-0">
            <span class="material-icons card-img-top pt-4 font-88px text-wheat"
              >library_books</span
            >
            <div class="card-body">
              <h5 class="card-title text-white">
                Transcript while studying at SIT
              </h5>
              <p class="card-text">
                As i am currently still in the final year of Bachelor of
                Information Technology, my transcript is incomplete. However,
                working as hard as I can, I have gained a great result with a
                current GPA of 8.4. (based on
                <a
                  target="_blank"
                  href="https://www.otago.ac.nz/study/enrolment/otago014344.html"
                  >Otago GPA calculator</a
                >)
              </p>
              <div class="text-center border-div-trigger w-220px m-auto">
                <a
                  target="_blank"
                  class="text-decoration-none"
                  href="/img/transcript.png"
                  >See Shawn's transcript</a
                >
                <div class="border-div"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div> -->




    <div id="Top" @click="Top">
      <span class="material-icons">
        arrow_upward
      </span>
      <p class="pl-1 mb-0">
        Top
      </p>
    </div>
    <div @click="Next" id="furtherInfo">
      <p class="mb-0">
        Next
      </p>
      <span class="material-icons">
        arrow_downward
      </span>
    </div>
  </div>
</template>

<script>
import $ from "jquery";
import root from "../App.vue";
// @ is an alias to /src

export default {
  name: "Resume",
  mounted() {
    $(window).unbind("scroll");
    $(window).on("load", root.methods.UpDownArrowsSwitcher());
    $(window).resize(function() {
      root.methods.UpDownArrowsSwitcher();
    });
    $(window).scroll(function() {
      var current = $(document).scrollTop();
      var firstP = $("#first-Page-15vh").offset().top;
      var secondP = $("#second-Page").offset().top;
      var thirdP = $("#third-Page").offset().top;

      if (!root.methods.ToDisableNavigationArrows()) {
        if (current <= firstP + 10) {
          $("#furtherInfo").css({ display: "block" });
        } else if (current > secondP - 40 && current <= secondP + 100) {
          $("#furtherInfo").css({ display: "block" });
        } else if (current > thirdP - 40 && current <= thirdP + 100) {
          $("#furtherInfo").css({ display: "block" });
        } else {
          $("#furtherInfo").css({ display: "none" });
        }
      }
    });
  },
  methods: {
    Next: function() {
      var current = $(document).scrollTop();
      var firstP = $("#first-Page-15vh").offset().top;
      var secondP = $("#second-Page").offset().top;
      var thirdP = $("#third-Page").offset().top;

      if (current <= firstP + 10) {
        $("html, body").animate({ scrollTop: secondP + 100 }, 1000);
        $("html, body").animate({ scrollTop: secondP - 60 }, 500);
        $("html, body").animate({ scrollTop: secondP + 20 }, 400);
        $("html, body").animate({ scrollTop: secondP }, 300);
      } else if (current > secondP - 40 && current <= secondP + 100) {
        $("html, body").animate({ scrollTop: thirdP + 100 }, 1000);
        $("html, body").animate({ scrollTop: thirdP - 60 }, 500);
        $("html, body").animate({ scrollTop: thirdP + 20 }, 400);
        $("html, body").animate({ scrollTop: thirdP }, 300);
      } else if (current > thirdP - 40 && current <= thirdP + 100) {
        $("html, body").animate(
          { scrollTop: $("#forth-Page").offset().top + 100 },
          500
        );
      }
    },
    Top: function() {
      root.methods.Top();
    }
  }
};
</script>

<style></style>
