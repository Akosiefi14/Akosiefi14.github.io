# Akosiefi14.github.io
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>True Crime Story</title>
  <style>
    /* Reset and base */
    *, *::before, *::after { box-sizing: border-box; }
    body {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      min-height: 100vh;
      background:
        radial-gradient(ellipse at center, rgba(0,0,0,0.18) 70%, rgba(0,0,0,0.88) 100%),
        url('https://user-gen-media-assets.s3.amazonaws.com/gpt4o_images/f9fd27ff-c892-4c52-91ae-59c358eed635.png') no-repeat center center fixed;
      background-size: cover;
      color: #9acd32;
      text-shadow: 1px 1px 2px rgba(0,0,0,0.4);
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
    }
    header, main, footer {
      background: rgba(0,0,0,0.7);
      max-width: 900px;
      margin: 3rem auto 2rem auto;
      border-radius: 12px;
      box-shadow: 0 12px 32px rgba(0,0,0,0.35);
      padding: 2.5rem 3rem;
      text-align: center;
      color: #9acd32;
    }
    header {
      font-weight: 700;
      font-size: 2.5rem;
      margin-bottom: 2rem;
      user-select: none;
      letter-spacing: 2px;
    }
    .page-buttons {
      display: grid;
      grid-template-columns: 1fr;
      gap: 1.5rem;
      justify-items: center;
      max-width: 320px;
      margin: 0 auto 3rem auto;
    }
    .page-buttons button {
      background: #9acd32;
      color: #003300;
      border: none;
      border-radius: 8px;
      padding: 0.9rem 2.5rem;
      font-size: 1.2rem;
      font-weight: 600;
      cursor: pointer;
      box-shadow: 0 6px 15px rgba(0,51,0,0.35);
      transition: background-color 0.3s ease, box-shadow 0.3s ease;
      width: 100%;
      max-width: 280px;
      letter-spacing: 1px;
      text-shadow: none;
    }
    .page-buttons button:hover,
    .page-buttons button:focus {
      background: #6b8e23;
      box-shadow: 0 8px 20px rgba(50,80,0,0.5);
      outline: none;
      color: #d7ffd9;
    }
    .page-buttons button[aria-selected="true"] {
      background: #6b8e23;
      box-shadow: 0 9px 22px rgba(50,80,0,0.5);
      cursor: default;
      color: #d7ffd9;
    }
    h2 {
      font-size: 2rem;
      margin-bottom: 1.5rem;
      font-weight: 700;
      letter-spacing: 1.2px;
    }
    h3 {
      font-size: 1.5rem;
      margin-bottom: 1rem;
      border-bottom: 2px solid #9acd32;
      padding-bottom: 0.3rem;
    }
    #story {
      background: rgba(0,0,0,0.85);
      border: 2px solid #9acd32;
      border-radius: 10px;
      margin-top: 2rem;
      padding: 2rem;
      box-shadow: 0 6px 20px rgba(0,51,0,0.3);
      text-align: left;
      display: none;
    }
    #story a.continue-btn {
      display: inline-block;
      background: #9acd32;
      color: #003300;
      margin-top: 1.5rem;
      border-radius: 6px;
      padding: 0.75rem 1.75rem;
      font-weight: 700;
      text-decoration: none;
      user-select: none;
      text-shadow: none;
      transition: background-color 0.3s ease;
      box-shadow: 0 4px 10px rgba(0,51,0,0.35);
    }
    #story a.continue-btn:hover,
    #story a.continue-btn:focus {
      background: #6b8e23;
      box-shadow: 0 6px 18px rgba(50,80,0,0.45);
      outline: none;
      color: #d7ffd9;
    }
    img {
      max-width: 100%;
      border-radius: 8px;
      margin-top: 1rem;
      margin-bottom: 1.25rem;
      box-shadow: 0 3px 10px rgba(0,51,0,0.25);
      user-select: none;
    }
    p {
      font-size: 1.1rem;
      margin-bottom: 1rem;
      letter-spacing: 0.02em;
    }
    footer {
      font-weight: 600;
      margin: 3rem auto 2rem auto;
      background: rgba(0,0,0,0.75);
      padding: 1rem 2rem;
      max-width: 900px;
      border-radius: 12px;
      box-shadow: 0 10px 30px rgba(0,51,0,0.5);
      letter-spacing: 1.5px;
      text-align: center;
      user-select: none;
      text-shadow: 1.5px 1.5px 2px rgba(0,0,0,0.6);
      color: #9acd32;
    }
    a {
      color: #9acd32;
      text-decoration: none;
      font-weight: 600;
      transition: color 0.3s;
      text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
    }
    a:hover, a:focus {
      color: #d7ffd9;
      outline: none;
      text-decoration: underline;
      text-shadow: 1.5px 1.5px 3px rgba(0,0,0,0.7);
    }
    section {
      display: none;
      max-width: 900px;
      margin: auto;
      padding: 0 1rem;
      text-align: left;
    }
    section.active {
      display: block;
    }
    #about p.signature {
      margin-top: 3rem;
      font-style: italic;
      color: #7a8b22;
      font-weight: 600;
      font-size: 1rem;
      user-select: none;
      text-align: center;
      text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
    }
    #startReadingBtn {
      margin-top: 1.5rem;
      padding: 18px 60px;
      font-size: 2rem;
      font-weight: 700;
      border-radius: 12px;
      box-shadow: 0 12px 25px rgba(154, 205, 50, 0.6);
      cursor: pointer;
      color: #003300;
      background-color: #9acd32;
      border: none;
      animation: blink 1.5s ease-in-out infinite;
      user-select: none;
      transition: background-color 0.3s ease;
      text-shadow: none;
    }
    #startReadingBtn:hover,
    #startReadingBtn:focus {
      background-color: #6b8e23;
      animation-play-state: paused;
      outline: none;
      color: #d7ffd9;
    }
    @keyframes blink {
      0%, 100% {opacity: 1;}
      50% {opacity: 0.4;}
    }
    @media (max-width: 480px) {
      .page-buttons {
        max-width: 100%;
        padding: 0 1rem;
      }
      .page-buttons button {
        max-width: 100%;
        font-size: 1.1rem;
      }
      header, main, footer {
        padding: 2rem 1rem;
        margin: 2rem auto 1.5rem auto;
      }
      h2 {
        font-size: 1.7rem;
      }
      h3 {
        font-size: 1.3rem;
      }
      #startReadingBtn {
        font-size: 1.5rem;
        padding: 14px 40px;
      }
    }

    /* Comment Section Styling */
    .comment-section {
      margin-top: 2rem;
      border-top: 1px solid #9acd32;
      padding-top: 1.5rem;
    }
    .comment-section label {
      font-weight: 600;
      display: block;
      margin-bottom: 0.5rem;
      color: #9acd32;
      text-shadow: 1px 1px 2px rgba(0,0,0,0.4);
    }
    .comment-section textarea {
      width: 100%;
      min-height: 90px;
      border-radius: 6px;
      border: 1px solid #9acd32;
      background-color: rgba(154, 205, 50, 0.1);
      color: #003300;
      padding: 10px;
      font-family: inherit;
      font-size: 1rem;
      resize: vertical;
    }
    .comment-section button.submit-comment {
      margin-top: 0.6rem;
      background-color: #9acd32;
      color: #003300;
      border: none;
      padding: 0.6rem 1.5rem;
      font-weight: 700;
      border-radius: 6px;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(0,51,0,0.35);
      transition: background-color 0.3s ease;
      user-select: none;
    }
    .comment-section button.submit-comment:hover,
    .comment-section button.submit-comment:focus {
      background-color: #6b8e23;
      color: #d7ffd9;
      outline: none;
    }
    .comment-list {
      margin-top: 1.25rem;
      max-height: 200px;
      overflow-y: auto;
      border-top: 1px solid #9acd32;
      padding-top: 1rem;
    }
    .comment-list p {
      background: rgba(154, 205, 50, 0.15);
      padding: 0.6rem 1rem;
      border-radius: 6px;
      margin-bottom: 0.8rem;
      box-shadow: inset 0 0 3px rgba(0,51,0,0.3);
      color: #003300;
      user-select: text;
    }
  </style>
