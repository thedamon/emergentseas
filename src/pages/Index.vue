<template>
<div class="homepage">
  <header class="site-intro" :class="{showInfo: showInfo}">
    <h1>emergent<wbr><span>⋅</span>seas</h1>
    <p class="tagline">
      <!-- creating original,
      undisciplined 
      performances, expressions
      and collaborations -->
      theatre &nbsp; art &nbsp; performance <br>&nbsp;or whatever
      <br>
      <span>original, collaborative, undisciplined</span>
    </p>
    <button :class="{on: showInfo}" @click="toggleInfo" aria-label="what was that? tell me more.">{{ showInfo ? 'shhh! ^':'????? ⌄' }}</button>
      <div v-if="showInfo" :style="{color: 'fff'}">
        <p>
          We're a pretty slow paced group of word, movement and theatre artists making stuff as life allows.
        </p>
        <p>
          We focus on creating new works, punching tradition, and we delight in finding practitioners from other fields to collaborate with.
        </p>
        <p>
          We are based in London, Ontario.
        </p>
      </div>
  </header>
  <main>
  <section class="work">
    <h2 class="section-title">Work</h2>
    <ul class="item-list-work">
      <li class="box">
        <h3 class="item-title">My Planet and Me</h3>
        <p>A speculative solo performance about a disaffected young man who believes he has been contacted by a sentient planet.</p>
        <ul class="version-list">
          <li><a href="./my-planet-fringe">at 2017 London Fringe</a></li>
          <li><a href="./my-planet-aeolian">Aeolian Hall collaborative redux</a></li>
          <li><a href="https://www.youtube.com/watch?v=lYFZSF-NJiM">Short film</a></li>
        </ul>
      </li>
      <li class="box">
        <h3 class="item-title">The Dramatic Weather Agency</h3>
        <p>An interactive animated poem, illustrated by <a href="http://ahpi.ca">Antony Hare</a>.</p>
        <!-- <a href="/dramatic-weather-unit">Visit project</a> -->
        <p><em>2019ish</em></p>
      </li>
    </ul>
  </section>

  <section class="team">
    <h2 class="section-title">Team</h2>
    <ul class="item-list-team box">
      <li>Kristin Bennett</li>
      <li>Cara Moyer</li>
      <li>Damon Muma</li>
    </ul>
  </section>
  <section class="words">
    <h2 class="section-title">Words</h2>
    <ul class="item-list-words box">
      <li><em>En route.</em></li>
    </ul>
  </section>

</main>
  <footer>
    <p class="small">
      site copyright and designed rights deserved etc etc
    </p>
  </footer>
  </div>
</template>

<script>
export default {
  metaInfo: {
    title: 'EmergentSeas',
    htmlAttrs: {
      class: 'index' 
    }
  },
  data(){
    return {
      showInfo: false
    }
  },

  methods: {
    toggleInfo: function(){
      this.showInfo = !this.showInfo
    }
  },
  mounted(){
    var h = document.documentElement,
      b = document.body,
      st = 'scrollTop',
      sh = 'scrollHeight',
      scroll;

    const setScrollVars = function() {
      scroll = (h[st]||b[st]) / ((h[sh]||b[sh]) - h.clientHeight);
      document.documentElement.style.setProperty('--scroll', scroll );
      document.documentElement.style.setProperty('--scrollPct', scroll * 100 + '%' );
    }

    document.addEventListener('scroll', setScrollVars);
    setScrollVars();


    document.addEventListener("mousemove", (e) => {
      document.documentElement.style.setProperty('--mouseX', e.clientX + "px");
      document.documentElement.style.setProperty('--mouseXPct', e.clientX / window.innerWidth);
      document.documentElement.style.setProperty('--mouseY', e.clientY + "px");
    });

    if (window.DeviceOrientationEvent) {
      window.addEventListener('deviceorientation', function(e){
        document.documentElement.style.setProperty('--mouseXPct', e.gamma/1.8+50);
      });
    }

  }
}
</script>


<style lang="scss">

html {
  background: rgba(89, 104, 107, 1);

&.index body {
    font-size: 18px;
    @media (min-width: 500px) {
      font-size: 20px;
    }
    margin: 0;
    padding: 0;
    --mousetate: calc((var(--mouseXPct) - .5) * 10);
    background: linear-gradient(
      calc( var(--mousetate) * 5deg),
      rgba(0, 0, 0, 1) 0%,
      rgb(50, 50, 80) 0%,
      rgba(89, 104, 107, 1) 100%
    );
    min-height: 100vh;
    position: relative;
    padding-bottom: 40px;
    color: rgba(255, 255, 255, 0.445);
    background-attachment: fixed;
    overflow-x: hidden;
  }
}
</style>
<style lang="scss" scoped>
/* some variables for y'all */

$font-fam-base: "PT Serif", 'Times New Roman', Times, serif;
$font-fam-display: "Open Sans", Helvetica, Arial, sans-serif;


/* basic reset and typo */
ul {
  margin: 0;
  padding-left: 1em;
}



h1, h2, h3, h4, h5 {
  font-family: $font-fam-display;
}

p, li {
  font-family: $font-fam-base; 
}


a {
  color: rgba(255, 255, 255, 0.7);
  display: inline-block;

  &:hover {
    color: rgba(255, 255, 255, 0.85);
  }
}

// gimme a griddy thing:

.homepage {
  overflow-x: hidden;
  @media (min-width: 900px) {
    display: grid;
    // grid-auto-columns: minmax(600px, auto);
    // grid-template-columns: 1fr 1fr;

    grid-template-columns: repeat(auto-fit, minmax(580px, 1fr));
    grid-gap: 50px;
  }
}


