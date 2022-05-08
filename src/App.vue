<template>
  <main class="warpper">
    <nav class="navigation">
      <section class="container">
        <a class="navigation-title">
          <h1 class="title">ADSB上传套件UUID在线生成</h1></a
        >
        <a
          href="https://github.com/dextercai/feeyo_uuid_gen"
          rel="noopener"
          target="_blank"
          ><svg class="octocat" viewBox="0 0 250 250">
            <path d="M0,0 L115,115 L130,115 L142,142 L250,250 L250,0 Z"></path>
            <path
              class="octocat-arm"
              d="M128.3,109.0 C113.8,99.7 119.0,89.6 119.0,89.6 C122.0,82.7 120.5,78.6 120.5,78.6 C119.2,72.0 123.4,76.3 123.4,76.3 C127.3,80.9 125.5,87.3 125.5,87.3 C122.9,97.6 130.6,101.9 134.4,103.2"
            ></path>
            <path
              class="octocat-body"
              d="M115.0,115.0 C114.9,115.1 118.7,116.5 119.8,115.4 L133.7,101.6 C136.9,99.2 139.9,98.4 142.2,98.6 C133.8,88.0 127.5,74.4 143.8,58.0 C148.5,53.4 154.0,51.2 159.7,51.0 C160.3,49.4 163.2,43.6 171.4,40.1 C171.4,40.1 176.1,42.5 178.8,56.2 C183.1,58.6 187.2,61.8 190.9,65.4 C194.5,69.0 197.7,73.2 200.1,77.6 C213.8,80.2 216.3,84.9 216.3,84.9 C212.7,93.1 206.9,96.0 205.4,96.6 C205.1,102.4 203.0,107.8 198.3,112.5 C181.9,128.9 168.3,122.5 157.7,114.1 C157.9,116.9 156.7,120.9 152.7,124.9 L141.0,136.5 C139.8,137.7 141.6,141.9 141.8,141.8 Z"
            ></path></svg
        ></a>
      </section>
    </nav>
    <section class="container" id="about">
      <div class="carbonads"></div>
      <h2 class="title">说明</h2>
      <p class="description">
        本页用于生成适用于<a
          href="https://github.com/dextercai/feeyo-adsb-golang"
          >飞常准ADSB上传套件Golang版</a
        >的16位UUID。
      </p>
      <h2 class="title">Q&A</h2>
      <p class="description">
        为什么v1多次生成不会变化？<br>
        基于时间部分主要变化在UUID前半部分，故后半部分在每次浏览加载的生命周期内不会发生改变。对于部署上传套件来说，两者均可。
      </p>
    </section>
    <section class="container">
      <form>
        <fieldset>
          <label for="nameField">UUID v1 （基于时间）</label>
          <input type="text" placeholder="UUID" readonly v-model="uuid1" />

          <label for="nameField">UUID v4 （随机，无生成参照）</label>
          <input type="text" placeholder="UUID" readonly v-model="uuid4" />

          <input
            class="button"
            type="button"
            value="生成完整UUID（不适用于CONF文件）"
            @click="this.full"
          />
          &nbsp;
          <input
            class="button"
            type="button"
            value="生成适用于飞常准套件的16位识别码"
            @click="this.tidy"
          />
        </fieldset>
      </form>
    </section>
    <footer class="footer">
      <section class="container">
        <p class="copyright">
           Created and Deployed by<a
            href="https://blog.dextercai.com"
            rel="noopener"
            target="_blank"
            title="Dexter Cai's Blog"
          >
            DexterCai </a
          >2022.05.08
        </p>
        <nav class="nav">
          <a
            class="link"
            href="https://github.com/dextercai"
            rel="noopener"
            target="_blank"
            title="Dexter Cai on Github"
            ><svg class="icon" viewBox="0 0 512 512">
              <g>
                <path
                  d="M109,33c1.667,0,3.333,0,5,0c0.858,0.338,1.688,0.821,2.578,0.993c9.22,1.778,18.936,2.236,27.569,5.534c14.421,5.51,28.124,12.886,42.202,19.317c2.099,0.959,4.652,1.66,6.897,1.448c17.485-1.653,34.912-4.113,52.427-5.184c11.058-0.676,22.262,0.256,33.351,1.117c9.9,0.769,19.71,2.641,29.601,3.597c4.24,0.41,8.364,2.348,12.935-0.69c21.736-14.445,45.523-23.332,71.793-24.663c1.361-0.069,3.713,1.54,4.079,2.807c1.591,5.516,3.041,11.141,3.76,16.826c1.531,12.107,4.122,24.377,3.329,36.386c-0.625,9.459,0.544,16.535,6.219,24.341c12.723,17.5,20.408,37.49,23.187,58.995c1.33,10.292,1.601,20.815,1.284,31.201c-0.376,12.316-1.901,24.596-2.951,37.167c0.338,0.036,1.465,0.25,2.595,0.266c15.816,0.237,31.634,0.383,47.449,0.689c8.153,0.158,16.313,0.436,24.44,1.054c1.251,0.095,2.34,2.323,3.503,3.564c-1.282,1.126-2.501,3.128-3.858,3.227c-5.639,0.409-11.319,0.278-16.984,0.285c-18.996,0.021-37.992,0.012-56.988,0.025c-2.427,0.002-5.137-0.354-5.302,3.649c0.909,0.237,1.666,0.575,2.438,0.614c14.272,0.715,28.59,0.917,42.803,2.244c10.187,0.951,20.257,3.283,30.315,5.314c1.363,0.275,2.355,2.384,3.519,3.644c-1.646,0.961-3.358,2.836-4.927,2.724c-6.597-0.47-13.183-1.34-19.715-2.416c-18.284-3.012-36.68-4.061-55.186-3.753c-2.809,0.047-4.359,0.898-5.809,3.508c-8.302,14.941-20.161,26.575-34.122,36.306c-16.457,11.471-35.061,17.423-54.285,21.939c-4.655,1.094-9.312,2.183-14.252,3.341c10.623,13.66,15.411,26.753,15.565,43.847c0.238,26.492,0.129,52.987,0.255,79.48c0.038,8.056,1.544,15.557,8.611,20.85c1.347,1.009,1.945,3.017,2.888,4.564c-0.277,0.441-0.554,0.883-0.831,1.324c-5.849-0.788-11.722-1.427-17.541-2.394c-14.611-2.429-28.554-8.686-27.837-30.227c0.753-22.612-0.417-45.288-0.795-67.936c-0.024-1.45-0.469-2.894-0.718-4.34c-1.355,1.315-1.711,2.539-1.708,3.762c0.091,28.979,0.031,57.961,0.57,86.932c0.072,3.841,2.661,8.057,5.135,11.298c1.992,2.61,1.829,3.792-0.486,5.427c-1.333,0-2.667,0-4,0c-5.8-0.99-11.667-1.692-17.384-3.034c-10.209-2.397-17.504-11.956-17.605-22.228c-0.265-26.803-0.581-53.607-0.969-80.408c-0.021-1.444-0.892-2.876-1.367-4.314c-0.565,0.115-1.129,0.229-1.694,0.344c0,1.741,0.001,3.483,0,5.224c-0.008,25.654,0.012,51.308-0.039,76.961c-0.022,10.904-2.372,20.592-14.658,23.864c-5.047,1.344-10.283,1.995-15.45,2.858c-2.256,0.377-4.555,0.496-6.835,0.733c-1,0-2,0-3,0c-2.247-1.482-2.846-3.036-0.577-5.141c4.878-4.523,5.891-10.21,5.604-16.691c-0.427-9.644-0.087-19.321-0.087-28.984c0-17.945,0.001-35.889-0.04-53.834c-0.002-0.993-0.38-1.985-0.583-2.978c-0.575-0.028-1.15-0.055-1.725-0.083c-0.597,4.946-1.62,9.884-1.71,14.839c-0.241,13.324,0.004,26.656-0.111,39.984c-0.085,9.813-0.349,19.627-0.693,29.434c-0.23,6.557-2.705,11.917-8.928,14.996c-3.112,1.54-6.068,3.473-9.299,4.685c-7.458,2.797-15.17,3.642-23.825,2.363c0.907-1.601,1.217-2.811,1.996-3.417c5.6-4.355,7.742-10.341,7.835-17.079c0.26-18.967,0.318-37.937,0.427-56.905c0.001-0.261-0.366-0.524-1.386-1.892c-9.618,0-20.066-0.101-30.511,0.024c-15.64,0.188-28.65-5.576-39.443-16.779c-9.263-9.615-15.158-21.456-22.02-32.674c-7.435-12.154-14.453-24.681-27.538-32.053c-1.176-0.662-1.579-2.696-2.806-4.944c6.744,0.764,12.28,1.214,17.747,2.09c2.547,0.408,5.303,1.152,7.375,2.591c8.143,5.654,16.232,11.416,24.006,17.561c13.169,10.409,24.265,24.328,43.559,23.589c9.913-0.379,19.853-0.067,30.057-0.067c2.016-13.247,9.261-23.677,18.936-33.082c-2.593-0.663-4.319-1.287-6.097-1.53c-16.388-2.237-32.313-6.396-47.542-12.723c-23.651-9.826-43.201-24.931-57.266-46.675c-0.676-1.046-2.211-2.194-3.339-2.187c-10.482,0.065-21.013-0.188-31.43,0.755c-12.879,1.165-25.65,3.488-38.499,5.055c-2.545,0.31-5.387-0.098-7.81-0.963c-2.753-0.984-2.819-3.17-0.399-4.86c1.18-0.824,2.712-1.301,4.153-1.567c22.086-4.076,44.27-7.14,66.826-6.267c1.618,0.063,3.253-0.3,4.88-0.464c0.046-0.645,0.093-1.291,0.139-1.936c-2.711-0.65-5.418-1.844-8.134-1.863c-22.156-0.154-44.315-0.053-66.472-0.136c-2.621-0.01-5.274-0.51-7.84-1.098c-0.907-0.208-2.326-1.473-2.234-2.051c0.181-1.125,1.068-2.731,2.01-3.026c2.506-0.783,5.19-1.294,7.816-1.352c21.475-0.471,42.953-0.816,64.431-1.192c1.741-0.03,3.482-0.004,4.273-0.004c-1.743-13.256-3.274-25.841-5.079-38.387c-2.117-14.711,0.115-29.126,3.077-43.4c3.819-18.405,12.758-34.358,24.964-48.556c0.69-0.803,1.265-2.101,1.177-3.105c-0.273-3.102-1.227-6.164-1.322-9.259c-0.393-12.88-1.298-25.808-0.582-38.638C104.49,51.686,107.24,42.371,109,33z"
                ></path>
              </g></svg
          ></a>
        </nav>
      </section>
    </footer>
  </main>
