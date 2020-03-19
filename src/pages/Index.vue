<template>
  <div class="homepage">
    <header class="site-intro" :class="{showInfo: showInfo}">
      <!--prettyhtml-ignore-->
      <h1>
        emergen<span class="t">t</span><wbr /><span class="dot" aria-hidden>⋅</span>seas
      </h1>
      <p class="tagline">
        <!-- creating original,
      undisciplined 
      performances, expressions
        and collaborations-->
        theatre &nbsp; art &nbsp; performance
        <br />&nbsp;or whatever
        <br />
        <span>original, collaborative, undisciplined</span>
      </p>
      <button
        :class="{on: showInfo}"
        @click="toggleInfo"
        aria-label="what was that? tell me more."
      >{{ showInfo ? 'shhh! ^':'????? ⌄' }}</button>
      <div v-if="showInfo" :style="{color: 'fff'}">
        <p>We're a pretty slow paced group of word, movement and theatre artists making stuff as life allows.</p>
        <p>We focus on creating new works, punching tradition, and we delight in finding practitioners from other fields to collaborate with.</p>
        <p>We are based in London, Ontario.</p>
      </div>
    </header>
    <main>
      <section class="work">
        <h2 class="section-title">Work</h2>
        <ul class="item-list-work">
          <li class="box">
            <h3 class="item-title">My Planet and Me</h3>
            <p class="deets">solo theatre</p>
            <p>A demoralized millennial's strange behaviour, he believes, is the result of being contacted telepathically by a distant sentient planet. Should he tell his girlfriend? Will anyone believe him? An exploration of love, loss and ego from one psyche across many galaxies.</p>
            <p class="deets">written and performed by Damon Muma</p>
            <p class="deets">directed by Cara Moyer and Kristin Bennett</p>
            <br />
            <ul class="version-list">
              <li>
                <a href="./my-planet-fringe">London Fringe (2017)</a>
                <p class="deets">featuring original music by Wormwood</p>
              </li>
              <li>
                <a href="./my-planet-aeolian">Aeolian Hall special presentation (2018)</a>
                <p
                  class="deets"
                >featuring live modular synth soundtrack by Timothy Glasgow, dance by Public Displays of Art, and light sculptures by Matthew Trueman</p>
              </li>
              <li>
                <a href="https://www.youtube.com/watch?v=lYFZSF-NJiM">Trailer/Short film</a>
                <p class="deets">directed by Matt Dupont</p>
              </li>

              <li>
                <a href="./my-planet-excerpt">Not really an excerpt</a>
              </li>
            </ul>
          </li>
          <li class="box">
            <h3 class="item-title">The Dramatic Weather Agency</h3>
            <p>
              An interactive animated poem, illustrated by
              <a href="http://ahpi.ca">Antony Hare</a>.
            </p>
            <!-- <a href="/dramatic-weather-unit">Visit project</a> -->
            <p>
              <em>Coming May 2020.</em>
              <a href="https://twitter.com/DrmatcWthrAgncy">
                <svg class="tweetster" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M8.3 20.3A11.6 11.6 0 0020 8c.8-.5 1.4-1.3 2-2-.7.3-1.5.5-2.4.6.9-.5 1.5-1.4 1.8-2.3-.8.5-1.6.8-2.6 1a4.1 4.1 0 00-7 3.7C8.6 9 5.5 7.3 3.4 4.7c-1.1 2-.5 4.3 1.3 5.5a4 4 0 01-1.9-.5c0 2 1.4 3.7 3.3 4-.6.3-1.2.3-1.9.2.6 1.6 2.1 2.8 3.9 2.8A8.2 8.2 0 012 18.4c1.9 1.2 4 1.9 6.3 1.9"
                  />
                </svg>
              </a>
            </p>
          </li>
        </ul>
      </section>

      <section class="team">
        <h2 class="section-title">Peeps</h2>
        <ul class="item-list-team box">
          <li>Kristin Bennett</li>
          <li>Cara Moyer</li>
          <li>Damon Muma</li>
        </ul>
      </section>
      <!-- <section class="words">
        <h2 class="section-title">Words</h2>
        <ul class="item-list-words box">
          <li>
            <em>En route.</em>
          </li>
        </ul>
      </section>-->
    </main>
    <footer>
      <p class="small">site copyright and designed rights deserved year of twenty whatever etc etc</p>
    </footer>
  </div>
</template>

