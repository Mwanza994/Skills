---
name: build-premium-web-experiences
description: Plan, art-direct, implement, and verify crisp, distinctive, responsive websites with purposeful premium animation and a functional conversion journey. Use for polished marketing and landing pages, modern product sites, creative portfolios, premium redesigns, interactive web experiences, GSAP/ScrollTrigger scenes, or when a frontend looks generic, visually inconsistent, or motion-heavy without purpose.
---

# Build Premium Web Experiences

Build a real website, not a static hero mockup. Combine precise design, functional product or conversion journeys, intentional motion, and verified browser behavior. Preserve the user's brand and project constraints. Visual sophistication must improve comprehension and trust, not compete with them.

## 1. Define the experience contract

Before changing code, inspect the brief and the existing project. Identify:

- Audience, primary user problem, desired action, and evidence that would earn trust.
- Brand assets, existing design tokens, content, media, references, technical stack, and deployment constraints.
- Whether the task is a new site, a redesign, a single section, or a narrow animation change.
- Desired level of motion: restrained product UI, editorial/cinematic, or immersive/3D.
- What must remain unchanged. Never expand a narrow task into a full redesign without authorization.

If references are supplied, extract composition, hierarchy, rhythm, contrast, media treatment, and motion behavior. Create a new expression rather than copying someone else's brand, assets, layout, or source code.

## 2. Load the smallest useful set of specialist skills

When this repository or equivalent installed skills are accessible, read the relevant paths below before implementation. Paths are relative to this SKILL.md. If the sibling skills are absent, proceed using the rules in this document; do not assume the files exist.

| Need | Existing specialist skill |
| --- | --- |
| Establish a visual specification | `../../ui/design-first-ui-prompting/SKILL.md` |
| Prevent generic or incoherent UI | `../../ui/no-ai-design-slop/SKILL.md` |
| Full premium / Awwwards-style art direction | `../../web-design/build-awwwards-quality-sites/SKILL.md` |
| Polished restrained motion | `../../web-design/animation-systems/SKILL.md` |
| A cohesive GSAP + Lenis cinematic system | `../../web-design/cinematic-gsap-lenis-motion-system/SKILL.md` |
| Scroll-synchronized product narrative | `../../web-design/gsap-scrolltrigger-storytelling/SKILL.md` |
| Product evidence and conversion | `../../web-design/product-proof-saas/SKILL.md` |
| Refined elevation when justified | `../../web-design/beautiful-shadows/SKILL.md` |
| Janky or expensive animations | `../optimize-web-animations/SKILL.md` |
| Evidence-based implementation review | `../iterate-until-verified/SKILL.md` |

Use a base design skill, the single most relevant motion skill, and the anti-slop gate by default. Add specialists only for concrete needs. Do not stack every effect library or aesthetic recipe. A specialist's stricter accessibility or performance rule takes precedence over a decorative preference.

## 3. Establish one art direction before coding

Write a compact internal design brief containing:

1. **Visual thesis:** A specific concept and mood that fits the business and audience.
2. **Page narrative:** The visitor's questions in order, the product demonstration or proof, objections, and primary CTA.
3. **Grid and spacing:** Container widths, columns, breakpoints, vertical rhythm, and alignment rules. Start from a coherent 4/8px spacing scale, then adjust optically.
4. **Typography:** Distinct display, heading, body, and label roles; responsive sizes using `clamp()` where appropriate; intentional line lengths and line breaks.
5. **Palette and materials:** Functional colors, contrast, surface hierarchy, borders, shadows, and one disciplined accent system.
6. **Imagery:** Real or properly licensed media, deliberate crops, responsive delivery, and fallback states. Never fabricate customer proof.
7. **Motion map:** Identify the one signature moment, supporting transitions, interaction feedback, and reduced-motion equivalents.
8. **Conversion mechanism:** Make the site useful: a working calculator, demo, search, quote flow, appointment path, or other relevant mechanism when the actual task calls for one.

The homepage must communicate what the product does and its next step without requiring animation. Select page sections from the real buying journey, not from a generic template checklist.

## 4. Implement a crisp design system

