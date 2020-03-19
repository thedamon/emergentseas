<template>
  <div class="writing">
    <main>
      <header>
        <a class="back" href="/">← back</a>
        <p>
          <em>My planet & Me</em>
        </p>
        <h1>
          <del>Excerpt</del>
        </h1>
      </header>
      <p>You know, when I was growing up, it never did occur to me to wonder what I would do if I was the point of first contact for extra-terrestrial intelligence.</p>
      <p>Maybe you neither. It’s kind of a weird thing to wonder about.</p>
      <p>But maybe you should. Because… What do you do in that situation? I guess it depends. If we’re being honest… probably you die immediately. Or die slowly. Or die but think you’re still alive because your consciousness has been stored in a computer made out of animal fat.</p>
      <p>Really, this is such a case-by-case scenario that you might as well just wing it. But… at the risk of sounding like “That Crazy Guy At The Party”. Well. Are you sitting down? Yeah you are! Love it!</p>
      <p>Well.</p>
      <p>I. Me. Regular Joe Schmoe. An inconsequential lower middle class white dude from a backwater Ontario citytown. Yeah That Guy.</p>
      <p>I.</p>
      <p>Was the point of first contact for extra-terrestrial intelligence.</p>
      <p>It’s a claim to fame I’ve kept quiet about because… it really screwed me up in a variety of good ways and bad ways. And because I have literally no proof and no reason for you to believe anything that I say.</p>
      <p>Except that it’s true. And I’m not insane.</p>
      <p>Promise.</p>
      <p>I mean.. if I was lying, I would be smart enough not be this pre-emptively defensive… right?</p>
      <p>But so this extra-terrestrial intelligence that made first contact with me turns out to be an entire sentient planet SO impossibly far away that the light from her star will never reach the Earth.</p>
      <p>Yeah.</p>
      <p>So I’m a guy who talks to a planet.</p>
      <p>
        <em>The music comes. FOOOOOOOP. 🤓 contorts into a position and holds it until the music ends, at which point he awkwardly regains a sort of normal standing stance.</em>
      </p>
      <p>Ok. Ok. THERE!. Right? Yeah? Ok now do you believe me?</p>
      <p>No! that was not performance art.</p>
      <p>It was her. It was the planet. Communicating with me.</p>
      <p>I guess it was a bit weird. Well looked weird. Did it look weird? I kinda get preoccupied when it’s…</p>
      <p>You don’t seem convinced. But you should be embracing this shit.</p>
      <p>What do I need to do?</p>
      <p>If I told you over and over and over for an hour that it’s true would you believe me?</p>
      <p>Ok now we’re getting somewhere.</p>
      <p>So I talk to this planet.</p>
      <p>
        OOooooooh. You’re saying. But Oooooo. You’re too smart for this. You’ve got your own ideas. Like. OOoooo. Like it’s probably just that I have a tumour in my brain. And it’s killing me. And…
        <em>Spoiler ALERT</em> I’ve personified the way it wrecks my nervous system into this dream that I’m special and a telepathic planet has chosen me to receive its messages.
        <em>Plot TWISssssT</em>
      </p>
      <p>But that’s not true. That can’t be true.</p>
      <p>Because if she got taken away from me. I don’t… I don’t know if I could handle that.</p>
      <a class="back" href="/">← back</a>
    </main>
  </div>
</template>
<script>
export default {
  metaInfo: {
    titleTemplate: "EmergentSeas",
    htmlAttrs: {
      class: "writing"
    }
  }
};
</script>
<style lang="scss">
html.writing {
  background: rgba(89, 104, 107, 1);

  body {
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
    color: rgba(255, 255, 255, 0.745);
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
  color: rgba(255, 255, 255, 0.5);
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

.back {
  text-decoration: none;
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

main {
  max-width: 500px;
  border-radius: 2px;
  padding: 16px;
  margin: 0 auto;
  // border: 1px solid rgba(255, 255, 255, 0.3);
  // background: linear-gradient(4deg, rgba(0, 0, 0, 1) 0%, rgb(32, 32, 51) 80%);
  position: relative;
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
</style>
