---
layout: default
title: Projects
description: Things I have built — from enterprise AI to education platforms to student technology groups.
permalink: /projects/
---

<style>
.projects-page {
  padding: 0 0 5rem;
}
.project-entry {
  display: grid;
  grid-template-columns: 200px 1fr;
  gap: 3rem;
  padding: 3rem 0;
  border-bottom: 1px solid #E5E7EB;
  align-items: start;
}
.project-entry:first-of-type { border-top: 1px solid #E5E7EB; }
.project-label {
  font-size: 0.72rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: #9CA3AF;
  margin-bottom: 0.4rem;
}
.project-org {
  font-size: 1.1rem;
  font-weight: 700;
  color: #1C1917;
  margin-bottom: 0.25rem;
}
.project-period {
  font-size: 0.82rem;
  color: #9CA3AF;
}
.project-title {
  font-size: 1.3rem;
  font-weight: 700;
  letter-spacing: -0.01em;
  color: #1C1917;
  margin-bottom: 0.75rem;
  line-height: 1.3;
}
.project-body {
  font-family: 'Lora', serif;
  font-size: 0.95rem;
  line-height: 1.75;
  color: #4B5563;
}
.project-body p { margin-bottom: 0.9rem; }
.project-body p:last-child { margin-bottom: 0; }
.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  margin-top: 1rem;
}
.project-link {
  display: inline-flex;
  align-items: center;
  gap: 0.3rem;
  font-size: 0.82rem;
  font-weight: 600;
  color: #B45309;
  text-decoration: none;
  margin-top: 1rem;
}
.project-link:hover { color: #92400E; }
@media (max-width: 640px) {
  .project-entry {
    grid-template-columns: 1fr;
    gap: 0.75rem;
    padding: 2rem 0;
  }
}
</style>

<header class="page-header">
  <div class="container-wide">
    <div class="page-label">Work</div>
    <h1 class="page-title">Projects</h1>
    <p class="page-description">
      Things I have built, companies I have founded and organisations I have contributed to.
    </p>
  </div>
</header>

<div class="projects-page">
  <div class="container-wide">

    <div class="project-entry">
      <div>
        <div class="project-label">Current · Founder</div>
        <div class="project-org">Terno AI</div>
        <div class="project-period">2023 – Present</div>
      </div>
      <div>
        <div class="project-title">Enterprise-Grade AI Data Scientist</div>
        <div class="project-body">
          <p>
            Terno AI enables business users to ask questions about their organisational data
            in natural language and receive reliable, analytically sound answers. Unlike AI
            tools that generate plausible-sounding text, Terno generates and executes
            analytical code in a secure environment — making results verifiable and reproducible.
          </p>
          <p>
            The platform is designed for enterprise deployment, with a semantic layer that
            maps messy real-world data to business concepts, fine-grained access controls,
            sandboxed code execution and the ability to run within a customer's private
            cloud infrastructure.
          </p>
          <p>
            Terno handles complex analytics including forecasting, clustering, classification,
            statistical analysis and decision support — not just simple SQL queries.
          </p>
        </div>
        <div class="project-tags">
          <span class="tag tag--accent">Enterprise AI</span>
          <span class="tag">Natural Language Analytics</span>
          <span class="tag">Data Science</span>
          <span class="tag">Secure AI</span>
        </div>
        <a href="{{ '/terno-ai' | relative_url }}" class="project-link">Learn more about Terno AI →</a>
      </div>
    </div>

    <div class="project-entry">
      <div>
        <div class="project-label">Founder</div>
        <div class="project-org">CloudxLab</div>
        <div class="project-period">2015 – Present</div>
      </div>
      <div>
        <div class="project-title">Practical AI and Technology Education at Scale</div>
        <div class="project-body">
          <p>
            CloudxLab is an education platform built to make practical, high-quality technology
            learning accessible to a large number of people. It has reached hundreds of thousands
            of learners interested in artificial intelligence, machine learning, data science,
            data engineering, cloud computing, distributed systems and generative AI.
          </p>
          <p>
            Teaching and interacting with learners through CloudxLab profoundly changed my
            thinking about education. It reinforced my belief that good teaching is not
            about delivering information — it is about helping learners discover ideas,
            develop confidence and build the ability to think independently.
          </p>
          <p>
            The platform is built around hands-on learning, real environments and the
            philosophy I call Learning by Inventing.
          </p>
        </div>
        <div class="project-tags">
          <span class="tag">EdTech</span>
          <span class="tag">AI Education</span>
          <span class="tag">Machine Learning</span>
          <span class="tag">Cloud Computing</span>
        </div>
        <a href="{{ site.cloudxlab_url }}" class="project-link" target="_blank" rel="noopener">Visit CloudxLab →</a>
      </div>
    </div>

    <div class="project-entry">
      <div>
        <div class="project-label">Founder</div>
        <div class="project-org">tBits</div>
        <div class="project-period">2008 – 2015</div>
      </div>
      <div>
        <div class="project-title">Document Management and Technology for the Power Sector</div>
        <div class="project-body">
          <p>
            tBits built document management software and technology products that were used
            extensively in India's power sector — including in projects related to the
            construction and operation of power plants. Seeing software built by my team
            being used in real industrial contexts was a formative experience.
          </p>
          <p>
            Through tBits, I hired and mentored several talented engineers, many of them
            graduates from leading Indian engineering institutions. Many of those engineers
            have gone on to build strong careers in the technology industry. Building the
            team and watching those individuals grow was one of the most satisfying parts
            of this chapter.
          </p>
          <p>
            tBits taught me how to turn technical capability into real-world outcomes —
            and how important it is to build for users who depend on your software for
            serious work.
          </p>
        </div>
        <div class="project-tags">
          <span class="tag">Enterprise Software</span>
          <span class="tag">Document Management</span>
          <span class="tag">Power Sector</span>
        </div>
      </div>
    </div>

    <div class="project-entry">
      <div>
        <div class="project-label">Co-founder · Student Organisation</div>
        <div class="project-org">IMG — IIT Roorkee</div>
        <div class="project-period">2000 – 2004</div>
      </div>
      <div>
        <div class="project-title">Information Management Group at IIT Roorkee</div>
        <div class="project-body">
          <p>
            During my time at IIT Roorkee, I co-founded IMG — Information Management Group —
            the student-led technical group responsible for building and maintaining important
            online systems and resources on campus.
          </p>
          <p>
            This was my first experience of building something real that many people depended
            on. It shaped my early understanding that technology, at its best, is a form of
            service — and that building useful things requires not just technical skill but
            also the ability to understand what people actually need.
          </p>
        </div>
        <div class="project-tags">
          <span class="tag">Web Development</span>
          <span class="tag">Student Leadership</span>
          <span class="tag">IIT Roorkee</span>
        </div>
      </div>
    </div>

  </div>
</div>