</template>

<script>
import { v4 as uuidv4, v1 as uuidv1 } from "uuid";
export default {
  name: "UUID_App",
  data() {
    return {
      uuid1: "",
      uuid4: "",
    };
  },
  mounted() {},
  methods: {
    full: function () {
      this.uuid1 = uuidv1();
      this.uuid4 = uuidv4();
    },
    tidy: function () {
      this.full();
      this.uuid1 = this.gen16(this.uuid1);
      this.uuid4 = this.gen16(this.uuid4);
    },
    gen16: function (str) {
      var re = /-/gi;
      str = str.replace(re, "").slice(16);
      return str;
    },
  },
};
</script>

<style>
@font-face {
  font-family: Gotham Rounded A;
  font-style: normal;
  font-weight: 300;
  src: url(data:application/x-font-woff;base64,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);
}

@font-face {
  font-family: Gotham Rounded B;
  font-style: normal;
  font-weight: 300;
  src: url(data:application/x-font-woff;base64,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);
}

.wrapper {
  display: block;
  overflow: hidden;
  position: relative;
  width: 100%;
}

.wrapper .container {
  max-width: 80rem;
}

.wrapper > .container {
  padding-bottom: 7.5rem;
  padding-top: 7.5rem;
}

.header {
  background-color: #f4f5f6;
  padding-top: 1rem;
}