<script>
export default {
  metaInfo: {
    titleTemplate: "EmergentSeas",
    htmlAttrs: {
      class: "index"
    }
  },
  data() {
    return {
      showInfo: false
    };
  },

  methods: {
    toggleInfo: function() {
      this.showInfo = !this.showInfo;
    }
  },
  mounted() {
    var h = document.documentElement,
      b = document.body,
      st = "scrollTop",
      sh = "scrollHeight",
      scroll;

    const setScrollVars = function() {
      scroll = (h[st] || b[st]) / ((h[sh] || b[sh]) - h.clientHeight);
      document.documentElement.style.setProperty("--scroll", scroll);
      document.documentElement.style.setProperty(
        "--scrollPct",
        scroll * 100 + "%"
      );
    };

    document.addEventListener("scroll", setScrollVars);
    setScrollVars();

    document.addEventListener("mousemove", e => {
      document.documentElement.style.setProperty("--mouseX", e.clientX + "px");
      document.documentElement.style.setProperty(
        "--mouseXPct",
        e.clientX / window.innerWidth
      );
      document.documentElement.style.setProperty("--mouseY", e.clientY + "px");
    });

    if (window.DeviceOrientationEvent) {
      window.addEventListener("deviceorientation", function(e) {
        // this is somewhat arbitrary,
        // but the rotation is much less visible with less of the gradient visible
        document.documentElement.style.setProperty(
          "--mouseXPct",
          (e.gamma / 1.8 + 50) / 10
        );
      });
    }
  }
};
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
    --mousetate: calc((var(--mouseXPct) - 0.5) * 10);
    background: linear-gradient(
      calc(var(--mousetate) * 5deg),
      rgba(0, 0, 0, 1) 0%,
      rgb(50, 50, 80) 0%,
      rgba(89, 104, 107, 1) 100%
    );
    min-height: 100vh;
    position: relative;
    padding-bottom: 40px;
    color: rgba(255, 255, 255, 0.545);
    background-attachment: fixed;
    overflow-x: hidden;
  }
}

:root {
  --mouseXPct: 0.5;
}
</style>
<style lang="scss" scoped>
/* some variables for y'all */

$font-fam-base: "PT Serif", "Times New Roman", Times, serif;
$font-fam-display: "Open Sans", Helvetica, Arial, sans-serif;

/* basic reset and typo */
ul {
  margin: 0;
  padding-left: 1em;
}

h1,
h2,
h3,
h4,
h5 {
  font-family: $font-fam-display;
}

p,
li {
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
  // overflow-x: hidden;
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
  width: 80vw;
  position: relative;
  align-self: start;
  @media (min-width: 500px) {
    width: calc(400px + 2vw);
    max-width: calc(90vw - 36px);
  }

  &:before {
    content: "";
    position: absolute;
    width: 140%;
    max-width: 95vw;
    height: 140%;
    left: -10%;
    top: -10%;
    opacity: 0.8;
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

  .t,
  .dot {
    letter-spacing: -1vw;
  }
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
  --offset1: calc(var(--n1) * 0.75 + var(--n1) * var(--scroll));
  --offset2: calc(var(--n2) * 0.75 + var(--n2) * var(--scroll));
  --offset3: calc(var(--n3) * 0.75 + var(--n3) * var(--scroll));

  text-shadow: 0px var(--offset1) 2px, 0px var(--offset2) 4px,
    0px var(--offset3) 8px;
}

h3 {
  margin: 0;
  font-size: 24px;
  text-shadow: 1px 2px 0px rgba(187, 187, 204, 0.892);
  font-weight: normal;
  color: #ff6ed0ab;
  mix-blend-mode: exclusion;
  @media (min-width: 500px) {
    font-size: 36px;
    text-shadow: 1px 3px 0px rgba(187, 187, 204, 0.892);
  }
}

.tagline {
  font-size: calc(22px + 0.5vw);
  margin: 0;
  color: #fff;
  opacity: 0.5;
  // text-transform: uppercase;
  // font-size: calc(16px + .5vw);
  @media (min-width: 500px) {
    margin-left: 26px;
  }
  span {
    font-size: calc(16px + 0.4vw);
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
    max-width: 100vw;
    height: 140%;
    left: -6%;
    top: -10%;
    opacity: 0.8;
    background: linear-gradient(4deg, black 0%, #202033 80%);
    clip-path: polygon(4% 11%, 93% 7%, 90% 87%, 6% 83%);
    z-index: -1;
  }
}

[class^="item-list"] {
  list-style: none;
  padding: 0;
  opacity: 0.9;
}
.item-list-work > li {
  color: rgba(255, 255, 255, 0.5);

  margin-bottom: 40px;
}

.deets {
  font-size: 16px;
  margin: 4px 0;
  font-style: italic;
  line-height: 1.3;
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
  font-weight: 400;
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
  transition: transform 0.5s;
  opacity: 0.75;
  cursor: pointer;

  &:before {
    position: absolute;
    content: "";
    top: -10px;
    right: -10px;
    left: -10px;
    bottom: -10px;
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

.tweetster {
  fill: rgba(255, 255, 255, 0.5);
  top: 5px;
  width: 30px;
  position: relative;
  &:hover {
    fill: rgba(255, 255, 255, 0.7);
    filter: drop-shadow(0px 0px 4px rgba(255, 255, 255, 0.7));
  }
}
</style>
