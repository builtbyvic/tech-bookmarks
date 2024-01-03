<script>
  import { slide } from 'svelte/transition';
  function toggleMenu(index) {
    cards[index].isOpen = !cards[index].isOpen;
  }
  // data
  let cards = [
    {
      "🎨 I just want to Design": [{'Figma':'figma.com'},{'Laws of UX': 'lawsofux.com'},{'Apple Human Interface Guidelines':'developer.apple.com/design/human-interface-guidelines/'},{'Material Design by Google':'m3.material.io'},{'Design Checklist':'checklist.design'},{'Awwwards':'awwwards.com'},{'Dribbble':'dribbble.com'},{'Pinterest':'pinterest.com'},{'Branding Style Guides':'brandingstyleguides.com/guide'},{'Layers':'layers.to/layers/discover'},{'Image Color Picker':'imagecolorpicker.com'},{'Figma Design Resources':'figma.com/resources/learn-design/'}],
      id: 1,
      isOpen: false,
    },
    {
      "🧑🏿‍💻 I want to be a Web Developer (Basic HTML & CSS)": [{'Getting Started':'builtbyvic.github.io'},{'Mozilla Web Docs':'developer.mozilla.org/en-US/docs/Web/HTML'},{'web.dev HTML':'web.dev/learn/html'},{'Codecademy HTML':'codecademy.com/learn/learn-html'},{'FreeCodeCamp HTML':'freecodecamp.org/news/html-crash-course/'},{'W3Schools HTML':'w3schools.com/html'},{'HTML Elements Reference':'htmlreference.io'},{'web.dev CSS':'web.dev/learn/css'},{'CSS Properties Reference':'cssreference.io'},{'Jennifer Dewalt Challenges':'jenniferdewalt.com'},{'Frontend Mentor':'frontendmentor.io/challenges'},],
      id: 2,
      isOpen: false,
    },
    {
      "😎 I want to be a 10X Web Developer (Advanced)": [{'Grainy Gradients':'css-tricks.com/grainy-gradients/'},{'Components':'components.ai'},{'VisBug':'visbug.web.app'},{'NPM Website':'npmjs.com'},{'Wizard Zines':'wizardzines.com'},{'Bits of Code':'bitsofco.de'},{'Frontend Practice':'frontendpractice.com'},{'I Hate Tomatoes':'ihatetomatoes.net'},{'Google Developers':'developers.google.com'},{'Chrome Developers':'developer.chrome.com'},{'Dev Docs':'devdocs.io'},{'Coding Fantasy':'codingfantasy.com'},{'Git by Atlassian':'atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud'},{'dev.to':'dev.to'},{'chalk.ist':'chalk.ist'},{'Julia Evans':'jvns.ca'}],
      id: 3,
      isOpen: false,
    },
    {
      "🔮 CSS is my Passion": [{'web.dev CSS':'web.dev/learn/css'},{'Uno CSS':'unocss.dev'},{'Una Kravets':'una.im'},{'Lightning CSS':'lightningcss.dev'},{'Can I Use':'caniuse.com'},{'SASS':'sass-lang.com'},{'Minimal SASS site setup':'thinkdobecreate.com/articles/minimum-static-site-sass-setup'},{'Custom CSS Reset':'joshwcomeau.com/css/custom-css-reset/'},{'Josh W. Comeau':'joshwcomeau.com'},{'CSS Examples by Wizard Zines':'css-examples.wizardzines.com/'},{'Responsive Layouts by Kevin Powell':'courses.kevinpowell.co/conquering-responsive-layouts'},{'CSS Layouts':'freebiesupply.com/blog/css-layouts/'},{'Bulma CSS':'bulma.io'},{'30 Seconds of Code':'30secondsofcode.org'},{'Open Props':'open-props.style'},{'Designcember by Google':'designcember.com'},{'TailwindCSS':'tailwindcss.com'},{'Pico CSS':'picocss.com'},{'The CSS Podcast':'pod.link/thecsspodcast/'},{'Every Layout':'every-layout.dev'},{'1 Line Layouts by Una':'1linelayouts.glitch.me'},{'CSS Layout Guide':'smashingmagazine.com/2018/05/guide-css-layout'},{'Grid by Example':'gridbyexample.com'},{'GUI Challenges':'web.dev/shows/gui-challenges/'},{'Designing in the Browser':'web.dev/shows/designing-in-the-browser/'},{'Can I Include (elements)':'caninclude.glitch.me'},{'Flowbite':'flowbite.com'},{'Bootstrap':'getbootstrap.com'},{'Codecademy CSS':'codecademy.com/learn/learn-css'},{'W3Schools CSS':'w3schools.com/css'},{'Mozilla CSS Docs':'developer.mozilla.org/en-US/docs/Web/CSS'},{'nerdy dev':'nerdy.dev'},{'Set Studio':'set.studio'}],
      id: 4,
      isOpen: false,
    },
    {
      "📽️ I'm a Visual Learner (YouTube)": [{'Web Dev Simplified':'youtube.com/c/WebDevSimplified'},{'Traversy Media':'youtube.com/c/TraversyMedia'},{'FreeCodeCamp':'youtube.com/c/Freecodecamp'},{'Programming with Mosh':'youtube.com/c/programmingwithmosh'},{'Dev Ed':'youtube.com/c/DevEd'},{'Coder Coder':'youtube.com/c/TheCoderCoder'},{'Kevin Powell':'youtube.com/kepowob'}],
      id: 5,
      isOpen: false,
    },
    {
      "😔 I have a Sh**ty Laptop (Use REPLs)": [{'Glitch':'glitch.com'},{'CodePen':'codepen.io'},{'VS Code Online':'vscode.dev'},{'Stackblitz':'stackblitz.com'},{'CodeSandbox':'codesandbox.io'},{'Svelte REPL':'svelte.dev/repl/hello-world?version=3.59.1'}],
      id: 6,
      isOpen: false,
    },
    {
      "🤯 I know HTML & CSS, but not JavaScript": [{'Modern JS Tutorial':'javascript.info'},{'W3Schools JS':'w3schools.com/js/'},{'Mozilla JS Docs':'developer.mozilla.org/en-US/docs/Web/JavaScript'},{'Codecademy JS':'codecademy.com/learn/introduction-to-javascript'},{'Wes Bos JS Tutorial':'wesbos.com/javascript'},{'Learn Node JS':'nodejs.dev/en/learn/'}],
      id: 7,
      isOpen: false,
    },
    {
      "😏 I know JavaScript, what Next? (JS Frameworks)": [{'Svelte':'svelte.dev'},{'Vue JS':'vuejs.org'},{'React':'react.dev'},{'Angular':'angular.io'},{'Vue Mastery (Vue)':'vuemastery.com'},{'Vue School (Vue)':'vueschool.io'},{'Formkit (Vue forms)':'formkit.com'},{'TypeScript Deep Dive':'basarat.gitbook.io/typescript/'},{'Astro':'astro.build'},{'TypeScript':'typescriptlang.org'}],
      id: 8,
      isOpen: false,
    },
    {
      "🤖 I want to build Full-Stack Web Apps with Javascript": [{'SvelteKit (Svelte)':'kit.svelte.dev'},{'Nuxt (Vue JS)':'nuxt.com/docs/getting-started/introduction'},{'Next JS (React)':'nextjs.org'},{'Meteor.js':'https://www.meteor.com/'}],
      id: 9,
      isOpen: false,
    },
    {
      "🪄 I want to do Animations with JavaScript": [{'Spline (3D)':'spline.design'},{'Rive':'rive.app'},{'GSAP':'greensock.com'},{'Barba.js (transitions)':'barba.js.org'},{'Three.js (3D)':'threejs.org'},{'Motion One':'motion.dev'},{'Theatre.js':'theatrejs.com'},{'Animate On Scroll':'michalsnik.github.io/aos/'},{'Anime.js':'animejs.com'}],
      id: 10,
      isOpen: false,
    },
    {
      "😭 I don't want to Learn Code": [{'Framer':'framer.com/learn/'},{'Notion':'notion.so/help/guides'},{'Super':'docs.super.so'},{'WordPress':'wordpress.org'},{'Webflow':'webflow.com'},{'Shopify':'https://www.shopify.com/'}],
      id: 11,
      isOpen: false,
    },
    {
      "😁 I like to be guided through Every Step of the Way": [{'Microsoft Learn':'learn.microsoft.com/en-us/'},{'Grow with Google':'grow.google/intl/ssa-en/'}],
      id: 12,
      isOpen: false,
    },
    {
      "☁️ I've made a project, how do I share it with the World?": [{'Vercel':'vercel.com'},{'Firebase':'firebase.google.com'},{'Netlify':'netlify.com'},{'Render':'render.com'},{'Surge':'surge.sh'},{'GitLab':'docs.gitlab.com/ee/user/project/pages/'},{'Super':'super.so/pricing'},{'Github Pages':'pages.github.com'}],
      id: 13,
      isOpen: false,
    },
    {
      "✒️ I don't have Fonts for my project": [{'Google Fonts':'fonts.google.com'},{'I Love Typography':'fonts.ilovetypography.com/'},{'Apple Fonts':'developer.apple.com/fonts/'},{'Adobe Fonts':'fonts.adobe.com'},{'Fontshare':'fontshare.com'},{'Nerd Fonts':'nerdfonts.com/font-downloads'}],
      id: 14,
      isOpen: false,
    },
    {
      "🦉 I need Icons for my project": [{'Iconic':'iconic.app'},{'Heroicons':'heroicons.com'},{'Health icons':'healthicons.org'},{'Icons8':'icons8.com/icons'},{'Iconscout':'iconscout.com'},{'Flat Icon':'flaticon.com'},{'Fontawesome':'fontawesome.com'},{'Openmoji':'openmoji.org/library/'},{'Feathericons':'feathericons.com'},{'Icones':'icones.js.org/collection/solar'}],
      id: 15,
      isOpen: false,
    },
    {
      "🖼️ I need FREE Images for my project": [{'Unsplash':'unsplash.com'},{'Pexels':'pexels.com'}],
      id: 16,
      isOpen: false,
    },
    {
      "⚒️ Developer Tools": [{'ChatGPT':'chat.openai.com'},{'Parcel':'parceljs.org'},{'Vite':'vitejs.dev'},{'Git Docs':'git-scm.com'},{'Plausible Analytics':'plausible.io'},{'JS Visualizer':'jsv9000.app'},{'Learn Git by Atlassian':'atlassian.com/git'},{'Devina DevTools':'devina.io/'},{'Github':'github.com'},{'JSdelivr (CDN)':'jsdelivr.com'},{'NPM website':'npmjs.com'},{'MacOS Package Manager':'brew.sh'},{'Temp Mail':'temp-mail.org/en/'}],
      id: 17,
      isOpen: false,
    },
    {
      "⌨️ Code Editors": [{'VS Code':'code.visualstudio.com/download'},{'Notepad++':'notepad-plus-plus.org/downloads/'},{'Brackets':'brackets.io'},{'Sublime Text':'sublimetext.com'},{'PyCharm':'jetbrains.com/pycharm/'},{'Bootstrap Studio':'bootstrapstudio.io'}],
      id: 18,
      isOpen: false,
    },
    {
      "📰 Content Management Systems": [{'Wordpress CMS':'wordpress.org'},{'Builder.io':'builder.io'},{'Strapi':'strapi.io'}],
      id: 19,
      isOpen: false,
    },
    {
      "📅 Database Systems": [{'Supabase':'supabase.com'}],
      id: 20,
      isOpen: false,
    },
    {
      "📚 Free Programming Books": [{'Goalkicker':'goalkicker.com'}],
      id: 21,
      isOpen: false,
    },
    {
      "🤓 Terminal": [{'Windows Terminal':'github.com/microsoft/terminal'},{'Scoop':'scoop.sh/'},{'Starship (fun)':'starship.rs'},{'iTerm2 (MacOS)':'iterm2.com'}]
    },
    {
      "🔙 If you ever decide to do Back-End": [{'Go':'go.dev'},{'Rust cheats (Rust)':'cheats.rs'}]
    }
  ];
  
