
# SITEMINI SPEC:

- Advanced prototype for demonstration purposes
- Not intended for production use.

## TARGET AUDIENCE: 

- CEOs of companies with over 100 employees 
- French speakers
- Interested in AI but not tech-savvy 
- Questions to be answered on this site: how can I use AI in my role as CEO?
  - Why listen to this CEO?
  - What has he done?
  - What has he gained?
  - How do I get started?

## WEBSITE POSITIONING:

A CEO talks to other CEOs about his adoption of AI
- in his day-to-day role as CEO
- to drive change within the company (800 employees).

## WEBSITE PAGES:

**PAGE 1 (home): AI FOR CEOs**
CEO testimonial on:
- use cases
- ROI
- approach to adopting AI

**PAGE 2: BETWEEN CEOs**
- Workshop registration form
- No actual data sent
- Confirmation message: "Prototype > 0 data sent or stored"

**PAGE 3: CEO STARTER KIT**
- AI strategy diagnostic tool
- Use case diagnostic tool
- Prompt generator tool 
[the code for these tools will be provided separately]

**PAGE 4: REFLECTIONS**
CEO’s additional reflection notes

**PAGE 4: CONTACT**
Contact form

## OUT OF SCOPE: 

- Full SaaS platform
- Members’ area
- Automation
- Customisation
- Marketplace
- In-depth technical content
- Private community.

## WEBSITE FORMAT: 

- Style: professional, modern. Design system: https://fr.ippon.tech 
- Language: FRENCH
- Structure: 1 screen = 1 key message 
- Editorial guidelines: 
  - Break up long texts into short sentences
  - Tone: CEO-to-CEO, understated, direct, credible
  - Prefer: concrete, practical, perspective, responsibility, judgement, composure, leadership. -- Do not use: “revolutionary”, “disruptive”, “game changer”
  - Each screen must have:
    - 1 strong headline
    - 1 explanatory sentence
    - 1 illustration
    - possibly a maximum of 3 bullet points (low density)
  - Content: very clear to understand (no technical jargon), no buzzword
- Responsive.

## TECHNOLOGY: 
 
- Application of best coding practices (architecture, DRY, YAGNI, etc.) 
  - The architecture must allow for migration to V1 with minimal effort 
- Constraint: a single HTML file
  - CSS within a <style> tag
  - JavaScript within a <script> tag
  - No database
  - No framework
  - No CDN
  - No mandatory external assets
  - Code commented only where useful
  - Readable and consistent class names
  - JS limited to necessary interactions: mobile menu, form, navigation, page/section display, possible video modal
- Hosting: GitHub Repo > Coolify (PaaS) > Hostinger (VPS).