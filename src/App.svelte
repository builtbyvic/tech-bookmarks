<script>
  import { slide } from 'svelte/transition';
  function toggleMenu(index) {
    cards[index].isOpen = !cards[index].isOpen;
  }
  // data
  let cards = [
    {
      "🎨 I just want to Design": ['figma.com','lawsofux.com','developer.apple.com/design/human-interface-guidelines/','m3.material.io','checklist.design','awwwards.com','dribbble.com','pinterest.com','brandingstyleguides.com/guide','layers.to/layers/discover','imagecolorpicker.com','figma.com/resources/learn-design/'],
      id: 1,
      isOpen: false,
    },
    {
      "🧑🏿‍💻 I want to be a Web Developer (Basic HTML & CSS)": ['builtbyvic.github.io','developer.mozilla.org/en-US/docs/Web/HTML','web.dev/learn/html','codecademy.com/learn/learn-html','freecodecamp.org/news/html-crash-course/','w3schools.com/html','htmlreference.io','web.dev/learn/css','cssreference.io','jenniferdewalt.com','frontendmentor.io/challenges',],
      id: 2,
      isOpen: false,
    },
    {
      "😎 I want to be a 10X Web Developer (Advanced)": ['css-tricks.com/grainy-gradients/','components.ai','visbug.web.app','npmjs.com','wizardzines.com','bitsofco.de','frontendpractice.com','ihatetomatoes.net','developers.google.com','developer.chrome.com','devdocs.io','codingfantasy.com','atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud','dev.to','chalk.ist','jvns.ca'],
      id: 3,
      isOpen: false,
    },
    {
      "🔮 CSS is my Passion": ['web.dev/learn/css','unocss.dev','una.im','lightningcss.dev','caniuse.com','sass-lang.com','thinkdobecreate.com/articles/minimum-static-site-sass-setup','joshwcomeau.com/css/custom-css-reset/','joshwcomeau.com','css-examples.wizardzines.com/','courses.kevinpowell.co/conquering-responsive-layouts','freebiesupply.com/blog/css-layouts/','bulma.io','30secondsofcode.org','open-props.style','designcember.com','tailwindcss.com','picocss.com','pod.link/thecsspodcast/','every-layout.dev','1linelayouts.glitch.me','smashingmagazine.com/2018/05/guide-css-layout','gridbyexample.com','web.dev/shows/gui-challenges/','web.dev/shows/designing-in-the-browser/','caninclude.glitch.me','flowbite.com','getbootstrap.com','codecademy.com/learn/learn-css','w3schools.com/css','developer.mozilla.org/en-US/docs/Web/CSS','nerdy.dev','set.studio'],
      id: 4,
      isOpen: false,
    },
    {
      "📽️ I'm a Visual Learner": ['youtube.com/c/WebDevSimplified','youtube.com/c/TraversyMedia','youtube.com/c/Freecodecamp','youtube.com/c/programmingwithmosh','youtube.com/c/DevEd','youtube.com/c/TheCoderCoder','youtube.com/kepowob'],
      id: 5,
      isOpen: false,
    },
    {
      "💻 I have a Sh**ty Laptop (Use REPLs)": ['glitch.com','codepen.io','vscode.dev','stackblitz.com','codesandbox.io','svelte.dev/repl/hello-world?version=3.59.1'],
      id: 6,
      isOpen: false,
    },
    {
      "🤯 I know HTML & CSS, but not JavaScript": ['javascript.info','w3schools.com/js/','developer.mozilla.org/en-US/docs/Web/JavaScript','codecademy.com/learn/introduction-to-javascript','wesbos.com/javascript','nodejs.dev/en/learn/'],
      id: 7,
      isOpen: false,
    },
    {
      "😏 I know JavaScript, what Next?": ['svelte.dev','vuejs.org','react.dev','angular.io','vuemastery.com','vueschool.io','formkit.com','basarat.gitbook.io/typescript/','astro.build','typescriptlang.org'],
      id: 8,
      isOpen: false,
    },
    {
      "🤖 I want to build Full-Stack Web Apps with Javascript": ['kit.svelte.dev','nuxt.com/docs/getting-started/introduction','nextjs.org'],
      id: 9,
      isOpen: false,
    },
    {
      "🪄 I want to do Animations with JavaScript": ['spline.design','rive.app','greensock.com','barba.js.org','threejs.org','motion.dev','theatrejs.com','michalsnik.github.io/aos/','animejs.com'],
      id: 10,
      isOpen: false,
    },
    {
      "😭 I don't want to Learn Code": ['framer.com/learn/','notion.so/help/guides','','docs.super.so','wordpress.org','webflow.com'],
      id: 11,
      isOpen: false,
    },
    {
      "😁 I like to be guided through Every Step of the Way": ['learn.microsoft.com/en-us/','grow.google/intl/ssa-en/'],
      id: 12,
      isOpen: false,
    },
    {
      "☁️ I've made a project, how do I share it with the World?": ['vercel.com','firebase.google.com','netlify.com','render.com','surge.sh','docs.gitlab.com/ee/user/project/pages/','super.so/pricing','pages.github.com'],
      id: 13,
      isOpen: false,
    },
    {
      "✒️ I don't have Fonts for my project": ['fonts.google.com','fonts.ilovetypography.com/','developer.apple.com/fonts/','fonts.adobe.com','fontshare.com','nerdfonts.com/font-downloads'],
      id: 14,
      isOpen: false,
    },
    {
      "🦉 I need Icons for my project": ['iconic.app','heroicons.com','healthicons.org','icons8.com/icons','iconscout.com','flaticon.com','fontawesome.com','openmoji.org/library/','feathericons.com','icones.js.org/collection/solar'],
      id: 15,
      isOpen: false,
    },
    {
      "🖼️ I need FREE Images for my project": ['unsplash.com','pexels.com'],
      id: 16,
      isOpen: false,
    },
    {
      "⚒️ Developer Tools": ['chat.openai.com','parceljs.org','vitejs.dev','git-scm.com','plausible.io','jsv9000.app','atlassian.com/git','devina.io/svg-minifier','github.com','jsdelivr.com','npmjs.com','brew.sh','temp-mail.org/en/'],
      id: 17,
      isOpen: false,
    },
    {
      "⌨️ Code Editors": ['code.visualstudio.com/download','notepad-plus-plus.org/downloads/','brackets.io','sublimetext.com','jetbrains.com/pycharm/','bootstrapstudio.io'],
      id: 18,
      isOpen: false,
    },
    {
      "📰 Content Management Systems": ['wordpress.org','builder.io','strapi.io'],
      id: 19,
      isOpen: false,
    },
    {
      "📅 Database Systems": ['supabase.com'],
      id: 20,
      isOpen: false,
    },
    {
      "📚 Free Programming Books": ['goalkicker.com'],
      id: 21,
      isOpen: false,
    },
    {
      "🤓 Terminal": ['github.com/microsoft/terminal','scoop.sh/','starship.rs','iterm2.com']
    },
    {
      "🔙 If you ever decide to do Back-End": ['go.dev','cheats.rs']
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
              <li><a href="https://{link}" target="_blank">{link}</a></li>
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
    <span>All rights reserved, 2040 by Vic⚡</span>
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
