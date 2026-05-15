# Project Report — Personal Portfolio Website

**Submitted by:** Purnima  
**College:** Sagarmatha College of Science and Technology, Kathmandu  
**Program:** Bachelor of Computer Applications (BCA) — 4th Year  
**Internship:** Synet Technologies  
**Task Level:** Basic  
**Task Number:** Task 1  
**Task Title:** Personal Portfolio Website  
**Submission Date:** May 2026  
**GitHub Repository:** https://github.com/purnimm45/synet-task1-portfolio-purnima

---

## 1. Introduction

This report documents the design and development of my personal portfolio website, submitted as Task 1 of the Synet Technologies internship program. The task required building a fully functional personal portfolio using web technologies, hosted on a public GitHub repository with proper documentation, screenshots, and a video walkthrough.

The portfolio serves as a digital resume — a single place where my skills, background, and projects are presented in a clean, accessible format for anyone who wants to know more about me as a developer.

---

## 2. Objective

The main goals for this task were:

- Build a personal portfolio website from scratch
- Include sections for introduction, about me, skills, and contact
- Make the site fully responsive across devices
- Write clean, readable, and commented code
- Maintain a proper git commit history (minimum 5 meaningful commits)
- Document everything in a README and submit via GitHub

---

## 3. Tools and Technologies Used

| Technology | Purpose |
|---|---|
| HTML5 | Page structure and semantic elements |
| CSS3 | Styling, layout (Flexbox + Grid), animations, CSS variables |
| JavaScript (ES6) | DOM manipulation, scroll effects, form handling, hamburger menu |
| Google Fonts | Typography — Playfair Display and DM Sans |
| Git & GitHub | Version control and public repository hosting |
| VS Code | Code editor |
| Browser DevTools | Testing responsiveness and debugging |

No CSS frameworks (like Bootstrap or Tailwind) or JavaScript frameworks (like React) were used. This was an intentional choice to strengthen core fundamentals.

---

## 4. Website Structure

The portfolio is a single-page website divided into the following sections:

### 4.1 Navigation Bar
A fixed navigation bar sits at the top across all pages. On desktop it shows links to About, Skills, and Contact. On mobile it collapses into a hamburger menu that slides open a drawer. When the user scrolls down past 40px, the navbar picks up a dark blurred background using JavaScript.

### 4.2 Hero Section
The hero is the first thing visitors see. It contains:
- A greeting with my name
- My role (Full-Stack Developer) and college info
- Two CTA buttons — "Hire Me" and "Learn More"
- A decorative code card displaying my info as a JavaScript object
- Subtle animated background blobs for visual depth

### 4.3 About Me Section
A two-column grid section. The left column has three paragraphs introducing me and my background, plus a stats row (3+ years coding, 5+ projects). The right column has a featured project card highlighting SewaSathi and PawBliss with their tech tags and current status.

### 4.4 Skills Section
Four cards displayed in a CSS Grid — PHP, MySQL, JavaScript, HTML & CSS. Each card has:
- A technology icon (inline SVG)
- Skill name and short description
- An animated progress bar showing proficiency percentage

### 4.5 Contact Section
A two-column layout with contact information on the left (location, college, status, projects) and a form on the right. The form has fields for first name, last name, email, subject, and message. On submit it shows a green success toast. Currently the form is front-end only — email sending is a planned improvement.

### 4.6 Footer
Simple centered footer with my name, college, and the current year auto-filled by JavaScript.

---

## 5. Key Implementation Details

### 5.1 CSS Custom Properties
All colors, fonts, spacing, border radii, and shadows are defined as CSS variables in `:root`. This made it easy to maintain a consistent design system and change values globally.

```css
:root {
  --accent    : #0ea5e9;
  --navy-900  : #0f172a;
  --font-body : 'DM Sans', sans-serif;
  --radius-lg : 20px;
}
```

### 5.2 Scroll Animations with IntersectionObserver
Rather than using a library, scroll-triggered animations are handled with the native IntersectionObserver API. Each section and skill card starts at `opacity: 0` and `translateY(30px)`, then gains a `.visible` class when it enters the viewport, transitioning smoothly into view.

```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) entry.target.classList.add('visible');
  });
}, { threshold: 0.12 });
```

### 5.3 Responsive Design
The layout uses CSS Flexbox for the hero and navigation, and CSS Grid for the about, skills, and contact sections. Two media query breakpoints handle the responsive behavior:
- `@media (max-width: 900px)` — tablet: hero stacks vertically, skills go to 2 columns
- `@media (max-width: 600px)` — mobile: hamburger menu shows, single column layouts, adjusted font sizes

### 5.4 Custom Logo
My personal logo (a moon with "Pwai" written in script — pt.png) is displayed as a circular image in the navbar alongside the "PT." text logo.

---

## 6. Screenshots

*(See the `/screenshots` folder in the repository)*

| Screenshot | Description |
|---|---|
| 01-hero.png | Landing section with name, tagline, and code card |
| 02-about.png | About me section with project card |
| 03-skills.png | Skills section with four animated cards |
| 04-contact.png | Contact section with form |
| 05-mobile.png | Mobile responsive view with hamburger menu |

---

## 7. Challenges Faced

**Responsive Hero Layout:** The two-column flex layout in the hero section required careful handling of breakpoints. The code card and text column needed to stack vertically on smaller screens while maintaining proper padding and alignment. This took several iterations.

**IntersectionObserver Threshold Tuning:** Finding the right threshold value (settled on 0.12) so animations triggered naturally without feeling either too early or too late required manual testing across different scroll speeds and screen sizes.

**Hamburger Menu Animation:** Animating the three spans to form an X shape on menu open using CSS transforms and nth-child selectors was tricky to get looking smooth.

**CSS Specificity Conflicts:** Having both a `.nav__logo` class and a nested `.nav__logo` caused some styling conflicts that needed to be cleaned up carefully.

---

## 8. Testing

The website was tested on:
- Chrome (Desktop — Windows)
- Microsoft Edge (Desktop)
- Chrome DevTools mobile emulation (iPhone SE, Pixel 5, iPad)

All core features — navigation, animations, form, hamburger menu — worked correctly across tested environments.

---

## 9. Future Improvements

- Connect the contact form to actually send emails (using EmailJS or PHP mailer)
- Add a dedicated Projects section with more work samples and GitHub links
- Add a downloadable CV/resume button
- Improve accessibility (ARIA labels, keyboard navigation, focus states)
- Add a light mode option

---

## 10. Conclusion

This task gave me hands-on practice with responsive web design, CSS animations, and clean JavaScript without relying on any external frameworks. Building a portfolio from scratch forced me to think about layout, user experience, and code organization in a way that tutorials don't always cover. I'm happy with how it turned out and I plan to keep improving it as I build more projects.

---

## 11. References

- MDN Web Docs — IntersectionObserver API
- MDN Web Docs — CSS Custom Properties
- Google Fonts — Playfair Display, DM Sans
- CSS-Tricks — A Complete Guide to Flexbox
- CSS-Tricks — A Complete Guide to Grid

---

*Report prepared by Purnima · BCA 4th Year · Sagarmatha College of Science and Technology · 2026*
