<template>
<div>
  <header class="site-intro">
    <h1>emergent<wbr>.seas</h1>
    <p class="tagline">
      creating original,
      undisciplined 
      performances, expressions
      and collaborations
    </p>
  </header>
  <section class="work">
    <h2 class="section-title">Work</h2>
    <ul class="item-list-work">
      <li class="box">
        <h3 class="item-title">My Planet and Me</h3>
        <p>A speculative solo performance about a disaffected young man who believes he has been contacted by a sentient planet.</p>
        <ul class="version-list">
          <li><a href="./my-planet-fringe">at 2017 London Fringe</a></li>
          <li><a href="./my-planet-aeolian">Aeolian Hall collaborative redux</a></li>
          <li><a href="./my-planet-film">Short film</a></li>
        </ul>
      </li>
      <li class="box">
        <h3 class="item-title">The Dramatic Weather Unit</h3>
        <p>An interactive animated poem, illustrated by Antony Hare.</p>
        <!-- <a href="/dramatic-weather-unit">Visit project</a> -->
        <p><em>Coming soon.</em></p>
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
    title: 'EmergentSeas'
  }
}
</script>

<style lang="scss">
/* some variables for y'all */

$font-fam-base: "PT Serif", 'Times New Roman', Times, serif;
$font-fam-display: "Open Sans", Helvetica, Arial, sans-serif;


/* basic reset and typo */
ul {
  margin: 0;
  padding-left: 1em;
}

body {
  font-size: 18px;
  @media (min-width: 500px) {
  font-size: 20px;
  }
}

h1, h2, h3, h4, h5 {
  font-family: $font-fam-display;
}

p, li {
  font-family: $font-fam-base; 
}

/* weird */
html {
  background: rgba(89, 104, 107, 1);

  --something: 0;
}

body {
  margin: 0;
  padding: 0;
  background: linear-gradient(
    0deg,
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

a {
  color: rgba(255, 255, 255, 0.7);
  display: inline-block;

  &:hover {
    color: rgba(255, 255, 255, 0.85);
  }
}

.site-intro {
  top: 50px;
  left: calc(10vw + 5px);
  width: 400px;
  max-width: calc(90vw - 36px);
  position: relative;
  
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
  text-shadow: 0px -36px 2px, 0px -72px 4px, 0px -108px 8px;
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
  font-size: calc(20px + .5vw);
  margin: 0;
  color: #fff;
  opacity: 0.5;
  @media (min-width: 500px) {
    margin-left: 26px;
  }
}

section {
  max-width: 700px;
  margin-left: auto;
  margin-right: 40px;
  margin-top: 160px;
  padding-left: 20px;
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

</style>