</head>
<body>
  <header>
    <h1>True Crime Story</h1>
  </header>
  
  <nav class="page-buttons" role="navigation" aria-label="Main navigation buttons">
    <button id="btn-home" aria-controls="home" aria-selected="true" type="button">Home</button>
    <button id="btn-about" aria-controls="about" aria-selected="false" type="button">About</button>
    <button id="btn-contact" aria-controls="contact" aria-selected="false" type="button">Contact</button>
  </nav>

  <main>
    <section id="home" class="active" tabindex="0" aria-label="Home Section">
      <h2>Home</h2>
      <p>Welcome to True Crime Story — Where True Crime Comes to Life.</p>
      <p>If you’re captivated by true crime, you’ve found your new home. At Dark Chronicles, we don’t just retell stories — we investigate them. Every case we feature is thoroughly researched, based on verified facts, police reports, eyewitness testimonies, and expert analysis. Our mission is to shed light on mysteries that have haunted communities and challenge the answers often taken at face value.</p>
      <p>Here, you’ll explore the real stories behind the headlines: disappearances that remain unsolved, shocking crimes that changed lives forever, and the relentless pursuit of justice by detectives and families alike. Our content is designed to inform, provoke thought, and honor the victims by keeping their stories alive.</p>
      <p>Join a community that values truth, critical thinking, and compassion. Because in true crime, every detail counts — and every story deserves to be told.</p>
      
      <button id="startReadingBtn" aria-expanded="false" aria-controls="story" type="button">Click here to start reading</button>
      
      <div id="story" aria-live="polite" aria-atomic="true">
        <article class="story-case" id="chiong">
          <h3>The Chiong Sisters Murder Case</h3>
          <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Cebu_City_Municipal_Hall_facade_07-2019.jpg/640px-Cebu_City_Municipal_Hall_facade_07-2019.jpg" alt="Cebu City, where the Chiong sisters case occurred" />
          <p><em>Location linked to the case: Cebu City, Philippines.</em></p>
          <p>On the night of July 16, 1997, sisters Marijoy (21) and Jacqueline Chiong (23) were abducted while waiting at a bus stop along Archbishop Reyes Avenue in Cebu City by a group of seven men.</p>
          <p>Marijoy’s body was later found in a ravine in Carcar City, showing signs of brutal rape and assault, but Jacqueline’s body has never been recovered.</p>
          <p>The accused, including Francisco Juan “Paco” Larrañaga and six others, were convicted of kidnapping, rape, and murder. Central to the prosecution's case was a co-defendant—Davidson Valiente Rusia—who was granted immunity in exchange for his testimony. However, his credibility was widely disputed, raising questions about the sufficiency and reliability of evidence against the accused.</p>
          <p>Despite the conviction and subsequent sentences—including death penalty later commuted to life imprisonment—the case remains one of the Philippines’ most controversial legal battles. It sparked multiple appeals, public debates on justice, and dramatizations in film and documentary.</p>
          <a href="https://jur.ph/jurisprudence/digest/people-v-larranaga-08632" target="_blank" rel="noopener noreferrer" class="continue-btn">Continue reading</a>

          <div class="comment-section" aria-label="Comments for Chiong Sisters Murder Case">
            <label for="chiong-comment">Leave a comment:</label>
            <textarea id="chiong-comment" rows="4" placeholder="Write your comment here..."></textarea>
            <button class="submit-comment" data-target="chiong-comments">Submit</button>
            <div id="chiong-comments" class="comment-list" aria-live="polite" aria-relevant="additions"></div>
          </div>
        </article>

        <article class="story-case" id="vizconde" style="margin-top:3rem;">
          <h3>The Vizconde Massacre</h3>
          <img src="https://upload.wikimedia.org/wikipedia/commons/4/49/Judge%E2%80%99s_Gavel_%2836041461993%29.jpg" alt="Court and gavel, symbolic of the Vizconde case" />
          <p><em>Location: Parañaque, Metro Manila, Philippines</em></p>
          <p>On June 30, 1991, Estrellita Vizconde and her two daughters, Carmela (18) and Jennifer (7), were brutally murdered in their home. Carmela also suffered sexual assault. The crime shocked the nation and led to intense media coverage.</p>
          <p>After years of investigation, Hubert Webb and several others were convicted in 2000, mainly on the testimony of a key witness. However, questions regarding the reliability of evidence and alibis led to ongoing debates and appeals.</p>
          <p>In December 2010, the Supreme Court acquitted Webb and his co-accused, citing reasonable doubt and the unreliability of prosecution witnesses, leaving the case officially unsolved and further intensifying controversy about the Philippine justice system.</p>
          <a href="https://jur.ph/jurisprudence/digest/people-v-larranaga-08632" target="_blank" rel="noopener noreferrer" class="continue-btn">Continue reading</a>

          <div class="comment-section" aria-label="Comments for Vizconde Massacre">
            <label for="vizconde-comment">Leave a comment:</label>
            <textarea id="vizconde-comment" rows="4" placeholder="Write your comment here..."></textarea>
            <button class="submit-comment" data-target="vizconde-comments">Submit</button>
            <div id="vizconde-comments" class="comment-list" aria-live="polite" aria-relevant="additions"></div>
          </div>
        </article>
      </div>
    </section>
    
    <section id="about" tabindex="0" aria-label="About Section">
      <h2>About</h2>
      <p>A true crime story is a non-fiction genre that examines real crimes, often focusing on violent acts like murders and serial killings. These stories detail the actions of perpetrators, victims, and others involved, investigating motives and the criminal justice process. True crime stories often appeal widely, especially among women, and can range from quick, sensationalized accounts to deeply researched works of literary merit. However, the genre sometimes faces criticism for sensationalism and for potentially disrespecting victims while influencing public perceptions of crime and justice.</p>
      <p class="signature">Created by: Capuyo, Efren D.</p>
    </section>
    
    <section id="contact" tabindex="0" aria-label="Contact Section">
      <h2>Contact</h2>
      <p>Phone: <a href="tel:09622630879">09622630879</a></p>
      <p>Follow me on Facebook: 
        <a href="https://www.facebook.com/share/1F5yxG57Cu/?mibextid=wwXIfr" target="_blank" rel="noopener noreferrer">Facebook</a>
      </p>
    </section>
  </main>
  
  <footer>
    <p>© 2025 True Crime Story</p>
  </footer>

  <script>
    function showSection(section) {
      const sections = ['home', 'about', 'contact'];
      sections.forEach(id => {
        document.getElementById(id).classList.remove('active');
        document.getElementById('btn-' + id).setAttribute('aria-selected', 'false');
      });
      document.getElementById(section).classList.add('active');
      document.getElementById('btn-' + section).setAttribute('aria-selected', 'true');
      window.scrollTo(0, 0);
    }
    document.getElementById('btn-home').addEventListener('click', () => showSection('home'));
    document.getElementById('btn-about').addEventListener('click', () => showSection('about'));
    document.getElementById('btn-contact').addEventListener('click', () => showSection('contact'));

    window.onload = () => {
      showSection('home');
    }

    document.getElementById('startReadingBtn').addEventListener('click', function() {
      const story = document.getElementById('story');
      if (story.style.display === 'none' || !story.style.display) {
        story.style.display = 'block';
        this.textContent = 'Hide story';
        this.setAttribute('aria-expanded', 'true');
      } else {
        story.style.display = 'none';
        this.textContent = 'Click here to start reading';
        this.setAttribute('aria-expanded', 'false');
      }
    });

    // Comment submission event delegation
    document.querySelectorAll('.submit-comment').forEach(button => {
      button.addEventListener('click', () => {
        const targetId = button.getAttribute('data-target');
        const textareaId = button.previousElementSibling.id;
        const textarea = document.getElementById(textareaId);
        const commentList = document.getElementById(targetId);
        const commentText = textarea.value.trim();
        if (commentText.length > 0) {
          const p = document.createElement('p');
          p.textContent = commentText;
          commentList.appendChild(p);
          textarea.value = "";
          textarea.focus();
        } else {
          alert("Please enter a comment before submitting.");
          textarea.focus();
        }
      });
    });
  </script>
</body>
</html>
