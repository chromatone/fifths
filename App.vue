<script setup>
import { ref } from 'vue';
import { version } from './package.json'

import CircleOfFifths from './components/CircleOfFifths.vue';

const started = ref(false)
</script>

<template lang="pug">
.flex.flex-col.items-start.transition-all.duration-500.ease-out.select-none.rounded-8.shadow-xl.w-full.h-full.text-white.flex-1

  .bg-dark-800.bg-op-40.p-2.text-light-800.flex.gap-2.items-center.flex-wrap.w-full.h-full

    CircleOfFifths.h-full.w-full

    article.rounded-xl.shadow-xl.z-1000.fixed.top-2.left-2.right-2.bottom-2.p-8.flex.flex-col.gap-6.bg-dark-800.bg-op-50.backdrop-blur.select-text.overflow-y-scroll(v-if="!started" )
      a.absolute.top-8.right-8.flex.gap-1.items-center.no-underline(href="https://github.com/chromatone/fifths/" target="_blank")
        .i-la-github
        span v.{{ version }}

      a.font-bold.no-underline.flex.items-center.gap-1(href="https://chromatone.center" target="_blank")
        img(src="/logo.svg" width="30" height="30")
        h1.text-xl Chromatone
      h2.text-4xl Circle of Fifths
      h2.text-2xl.max-w-25ch Interactive circle of fifths as composition tool and performance instrument. A tool to explore chords in tonal space.
      button.max-w-30ch.p-2.bg-light-800.hover-bg-light-100.transition.text-dark-800.text-2xl.rounded-2xl.shadow-lg(@click="started = true") START

      .flex.flex-wrap.gap-4(style="flex: 1 1 300px")
        .text-sm.max-w-55ch.prose.text-white
          p The circle of fifths organizes pitches in a sequence of perfect fifths, generally shown as a circle with the pitches (and their corresponding keys) in a clockwise progression. Musicians and composers often use the circle of fifths to describe the musical relationships between pitches. Its design is helpful in composing and harmonizing melodies, building chords, and modulating to different keys within a composition. 

          p Moving counterclockwise, the pitches descend by a fifth, but ascending by a perfect fourth will lead to the same note an octave higher (therefore in the same pitch class). Moving counter-clockwise from C could be thought of as descending by a fifth to F, or ascending by a fourth to F.

          p Here we have two circles of fifths rotated by a minor third interval. With this placement we get quite a useful tool. Considering each position of the circle as a scale we instantly get two parallel major and minor keys. It has the same notes, but start from another tonic and have the opposite tonal quality. Take C major and get A minor. Take C# minor and get E major at one glimpse.

          p The highlighted sector of 90 degrees includes 6 points of the circle that represent 6 main degrees of the scale starting from the notes in the middle of the sector. You can choose either major or minor basic scale by pressing on the little circles outside or inside the rings. Choose the one on the outside and you'll get the scale degrees numbers for the major scale. On the outer circle to the left of it you find the IV degree - the subdominant – the major chord starting from the note a fourth apart from the tonic. To the right lays the dominant V major chord. The inner circle shows the minor chords of the major scale – the ii, the vi and the iii degrees show in a clockwise succession. The vi diminished chord of a major scale isn't shown in the main sector, but you can find a reminder of it one step to the right in the inner circle.

          p So for C major scale you'll get C major chord as the tonic I degree, F major to the left as the IV subdominant degree, and G major chord as the dominant V degree to the right of the tonic. The inner circle will show you the Dm chord for the ii degree, Am as the vi degree and the tonic of the parallel minor scale and Em as the iii degree of the C major scale. The next step of the inner circle shows Bm and it can represent the vi degree – the leading tone and its diminished chord Bdim (Bb5).

          p This scheme helps find interesting chord progressions either in one predefined key or traversing different keys in complex modulation movements. Neighbouring sectors include scales that are easy to borrow chords from and to travel to with simple moves like common-chord modulation. Once you find any other path from one key to another you can trace its form on the circle and transpose it to any key you're in or you want to move to.     

        .flex.flex-col.gap-2(style="flex: 1 1 300px")
          .text-xl.font-bold.py-2 Install this web-app for offline use!
          .max-w-55ch This Progressive Web-Application can be installed and used just like a regular app on your mobile or desktop platform.
          .flex.flex-col.gap-4.max-w-55ch
            .p-0
              i.i-la-apple.inline-block.text-lg
              | <b>iOS</b>: Open this page in Safari, tap the 
              i.i-ic-round-ios-share.inline-block
              |   "Share" button, then select 
              i.i-material-symbols-add-box-outline-rounded.inline-block
              |   "Add to Home Screen" action down in the list.
            .p-0 
              i.i-la-android.inline-block.text-lg
              | <b>Android</b>: Open this page in Chrome, tap the menu button 
              i.i-la-ellipsis-v.inline-block
              |  (three dots), then select "Add to Home Screen".
            .p-0 
              i.i-la-apple.inline-block.text-lg
              |  <b>macOS</b>: Open this page in Safari, click the 
              i.i-ic-round-ios-share.inline-block
              |  "Share" button, then select 
              i.i-f7-rectangle-dock.inline-block
              |  "Add to Dock" action in the list.
            .p-0  
              i.i-la-windows.inline-block.text-lg
              | <b>Windows</b>: Open this page in Edge, click the "Settings and more" button 
              i.i-la-ellipsis-h.inline-block
              |  (three dots), then select "Apps" > "Install this site as an app".
  

</template>

<style lang="postcss">
#app {
  @apply w-full flex flex-col min-h-100svh;
}

a {
  @apply underline;
}

html {
  @apply min-h-100svh;
}

html,
body {
  @apply flex items-stretch justify-stretch min-h-100svh;
  background-color: #444;
  width: 100%;
  line-height: 1.3;
  font-family: "Commissioner", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, Oxygen, Ubuntu, Cantarell, "Fira Sans", "Droid Sans",
    "Helvetica Neue", sans-serif;
  font-size: 1em;
  font-weight: 400;
  color: var(--c-text);
  direction: ltr;
  font-synthesis: none;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overscroll-behavior: none;
  touch-action: pan-y;
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
}
</style>