@media (min-width: 40rem) {
  .header {
    padding-top: 5rem;
  }
}

.header + section {
  border-top: 0;
}

.header .container {
  border-top: 0;
  padding-bottom: 7.5rem;
  padding-top: 7.5rem;
  position: relative;
  text-align: center;
}

.header .title {
  font-family: Gotham Rounded A, Gotham Rounded B, Helvetica Neue, Arial,
    sans-serif;
}

.header .img {
  height: 15rem;
  margin-bottom: 2rem;
}

.header .img path {
  animation: 7s a forwards;
  fill: #000000;
  stroke: #000000;
  stroke-dasharray: 38321;
  stroke-miterlimit: 10;
  stroke-width: 15px;
}

.header .button {
  margin-bottom: 4rem;
  margin-top: 2rem;
}

@media (min-width: 40rem) {
  .header .button {
    margin-bottom: 4rem;
    margin-top: 2rem;
  }
}

@keyframes a {
  0% {
    fill-opacity: 0;
    stroke-dashoffset: 38321;
  }

  25% {
    fill-opacity: 0;
    stroke: #9b4dca;
  }

  to {
    fill-opacity: 1;
    stroke-dashoffset: 0;
  }
}

.footer {
  padding: 8rem 0 2rem;
}

.footer .copyright {
  padding-right: 6rem;
}