</script>

<main>
  <header>
    <nav>
      <a href="/">
        tech~<br id="break"/>bookmarks
        <span></span>
      </a> 
      <span><a href="https://svelte.dev">* made with svelte</a></span>
    </nav>
    <a href="https://builtbyvic.github.io" target="_blank">first time?</a>
  </header>
  <div class="input-wrapper">
    <label for="search">🔎</label>
    <input type="search" id="search" placeholder="Coming Soon..."/>
  </div>
  <section>
    {#each cards as card, index}
      <article>
        <header on:click={()=> toggleMenu(index)}>
          <span class={card.isOpen ? 'rotate' : ''}>
            <svg fill="none" viewBox="0 0 24 24"><path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M15.3 10.8 12 14.2l-3.3-3.4"/></svg>
          </span>
          <h1>{Object.keys(card)[0]}</h1>
        </header>
        {#if card.isOpen}
          <ul transition:slide>
            {#each card[Object.keys(card)[0]] as link}
              <li><a href="https://{Object.values(link)}" target="_blank">{Object.keys(link)}</a></li>
            {/each}
          </ul>
        {/if}
      </article>
    {/each}
  </section>
  <footer>
    <a href="https:github.com/builtbyvic">
      builtbyvic
      <span></span>
    </a>
    <figure>
      <blockquote>"I feel like he disrespected me. Tried to say I wasn't a genius."</blockquote>
      <figcaption>- Kanye West, 2002.</figcaption>
    </figure>
    <span>All rights reserved, 2030 by Vic⚡</span>
  </footer>
</main>

<style>
  main {
    align-items: center;
    display: flex;
    flex-direction: column;
  }
  ::placeholder {
    color: rgba(255 255 255 / 0.5);
    font-size: var(--large);
  }
  a {
    display: inline-block;
    color: currentColor;
    inline-size: 100%;
    text-decoration: none;
  }
  svg {
    block-size: 48px;
    inline-size: 48px;
  }
  h1 {
    margin-block: 0;
  }
  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }
  label {
    cursor: pointer;
  }
  #break {
    display: none;
  }
  main > header {
    margin-block-end: var(--regular);
    align-items: center;
    display: flex;
    gap: var(--xs);
    justify-content: space-between;
  }
  header nav > a {
    display: initial;
    font-size: 3rem;
    font-weight: 700;
    background-image: linear-gradient(to right,#6A359C, #B589D6);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    position: relative;
  }
  header a span {
    background-image: linear-gradient(to right,#6A359C, #B589D6);
  }
  header > a {
    background-color: #000;
    background-image: linear-gradient(to right,#000, rgba(255 255 255 / 0.1));
    border: var(--border-glass);
    border-radius: var(--xs);
    font-size: var(--large);
    inline-size: auto;
    padding: var(--medium) var(--large) var(--medium);
    white-space: nowrap;
  }
  header > a:hover {
    background-image: linear-gradient(to right,rgba(0 0 0 / 0.9),rgba(255 255 255 / 0.2));
  }
  .input-wrapper {
    /* border: 2px solid red; */
    align-items: center;
    display: flex;
    font-size: var(--xxl);
    inline-size: 540px;
    margin-block: var(--large);
  }
  [type="search"] {
    background-color: transparent;
    border: var(--border-glass);
    border-radius: var(--large);
    padding: var(--large);
    inline-size: 100%;
  }
  [type="search"]:focus {
    outline: 1px solid rgba(255 255 255 / 0.2);
  }
  header a span,
  footer a span {
    block-size: 2px;
    display: inline-block;
    inset-inline-start: 0;
    inline-size: 0;
    inset-block-start: 95%;
    position: absolute;
    transition: all 200ms ease-out;
  }
  header a:hover span,
  footer a:hover span {
    inline-size: 100%;
    transition: all 200ms ease-out;
  }
  main header nav > span {
    background-image: linear-gradient(to right,#FF6200, #FDB777);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    font-weight: 600;
    white-space: nowrap;
  }
  article header,
  article ul {
    z-index: 2;
    position: relative;
  }
  article {
    border: var(--border-glass);
    border-radius: var(--xs);
    max-inline-size: 66ch;
    padding: var(--regular);
    position: relative;
  }
  article::after {
    background-color: #000;
    content: "";
    display: block;
    inset: 1px;
    position: absolute;
    z-index: 1;
    transition: opacity .3s ease;
  }
  @property --r2 {
    syntax: '<angle>';
    inherits: false;
    initial-value: 0deg;
  }
  @property --x {
    syntax: '<length>';
    inherits: false;
    initial-value: 0px;
  }
  article:hover {
    background: conic-gradient(from calc(var(--r2) - 80deg) at var(--x) 50px, #222 0%, #fff 20%, #222 25%);
    animation: -0.64s rotating2 3s linear infinite, -0.64s x 3s linear infinite;
  }
  @keyframes x {
    /* w:h === 6:1 */
    /* with a 80px x-margin */
    0% {
      --x: 80px;
    }
    /* 6/(6+3.14) * 50% */
    32.82275711% {
      --x: 520px;
    }
    50% {
      --x: 520px;
    }
    /* 50% + 32.8% */
    82.82275711% {
      --x: 80px;
    }
    100% {
      --x: 80px;
    }
  }
  @keyframes rotating2 {
    0% {
      --r2: 0deg;
    }
    32.82275711% {
      --r2: 0deg;
    }
    50% {
      --r2: 180deg;
    }
    82.82275711% {
      --r2: 180deg;
    }
    100% {
      --r2: 360deg;
    }
  }
  article header {
    align-items: center;
    cursor: pointer;
    display: flex;
  }
  article header span {
    transition: all 200ms ease-in-out;
  }
  article header h1 {
    font-size: var(--xxl);
  }
  ul li:first-child {
    border-block-start: var(--border-glass);
  }
  ul li {
    border-block-end: var(--border-glass);
    font-size: var(--large);
    letter-spacing: 0.05ch;
    overflow-wrap: break-word;
    padding-block: var(--regular);
    transition: all 200ms ease-in-out;
  }
  ul li:last-child {
    border-block-end: none;
  }
  ul li:hover {
    background-color: rgba(136, 136, 136, 0.1);
    padding-inline-start: var(--small);
    transition: all 200ms ease-in-out;
  }
  section {
    display: flex;
    flex-direction: column;
    gap: var(--regular);
    justify-content: center;
    margin-block-end: var(--xl);
  }
  footer {
    text-align: center;
  }
  footer a {
    display: initial;
    font-size: 3rem;
    background-image: linear-gradient(to right,#FF6200, #FDB777);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    position: relative;
  }
  footer a span {
    background-image: linear-gradient(to right,#FF6200, #FDB777);
  }
  figure {
    font-size: var(--large);
  }
  blockquote {
    margin: 0;
  }
  .rotate {
    transform: rotate(180deg);
    transition: all 200ms ease-in-out;
  }
  @media (max-width: 640px) {
    #break {
      display: initial;
    }
    header nav > a {
      font-size: var(--xxl);
    }
    header > a {
      padding: var(--small) var(--regular) var(--small);
      font-size: var(--regular);
    }
    .input-wrapper {
      inline-size: 100%;
    }
    ul li {
      font-size: var(--regular);
    }
    article header h1 {
      font-size: var(--regular);
      text-align: center;
    }
  }
</style>
