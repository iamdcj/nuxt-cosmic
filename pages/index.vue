<template>
  <div class=site-wrapper>
    <header class="grid site-header">
      <h1 class=visually--hidden>David Christian Jones, User Interface Engineer.</h1><a href=# class=site-logo>dcj</a>
    </header>
    <main class=site-main role=main>
      <div class="layout layout--home">
        <section class="grid masthead">
          <div class="grid__item masthead__inner">
            <h2 class=visually--hidden>Introduction</h2>
            <h3 class=masthead__title>Hi</h3>
            <div class=masthead__subtitle>
              <p>I am David Christian Jones,<br>a User Interface Engineer specialising<br>in responsive web
                applications.</p>
              <p><a href=https://dcj-temp.s3.us-east-2.amazonaws.com/dcj.codes/resume.pdf target=_blank
                  rel="external noopener noreferrer" class="btn btn--style-b">Résumé</a></p>
            </div>
          </div>
        </section>
        <div class=inner-wrapper>
          <div class=inner-action><a href=# class=site-logo>dcj</a></div>
          <section class="section section--approach">
            <header class=section__header>
              <h2 class=section__heading>About</h2>
              <div class=section__subtitle>
                <p>I have over seven years experience combining <abbr title="HyperText Markup Language">HTML</abbr>,
                  <abbr title="Cascading Style Sheets">CSS</abbr> and JavaScript to create modular, scalable, performant
                  websites for companies, charities, and <abbr title="Non-governmental organization">NGOs</abbr> of all
                  sizes.</p>
                <p>I am currently building web applications at <a href=https://www.rocketinsights.com/ target=_blank
                    rel="external noopener noreferrer">Rocket Insights.</a></p>
              </div>
            </header>
          </section>
        </div>
      </div>
    </main>
    <footer class="grid site-footer">
      <header class="grid__item section__header">
        <h2 class=section__heading>Contact</h2>
        <div class=section__subtitle>
          <p>If you would like to get in touch, just <a href=mailto:david@dcj.codes target=blank>drop me a line</a>.</p>
        </div>
      </header>
      <div class=grid__item>
        <nav class="navigation navigation--social">
          <h3 class=navigation__title>Social Navigation</h3>
          <ul>
            <li><a href=https://github.com/iamdcj/ target=_blank rel="external noopener noreferrer">GitHub</a></li>
            <li><a href=https://www.linkedin.com/in/iamdcj/ target=_blank
                rel="external noopener noreferrer">Linkedin</a></li>
            <li><a href=https://www.strava.com/athletes/iamdcj target=_blank
                rel="external noopener noreferrer">Strava</a></li>
          </ul>
        </nav>
      </div>
      <div class=grid__item><small class=copyright>© dcj.codes</small></div><a href=#
        class="btn back-to-top btn--style-a">Return to Start</a>
    </footer>
  </div>
</template>

<script>
import config from "../config";

const { read_key, bucket_slug } = config

export default {
  asyncData({ $axios }) {
    return $axios
      .get(`https://api.cosmicjs.com/v1/${bucket_slug}/object-type/posts`, {
        params: {
          read_key
        }
      })
      .then(res => {
        console.log(res);
      })
      .catch(error => {
        console.error(error);
      });
  }
};
</script>