.footer .nav {
  position: absolute;
  right: 2rem;
  top: 50%;
  transform: translateY(-50%);
}

.footer .nav .link {
  display: inline-block;
  margin-left: 1.2rem;
  padding: 0;
}

.footer .nav .icon {
  fill: #9b4dca;
  height: 2rem;
}

.footer .nav .icon:hover {
  fill: #606c76;
}

.navigation {
  background: #f4f5f6;
  border-bottom: 0.1rem solid #d1d1d1;
  display: block;
  height: 5.2rem;
  left: 0;
  max-width: 100%;
  position: fixed;
  right: 0;
  top: 0;
  width: 100%;
  z-index: 2;
}

.navigation .container {
  padding-bottom: 0;
  padding-top: 0;
}

.navigation .navigation-list {
  list-style: none;
  margin-bottom: 0;
  margin-right: 5rem;
}

@media (min-width: 80rem) {
  .navigation .navigation-list {
    margin-right: 0;
  }
}

.navigation .navigation-item {
  float: left;
  margin-bottom: 0;
  margin-left: 2.5rem;
  position: relative;
}

.navigation .img {
  fill: #000000;
  height: 2rem;
  position: relative;
  top: 0.3rem;
}

.navigation .navigation-title,
.navigation .title {
  color: #606c76;
  font-family: Gotham Rounded A, Gotham Rounded B, Helvetica Neue, Arial,
    sans-serif;
  position: relative;
}

.navigation .navigation-link,
.navigation .navigation-title,
.navigation .title {
  display: inline;
  font-size: 1.6rem;
  line-height: 5.2rem;
  padding: 0;
  text-decoration: none;
}

.navigation .navigation-link.active {
  color: #606c76;
}

.octocat {
  border: 0;
  color: #f4f5f6;
  fill: #000000;
  height: 5.2rem;
  position: fixed;
  right: 0;
  top: 0;
  width: 5.2rem;
  z-index: 2;
}

.octocat:hover .octocat-arm {
  animation: b 0.56s infinite;
  transform-origin: 13rem 10.6rem;
}

.octocat .octocat-arm,
.octocat .octocat-body {
  fill: #f4f5f6;
}

@keyframes b {
  0%,
  50% {
    transform: rotate(0);
  }

  25%,
  75% {
    transform: rotate(-25deg);
  }
}