- Preserve the existing framework and design system unless a replacement is explicitly authorized.
- Use semantic HTML and reusable components with clear ownership. Match the project's conventions for routing, state, styling, and asset loading.
- Create precision through optical alignment, consistent baselines, purposeful whitespace, readable type, controlled hierarchy, and image sharpness.
- Favor coherent composition over repeated cards, ornamental pills, indistinguishable feature grids, glass everywhere, random gradients, and decorative particles.
- Ensure every interactive element has obvious affordance, keyboard access, visible focus, and meaningful hover, active, disabled, loading, success, and error states where applicable.
- Build a complete responsive composition. Recompose at narrower widths rather than merely shrinking the desktop layout.
- Use truthful copy, real product capabilities, licensed media, and verified evidence. Never invent testimonials, logos, metrics, endorsements, ratings, or awards.
- Do not replace functional product interfaces with screenshots or pretend buttons that do nothing.

## 5. Choreograph motion with restraint

Choose the lightest appropriate technology:

- **CSS:** Hover, focus, simple opacity/transform transitions, and low-complexity reveals.
- **GSAP + ScrollTrigger:** Coordinated hero intros, staggered text, measured scroll choreography, and pinned product narratives.
- **Lenis:** Only when smooth scrolling is material to the chosen experience; integrate with ScrollTrigger correctly. Never run multiple smooth-scroll engines.
- **Three.js/WebGL:** Only when spatial storytelling, product inspection, or material response clearly benefits. Provide a complete static fallback.

Starting timing ranges, to be tuned in the browser:

- Hover and press feedback: 120–200 ms.
- UI state transitions: 180–320 ms.
- Section entrance: 400–800 ms.
- Hero choreography: 800–1600 ms, without delaying content usability.
- Small staggers: 40–90 ms; reduce density on mobile.

Keep motion meaningful: establish reading order, explain state, preserve continuity, or reward action. Use mostly `transform` and `opacity` for animated movement. Do not pin long content or animate scroll for novelty. Keep one primary orchestrator per scene.

Treat `prefers-reduced-motion: reduce` as a full alternative experience: show completed states immediately, disable pinning and scrubbed motion, and leave every control usable. The page must still read correctly with JavaScript unavailable or animation initialization failing.

On React route changes or component unmounts, kill timelines and triggers; disconnect observers and listeners; cancel animation frames; dispose WebGL resources. Pause continuous offscreen work and use mobile-friendly budgets. Preserve native scrolling and touch behavior.

## 6. Verify the rendered experience

Use the available browser and project checks. At minimum:

1. Run the project's build and applicable lint/type checks; fix actual errors rather than hiding them.
2. Inspect the real rendered page at approximately 390px, 768px, and 1440px, plus 320px for tight layouts. Check text clipping, unwanted horizontal scroll, image crops, baseline alignment, and content hierarchy.
3. Test the primary CTA or workflow end to end, including validation and recovery states. Check links, menus, forms, and navigation.
4. Test keyboard navigation, focus visibility, contrast, 200% zoom where tooling permits, and reduced motion.
5. Run the actual animation sequence forward and backward; confirm no blank initial states, scroll traps, jumpy pins, sticky overflow failures, or unresponsive controls.
6. Inspect console errors and slow or continuous animation work. Verify offscreen animation loops stop and no listeners or canvases accumulate after navigation.
7. Compare the result to the design brief and any supplied references. Remove the most obvious generic or purposeless treatments before adding new ones.

If a browser, profiler, or build command is unavailable, say what could not be verified. Do not claim a test passed without running it.

## 7. Report the completed work

Summarize the implemented design direction, primary functional path, chosen specialist skills, motion stack, responsive adjustments, validation evidence, and remaining limitations. Distinguish between a finished website, an untested implementation, and a visual concept.

## Acceptance criteria

A premium result must satisfy all applicable gates:

- **Distinctive:** A defensible brand-specific visual thesis; no interchangeable AI-template appearance.
- **Crisp:** Consistent alignment, typography, spacing, media quality, and high-information hierarchy.
- **Useful:** A real visitor journey, working controls, credible proof, and a clear next action.
- **Motion-led, not motion-burdened:** One memorable signature interaction; all remaining animation supports comprehension.
- **Accessible and responsive:** Usable by keyboard and touch, with complete reduced-motion and static fallbacks.
- **Operational:** No known blocking build, runtime, console, or navigation defects; observed performance problems addressed.

Prioritize fixing failed gates over introducing additional visual effects.