.site-intro {
  top: 50px;
  left: calc(10vw + 5px);
  width: calc(400px + 2vw);
  max-width: calc(90vw - 36px);
  position: relative;
  align-self: start;

  
  &:before {
    content: "";
    position: absolute;
    width: 140%;
    height: 140%;
    left: -10%;
    top: -10%;
    opacity: .8;
    background: linear-gradient(4deg, black 0%, #202033 80%);
    clip-path: polygon(7% 8%, 100% 0%, 89% 99%, 0% 84%);
    z-index: 0;
    transition: clip-path 1s;
  }

  &.showInfo:before {
    clip-path: polygon(3% 9%, 100% 0%, 82% 100%, 2% 84%);
  }



  > * {
    z-index: 1;
    position: relative;
  }
}

h1 {
  font-size: calc(30px + 5vw);
  width: calc(90vw - 15px);
  color: rgba(138, 237, 255, 0.7);
  margin: 0;
  margin-left: 10px;
  margin-bottom: 10px;
  text-shadow: -2px 2px 0px #bbc;
  position: relative;
  z-index: 2;
}

h2 {
  text-transform: uppercase;
  font-size: 20px;
  letter-spacing: 3px;
  font-weight: normal;
  color: #fff;
  opacity: 0.5;
  // 36-72-108

  // -(36*.75 + (.25 * --scroll))
  // font-size: calc((var(--scroll) * 25 * 36px * 75)/100);
  --n1: -36px;
  --n2: -72px;
  --n3: -108px;

// this works simply nicely.
  --offset1: calc( var(--n1) * .75 + var(--n1) * var(--scroll));
  --offset2: calc( var(--n2) * .75 + var(--n2) * var(--scroll));
  --offset3: calc( var(--n3) * .75 + var(--n3) * var(--scroll));


// the whatup?

// --offset1: calc((var(--n1) * .5) + (--var(--scroll) * 1 * var(--n1)));
// --offset2: calc((var(--n2) * .5) + (--var(--scroll) * 1 * var(--n2)));
// --offset3: calc((var(--n3) * .5) + (--var(--scroll) * 1 * var(--n3)));


  text-shadow: 0px var(--offset1) 2px, 0px var(--offset2) 4px, 0px var(--offset3) 8px;
}

h3 {
  margin: 0;
  font-size: 24px;
  @media (min-width: 500px) {
    font-size: 36px;
  }
  font-weight: bold;
  color: #ff6ed0ab;
  text-shadow: 1px 3px 0px rgba(187, 187, 204, 0.892);
  mix-blend-mode: exclusion;
}

.tagline {
  font-size: calc(22px + .5vw);
  margin: 0;
  color: #fff;
  opacity: 0.5;
  // text-transform: uppercase;
  // font-size: calc(16px + .5vw);
  @media (min-width: 500px) {
    margin-left: 26px;
  }
  span {
    font-size: calc(16px + .4vw);
  }
}

section {
  max-width: 700px;
  margin-left: auto;
  margin-right: 40px;
  margin-top: 170px;
  padding-left: 20px;
}

.work {
  margin-top: 240px;
}

.box {
  max-width: 500px;
  border-radius: 2px;
  padding: 16px;
  // border: 1px solid rgba(255, 255, 255, 0.3);
  // background: linear-gradient(4deg, rgba(0, 0, 0, 1) 0%, rgb(32, 32, 51) 80%);
  position: relative;

  &:before {
    content: "";
    position: absolute;
    width: 125%;
    height: 140%;
    left: -10%;
    top: -10%;
    opacity: .8;
    background: linear-gradient(4deg, black 0%, #202033 80%);
    clip-path: polygon(4% 11%, 93% 7%, 90% 87%, 6% 83%);
    z-index: -1;
  }
}

[class^='item-list'] {
  list-style: none;
  padding: 0;
  opacity: 0.9;
}
.item-list-work > li {
  color: rgba(255, 255, 255, 0.5);
  
  margin-bottom: 40px;
}

.item-list-team {
  
  left: -40px;
  position: relative;
  padding: 4px 36px;
  padding-right: 0px;

  &:before {
    clip-path: polygon(2% 2%, 94% 13%, 44% 99%, 7% 86%);
  }
}

.item-list-team > li {
  margin: 18px 0;
  text-shadow: 1px 3px 0px rgba(187, 187, 204, 0.892);
  color: #1bca7194;
  font-size: 30px;
  font-weight: 600;
  font-family: $font-fam-display;
}

.item-list-words {
  max-width: 250px;
  font-size: 20px;
  padding: 24px 24px;
  text-align: center;
  opacity: 0.7;
}

footer {
  position: absolute;
  bottom: 0;
  color: rgba(255, 255, 255, 0.5);
  margin: 0 10px;
  font-size: 12px;
}

button {
  background: transparent;
  border: 1px #ccc solid;
  color: #ccc;
  transform: skew(0.02turn, 4deg);
  position: relative;
  transition: transform .5s;
  opacity: .75;
  cursor: pointer;

  &:before{
      position:absolute;
      content:'';
      top:-10px;
      right:-10px;
      left:-10px;
      bottom:-10px;
  }

  &:focus,
  &:hover {
    outline: none;
    box-shadow: 0px 0px 0px 2px #000, 0px 0px 0px 3px #ccc;
  }
  &:hover {
    transform: skew(0.06turn, -10deg) scale(1.05);
    opacity: 1;
  }
  &.on {
    transform: skew(0.06turn, -10deg);

    // &:hover {
    //   transform: skew(0.02turn, 4deg);
    // }
  }
}
</style>