.popover {
  background: #fff;
  border: 0.1rem solid #d1d1d1;
  border-radius: 0.4rem;
  display: none;
  filter: drop-shadow(0 0 0.6rem rgba(0, 0, 0, 0.1));
  left: 50%;
  min-width: 13.4rem;
  position: absolute;
  top: 94%;
  transform: translateX(-50%);
}

.popover.popover-open {
  display: block;
}

.popover:after,
.popover:before {
  border: solid transparent;
  border-color: transparent;
  border-width: 1rem;
  content: " ";
  height: 0;
  left: 50%;
  pointer-events: none;
  position: absolute;
  right: 1.7rem;
  top: 0;
  width: 0;
}

.popover:after {
  border-bottom-color: #fff;
  transform: translate(-50%, -100%);
}

.popover:before {
  border-bottom-color: #d1d1d1;
  transform: translate(-50%, -102%);
}

.popover .popover-list {
  list-style: none;
  margin: 0;
  padding: 0;
}

.popover .popover-item {
  margin: 0;
  padding: 0;
}

.popover .popover-item:first-child .popover-link {
  border-radius: 0.4rem 0.4rem 0 0;
}

.popover .popover-item:last-child .popover-link {
  border-bottom-width: 0;
  border-radius: 0 0 0.4rem 0.4rem;
}

.popover .popover-link {
  border-bottom: 0.1rem solid #d1d1d1;
  color: #606c76;
  display: block;
  font-size: 1.2rem;
  padding: 0.8rem 2rem;
  position: relative;
  text-align: center;
  text-decoration: none;
}

.popover .popover-link:hover {
  background: #9b4dca;
  border-bottom-color: #9b4dca;
  color: #fff;
}

.share,
.share-list,
.share-list a {
  position: relative;
  text-decoration: none;
}

.share-item {
  display: inline-block;
  margin: 1rem 0;
}

.share-item:nth-child(n + 1) {
  margin-left: 0.5rem;
}

.share-dialog {
  background-color: #9b4dca;
  border-radius: 0.4rem;
  color: #fff;
  display: block;
  height: 2.2rem;
  text-align: center;
  width: 5rem;
}

.share-dialog:hover {
  background-color: #606c76;
}

.share-dialog .share-icon {
  fill: #fff;
  height: 1.5rem;
}

@media (min-width: 40rem) {
  .only-mobile {
    display: none;
  }
}

.prettyprint.code {
  border: 0;
  border-left: 0.3rem solid #9b4dca;
  color: #655d5d;
  margin-top: 0;
  position: relative;
}

.prettyprint.code .str {
  color: #4b8b8b;
}

.prettyprint.code .kwd {
  color: #8464c4;
}

.prettyprint.code .com {
  color: #adadad;
}

.prettyprint.code .typ {
  color: #7272ca;
}

.prettyprint.code .lit {
  color: #9b4dca;
}

.prettyprint.code .pun {
  color: #5485b6;
}

.prettyprint.code .clo,
.prettyprint.code .opn {
  color: #f4ecec;
}

.prettyprint.code .atn,
.prettyprint.code .tag {
  color: #9b4dca;
}

.prettyprint.code .atv {
  color: #5485b6;
}

.prettyprint.code .dec {
  color: #b45a3c;
}

.prettyprint.code .var {
  color: #ca4949;
}

.prettyprint.code .fun {
  color: #7272ca;
}

.prettyprint.code.lang-md * {
  color: #655d5d;
}

