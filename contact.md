---
layout: default
title: Connect
description: Get in touch with Sandeep Giri — founder, teacher and technologist.
permalink: /contact/
---

<style>
.contact-page {
  padding: 3rem 0 6rem;
}
.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 5rem;
  align-items: start;
}
.contact-intro p {
  font-family: 'Lora', serif;
  font-size: 1rem;
  line-height: 1.78;
  color: #4B5563;
  margin-bottom: 1.25rem;
}
.contact-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem 0;
  border-bottom: 1px solid #F3F4F6;
  text-decoration: none;
  color: inherit;
  transition: color 150ms ease;
}
.contact-item:hover { color: #2563EB; }
.contact-item:first-of-type { border-top: 1px solid #F3F4F6; }
.contact-icon {
  width: 40px;
  height: 40px;
  background: #EEF2FF;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.1rem;
  flex-shrink: 0;
  transition: background 150ms ease;
}
.contact-item:hover .contact-icon { background: #DBEAFE; }
.contact-label {
  font-size: 0.75rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.07em;
  color: #9CA3AF;
}
.contact-value {
  font-size: 0.95rem;
  font-weight: 500;
  color: #111827;
}
@media (max-width: 768px) {
  .contact-grid { grid-template-columns: 1fr; gap: 3rem; }
}
</style>

<header class="page-header">
  <div class="container-wide">
    <div class="page-label">Connect</div>
    <h1 class="page-title">Let's talk</h1>
    <p class="page-description">
      I enjoy conversations that cross the boundaries of technology, education and ideas.
    </p>
  </div>
</header>

<div class="contact-page">
  <div class="container-wide">
    <div class="contact-grid">

      <div class="contact-intro">
        <p>
          I enjoy connecting with learners, educators, founders, researchers and enterprise
          leaders working on meaningful applications of artificial intelligence.
        </p>
        <p>
          If you are interested in trustworthy enterprise AI, education through discovery,
          intelligent analytics, agentic systems or collaborative work across industry and
          academia — I would be glad to hear from you.
        </p>
        <p>
          I am particularly interested in conversations about:
        </p>
        <ul style="font-family:'Lora',serif;font-size:1rem;line-height:1.75;color:#4B5563;margin-bottom:1.25rem;padding-left:1.5rem">
          <li>Secure and reliable enterprise AI</li>
          <li>Teaching through discovery and the Learning by Inventing philosophy</li>
          <li>Agentic AI systems and open-source tools</li>
          <li>Collaboration between industry, academia and educators</li>
          <li>Early-stage founders building at the intersection of AI and education</li>
        </ul>
        <p>
          I read everything I receive. I may not be able to respond to every message
          immediately, but I will try.
        </p>
      </div>

      <div>
        <a href="mailto:{{ site.author.email }}" class="contact-item">
          <div class="contact-icon">&#9993;</div>
          <div>
            <div class="contact-label">Email</div>
            <div class="contact-value">{{ site.author.email }}</div>
          </div>
        </a>

        <a href="{{ site.author.linkedin }}" class="contact-item" target="_blank" rel="noopener">
          <div class="contact-icon">&#128101;</div>
          <div>
            <div class="contact-label">LinkedIn</div>
            <div class="contact-value">Connect on LinkedIn</div>
          </div>
        </a>

        <a href="{{ site.author.github }}" class="contact-item" target="_blank" rel="noopener">
          <div class="contact-icon">&#128736;</div>
          <div>
            <div class="contact-label">GitHub</div>
            <div class="contact-value">See my code</div>
          </div>
        </a>

        <a href="{{ site.cloudxlab_url }}" class="contact-item" target="_blank" rel="noopener">
          <div class="contact-icon">&#127891;</div>
          <div>
            <div class="contact-label">CloudxLab</div>
            <div class="contact-value">Learn AI, ML and Data Science</div>
          </div>
        </a>

        <a href="{{ site.terno_url }}" class="contact-item" target="_blank" rel="noopener">
          <div class="contact-icon">&#128202;</div>
          <div>
            <div class="contact-label">Terno AI</div>
            <div class="contact-value">Enterprise AI data science</div>
          </div>
        </a>

        <a href="{{ '/feed.xml' | relative_url }}" class="contact-item">
          <div class="contact-icon">&#128240;</div>
          <div>
            <div class="contact-label">RSS Feed</div>
            <div class="contact-value">Subscribe to new essays</div>
          </div>
        </a>

        <div style="margin-top:2rem;padding:1.5rem;background:#F9FAFB;border-radius:12px;border:1px solid #E5E7EB">
          <p style="font-size:0.82rem;color:#9CA3AF;margin:0;line-height:1.6">
            For media enquiries, academic collaborations or enterprise AI discussions,
            email is the best way to reach me. I am also open to speaking at conferences
            and educational institutions on topics related to AI, education and
            entrepreneurship.
          </p>
        </div>
      </div>

    </div>
  </div>
</div>