<style>
    .grid,
    .grid__item {
      width: 100%
    }

    .btn {
      display: inline-block;
      text-decoration: none;
      border-bottom: 1px solid
    }

    @media (min-width:768px) {
      .btn {
        font-size: 18px;
        line-height: 30px
      }

      .btn--style-b {
        font-size: var(--font-size-a)
      }
    }

    .btn:hover,
    .btn:visited {
      color: #e13206;
      color: var(--brand-color-a)
    }

    .btn--style-a {
      border-bottom: 1px solid currentColor;
      padding: 0 15px calc(var(--vr)/2) 0;
      font: 200 18px/18px var(--font-fam-b);
      color: var(--brand-color-d)
    }

    @media (min-width:768px) {
      .btn--style-a {
        padding: 0 20px calc(var(--vr)/2) 0
      }
    }

    .btn--style-b {
      border-bottom: 1px solid currentColor;
      padding: 0 15px calc(var(--vr)/2) 0;
      font: 200 18px/18px var(--font-fam-thin);
      color: #e13206;
      color: var(--brand-color-a)
    }

    @media (min-width:768px) {
      .btn--style-b {
        font: 200 24px/30px var(--font-fam-thin);
        padding: 0 20px calc(var(--vr)/2) 0
      }
    }

    .btn--style-c:hover {
      color: var(--color-black);
      border: 1px solid;
      background: currentColor
    }

    :root {
      background: #fff;
      height: 100%;
      overflow-y: auto;
      --color-white: #fff;
      --color-black: #151515
    }

    * {
      -webkit-box-sizing: border-box;
      box-sizing: border-box
    }

    body {
      font-family: HelveticaNeue, Helvetica Neue, Helvetica, Arial, Lucida Grande, sans-serif;
      font-family: var(--font-fam-medium);
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      color: #151515;
      color: var(--color-black)
    }

    h5 {
      font: 600 20px/28px HelveticaNeue, Helvetica Neue, Helvetica, Arial, Lucida Grande, sans-serif;
      font: 600 20px/28px var(--font-fam-medium);
      margin-bottom: 18px
    }

    hr {
      display: inline-block;
      width: 30px;
      border-color: #023fa3;
      border-color: var(--color-d);
      margin: 18px 0
    }

    abbr {
      text-decoration: none
    }

    p {
      font: 200 16px/24px var(--font-fam-thin);
      margin-bottom: 12px;
      color: var(--brand-color-d)
    }

    @media (min-width:768px) {
      p {
        font: 200 24px/36px var(--font-fam-thin)
      }
    }

    .site-wrapper {
      --vr: 6px;
      --font-size-small: 14px;
      --font-size-a: calc(var(--vr)*3);
      --font-size-b: calc(var(--vr)*5);
      --font-size-c: calc(var(--vr)*7);
      --font-size-d: calc(var(--vr)*9);
      --font-fam-thin: "HelveticaNeue-Thin", "Helvetica Neue Thin", "Helvetica Neue", Helvetica, Arial, "Lucida Grande", sans-serif;
      --font-fam-light: "HelveticaNeue-Light", "Helvetica Neue Light", "Helvetica Neue", Helvetica, Arial, "Lucida Grande", sans-serif;
      --font-fam-medium: "HelveticaNeue", "Helvetica Neue", Helvetica, Arial, "Lucida Grande", sans-serif;
      --font-fam-strong: "HelveticaNeue-Bold", "Helvetica Neue Bold", "Helvetica Neue", Helvetica, Arial, "Lucida Grande", sans-serif;
      --font-fam-b: var(--font-fam-light);
      --font-fam-c: "Georgia";
      --brand-color-a: #e13206;
      --brand-color-b: var(--color-black);
      --brand-color-c: #e13206;
      --brand-color-d: #4b4b4b;
      --brand-color-e: #a9a9a9
    }

    .site-main {
      text-rendering: optimizeLegibility;
      -webkit-font-smoothing: antialiased;
      max-width: 100%;
      overflow-x: hidden
    }

    .navigation__title,
    .site-logo span {
      border: 0;
      clip: rect(0 0 0 0);
      height: 1px;
      margin: -1px;
      overflow: hidden;
      padding: 0;
      position: absolute;
      width: 1px
    }

    .navigation__title.focusable:active,
    .navigation__title.focusable:focus {
      clip: auto;
      height: auto;
      margin: 0;
      overflow: visible;
      position: static;
      width: auto
    }

    a {
      display: inline-block;
      -webkit-transition: all .25s ease-in-out;
      -o-transition: all ease-in-out .25s;
      transition: all .25s ease-in-out;
      border-bottom: 1px solid currentColor;
      color: #e13206;
      color: var(--brand-color-a);
      cursor: pointer;
      text-decoration: none
    }

    a:visited {
      color: #a9a9a9;
      color: var(--brand-color-e)
    }

    a:hover,
    a:visited {
      border-color: currentColor
    }

    a:hover {
      color: #e13206;
      color: var(--brand-color-a)
    }

    li {
      font: 200 18px/30px var(--font-fam-b);
      margin-bottom: 12px
    }

    .cntr {
      text-align: center
    }

    .inner-wrapper {
      position: relative;
      height: 100%
    }

    .inner-action {
      position: absolute;
      top: 0;
      right: 0;
      width: 100%;
      height: 100%;
      clip: rect(auto, auto, auto, auto);
      z-index: 2;
      pointer-events: none
    }

    .inner-action .site-logo,
    .inner-action .site-logo:hover,
    .inner-action .site-logo:visited {
      color: #a9a9a9;
      color: var(--brand-color-e)
    }

    .section {
      -webkit-backface-visibility: hidden;
      backface-visibility: hidden;
      position: relative;
      padding: 0 20px 30px;
      z-index: 1
    }

    @media (min-width:768px) {
      .section {
        padding: 40px 20px 120px
      }
    }

    .section__header {
      width: 90%;
      text-align: center;
      margin-bottom: 48px
    }

    @media (min-width:768px) {
      .section__header {
        width: 100%
      }
    }

    .section__heading {
      position: relative;
      margin-bottom: 18px;
      font: 800 36px/48px var(--font-fam-strong)
    }

    @media (min-width:768px) {
      .section__heading {
        font: 800 72px/84px var(--font-fam-strong)
      }
    }

    @media (min-width:768px) {
      .section__subtitle {
        width: 97.5%
      }
    }

    @media (min-width:1200px) {
      .section__subtitle {
        width: 55%
      }
    }

    .section p {
      margin-bottom: 30px
    }

    .section__body,
    .section__subtitle {
      display: inline-block
    }

    .section__body {
      padding-bottom: 36px
    }

    @media (min-width:768px) {
      .section__body {
        width: 80%
      }
    }

    @media (min-width:1200px) {
      .section__body {
        width: 60%
      }
    }

    .section__closing {
      position: relative;
      margin-top: 15px;
      padding-top: 24px;
      text-align: center
    }

    .section__closing:before {
      content: "";
      display: inline-block;
      width: 30px;
      height: 1px;
      background: #000;
      background: var(--color-black);
      position: absolute;
      top: 0;
      left: 50%;
      -webkit-transform: translateX(-50%);
      -ms-transform: translateX(-50%);
      transform: translateX(-50%)
    }

    .site-header {
      max-width: 100%;
      height: 120px;
      padding: 24px 20px;
      position: fixed;
      clip: rect(auto, auto, auto, auto);
      top: 0;
      left: 0;
      z-index: 2;
      pointer-events: none
    }

    @media (min-width:1200px) {
      .site-header {
        padding: 24px 60px
      }
    }

    .site-header__title {
      font-size: var(--font-size-d)
    }

    .site-logo {
      position: fixed;
      top: 18px;
      right: 20px;
      z-index: 1;
      color: #e13206;
      color: var(--brand-color-a);
      pointer-events: auto;
      text-decoration: none;
      font: 200 18px/18px var(--font-fam-thin);
      border: none
    }

    @media (min-width:768px) {
      .site-logo {
        width: 50px;
        top: 30px;
        right: 20px;
        font: 200 30px/30px var(--font-fam-thin)
      }
    }

    .site-logo a {
      border: none
    }

    .site-logo a:hover,
    .site-logo a:visited {
      color: #a9a9a9;
      color: var(--brand-color-e)
    }

    .site-logo:hover,
    .site-logo:visited {
      color: #e13206;
      color: var(--brand-color-a)
    }

    .site-logo--footer {
      display: inline-block;
      width: 25px
    }

    .navigation--main {
      width: 100%;
      visibility: hidden
    }

    @media (min-width:1024px) {
      .navigation--main {
        opacity: 1;
        visibility: visible
      }
    }

    .site-footer {
      padding: 30px 20px;
      position: relative;
      -ms-flex-align: center;
      align-items: center;
      color: #000;
      color: var(--color-black);
      text-align: center
    }

    @media (min-width:768px) {
      .site-footer {
        padding: 40px 20px 20px
      }
    }

    .site-footer .section__header {
      width: 100%;
      margin-bottom: 18px
    }

    .copyright {
      font-size: 18px;
      font-family: var(--font-fam-thin);
      text-align: center;
      color: #e13206;
      color: var(--brand-color-a)
    }

    .back-to-top {
      font-size: 14px;
      font-family: var(--font-fam-thin);
      position: absolute;
      padding-right: 40px;
      right: 0;
      bottom: 20px;
      text-align: left
    }

    .back-to-top,
    .back-to-top:hover {
      color: #e13206;
      color: var(--brand-color-a)
    }

    .back-to-top:hover,
    .back-to-top:visited {
      border-color: currentColor
    }

    .back-to-top:visited {
      color: #e13206;
      color: var(--brand-color-a)
    }

    @media (min-width:768px) {
      .back-to-top {
        font-size: 16px
      }
    }

    .navigation--social ul {
      display: -ms-flexbox;
      display: flex;
      text-align: center;
      -ms-flex-pack: center;
      justify-content: center;
      -ms-flex-wrap: wrap;
      flex-wrap: wrap;
      padding: 0 0 54px
    }

    .navigation--social li {
      padding: var(--vr) 0 calc(var(--vr)*2);
      margin: 0 10px
    }

    @media (min-width:768px) {
      .navigation--social li {
        width: auto;
        padding: calc(var(--vr)*2) 10px
      }
    }

    .navigation--social li a {
      padding: 0 15px calc(var(--vr)/2) 0;
      border-bottom: 1px solid currentColor;
      font-size: 12px;
      text-decoration: none;
      -webkit-transition: color .25s ease-in-out;
      -o-transition: color ease-in-out .25s;
      transition: color .25s ease-in-out;
      color: var(--brand-color-d)
    }

    @media (min-width:768px) {
      .navigation--social li a {
        padding: 0 20px calc(var(--vr)/2) 0;
        font-size: 18px
      }
    }

    .navigation--social li a:hover {
      color: #e13206;
      color: var(--brand-color-a)
    }

    .masthead {
      display: -ms-flexbox;
      display: flex;
      height: 92.5vh;
      min-height: 400px;
      position: relative;
      -ms-flex-align: center;
      align-items: center;
      justify-items: center;
      color: #000;
      color: var(--color-black)
    }

    @media (min-width:1200px) {
      .masthead {
        height: 100vh
      }
    }

    .masthead__inner {
      position: relative;
      padding: 78px 20px 20px;
      z-index: 2
    }

    @media (min-width:1200px) {
      .masthead__inner {
        padding: 20px 20%;
        width: 100%
      }
    }

    .masthead__title {
      font: 800 114px/114px var(--font-fam-medium)
    }

    @media (min-width:768px) {
      .masthead__title {
        font: 800 222px/222px var(--font-fam-medium)
      }
    }

    .masthead__subtitle p {
      clear: left;
      font: 200 18px/24px var(--font-fam-thin);
      padding-left: 5px;
      color: var(--brand-color-d)
    }

    @media (min-width:768px) {
      .masthead__subtitle p {
        font: 200 30px/42px var(--font-fam-thin);
        padding-left: 10px
      }
    }

    .section--approach,
    .section--introduction {
      display: -ms-flexbox;
      display: flex;
      -ms-flex-direction: column;
      flex-direction: column;
      -ms-flex-align: center;
      align-items: center;
      -ms-flex-pack: center;
      justify-content: center
    }

    .section--introduction {
      margin: 0 auto 142px;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 60px 0 40px;
      background-color: #e13206;
      background-color: var(--brand-color-a);
      width: 90%;
      color: #fff
    }

    .section--introduction .section__header {
      margin-bottom: 12px
    }

    .section--introduction .section__header .section__heading {
      position: relative;
      margin-bottom: 18px;
      font: 800 18px/30px var(--font-fam-strong);
      color: #fff;
      color: var(--color-white)
    }

    @media (min-width:768px) {
      .section--introduction {
        width: 75%;
        margin: 0 auto 240px;
        min-height: 35vh
      }

      .section--introduction .section__header {
        width: 85%
      }

      .section--introduction .section__header .section__heading {
        font: 800 30px/36px var(--font-fam-strong)
      }
    }

    @media (min-width:1200px) {
      .section--introduction {
        min-height: 40vh;
        max-height: 450px
      }

      .section--introduction .section__header {
        width: 85%
      }

      .section--introduction .section__header .section__heading {
        font: 800 42px/48px var(--font-fam-strong)
      }
    }

    .section--introduction:before {
      bottom: 0;
      background: #fff;
      background: var(--color-white)
    }

    .section--introduction:after,
    .section--introduction:before {
      content: "";
      display: block;
      position: absolute;
      left: 50%;
      -webkit-transform: translateX(-50%);
      -ms-transform: translateX(-50%);
      transform: translateX(-50%);
      height: 15px;
      width: 1px
    }

    .section--introduction:after {
      top: 100%;
      background: #e13206;
      background: var(--brand-color-a)
    }

    @media (min-width:768px) {

      .section--introduction:after,
      .section--introduction:before {
        height: 30px
      }
    }
  </style>