.button--clipboard {
  background-color: #eee;
  background-image: linear-gradient(#fcfcfc, #eee);
  border: 0;
  border-radius: 0;
  fill: #e1e1e1;
  height: 4.2rem;
  padding: 0;
  position: absolute;
  right: 2rem;
  width: 4.6rem;
  z-index: 1;
}

.button--clipboard:focus *,
.button--clipboard:hover * {
  opacity: 0.3;
}

.button--clipboard.tooptip--clipboard:after {
  background: rgba(96, 108, 118, 0.5);
  border-radius: 1rem;
  color: #fcfcfc;
  content: "Copied!";
  display: block;
  font-size: 1.1rem;
  font-weight: 400;
  line-height: 2.5rem;
  padding: 0 0.6rem;
  position: absolute;
  right: 100%;
  text-transform: capitalize;
  top: 50%;
  transform: translate(-0.4rem, -50%);
}

.button--clipboard > * {
  left: 50%;
  position: absolute;
  top: 50%;
  transform: translate(-50%, -50%);
  width: 1.3rem;
}

.showcase-hero {
  border-bottom: 0.1rem solid #f4f5f6;
  max-width: 100%;
  padding-bottom: 7.5rem;
  padding-top: 7.5rem;
  width: 100%;
}

.showcase-hero,
.showcase-share {
  text-align: center;
}

.image--showcase {
  border: 0.1rem solid #f4f5f6;
}

.button--twitter {
  background: #55acee;
  border-color: #55acee;
  color: #fff;
  fill: #fff;
  padding-left: 4rem;
  padding-right: 5rem;
}

.button--twitter .icon--twitter {
  left: -1rem;
  max-width: 2rem;
  position: relative;
  top: 0.6rem;
}

.subscribe-column {
  max-width: 41% !important;
}

.subscribe-input {
  border-bottom-right-radius: 0 !important;
  border-right: 0;
  border-top-right-radius: 0 !important;
  margin: 0;
}

.subscribe-button {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
  margin: 0;
}

.carbonads {
  background-color: #f4f5f6;
  border-radius: 4px;
  color: #606c76;
  line-height: 1.6;
  margin: 0 auto;
  margin-bottom: 2rem;
  max-width: 33rem;
  padding: 1.5rem;
}

.carbonads,
.carbonads span {
  display: block;
  overflow: hidden;
}

.carbonads .carbon-poweredby,
.carbonads .carbon-text {
  color: #606c76;
  display: block;
  float: right;
  font-size: 1.2rem;
  max-width: 44%;
  text-align: left;
  width: 44%;
}

@media (min-width: 40rem) {
  .carbonads .carbon-poweredby,
  .carbonads .carbon-text {
    max-width: 52%;
    width: 52%;
  }
}

.carbonads .carbon-poweredby {
  margin: 0;
  margin-top: -2.5rem;
}

.carbonads .carbon-img {
  float: left;
  margin-right: 1rem;
}

#home .carbonads {
  background-color: #fff;
  margin-bottom: 0;
}

.example {
  margin-bottom: 4rem;
  margin-top: 4rem;
  position: relative;
}

.example .example-header {
  font-weight: 600;
  margin-top: 1.5rem;
}

.example h1,
.example h2,
.example h3,
.example h4,
.example h5,
.example h6 {
  margin-bottom: 1rem;
}

.example form {
  margin-bottom: 0;
}

.example .heading-font-size {
  color: #999;
  font-size: 1.2rem;
  letter-spacing: normal;
}

.example .button-black {
  background-color: #000;
  border-color: #000;
}

.example .button-black.button-clear,
.example .button-black.button-outline {
  background-color: transparent;
  color: #000;
}

.example .button-black.button-clear {
  border-color: transparent;
}

.example .button-large {
  font-size: 1.4rem;
  height: 4.5rem;
  line-height: 4.5rem;
  padding: 0 2rem;
}

.example .button-small {
  font-size: 0.8rem;
  height: 2.8rem;
  line-height: 2.8rem;
  padding: 0 1.5rem;
}

.example .column-demo {
  background: #d1d1d1;
  border-radius: 0.4rem;
  display: block;
  font-size: 1rem;
  font-weight: 600;
  height: 3rem;
  letter-spacing: 0.1rem;
  line-height: 3rem;
  margin-bottom: 2.5rem;
  text-align: center;
  text-transform: uppercase;
}

.example .container {
  padding-left: 0;
  padding-right: 0;
}

.example.row,
.example .row {
  margin-bottom: 0;
}
</style>
