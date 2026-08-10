# Paradigm Study product reconnaissance

Research date: 2026-08-08

Scope: First-party, publicly reachable surfaces at [paradigm.study](https://www.paradigm.study/). I did not create an account, complete OAuth, submit an email form, purchase anything, or bypass authentication. Observations are labeled as direct, claimed, or inferred where that distinction matters.

## Executive read

Paradigm presents itself less like a conventional course catalog and more like a personal learning workspace:

1. Bring a goal or source material.
2. Let an AI tutor build a learning route.
3. Work through a mutable canvas containing courses, lessons, notes, web material, and interactive content.
4. Let a persistent assistant, "Clover," remember deadlines, activity, and context.
5. Reuse routes and teaching approaches created by other people.

The strongest product idea is the combination of a personal AI tutor and a visual, editable learning canvas. The strongest marketing idea is that the homepage demonstrates this model interactively instead of explaining it only with screenshots.

The major limitation of this review is that all real study surfaces are authenticated. I could inspect the public product demonstration, auth entry points, a complete top-of-funnel quiz, public campaigns, legal feature claims, localization, responsive behavior, and error states. I could not inspect the real dashboard, onboarding, lesson player, practice flow, notebook, settings, progress reporting, or course authoring experience.

## Screens and workflows checked

| Surface | URL | Access | What was checked |
|---|---|---:|---|
| Main landing page | [paradigm.study](https://www.paradigm.study/) | Full | Navigation, hero, product demo, learning canvas, assistant narrative, example courses, pricing, footer |
| Spanish landing page | [/es](https://www.paradigm.study/es) | Full | Fully translated marketing copy and localized route links |
| Simplified Chinese landing page | [/zh-Hans](https://www.paradigm.study/zh-Hans) | Full | Locale route and translated page title/content |
| Learning-route canvas demo | [Homepage, "Invent a unique path"](https://www.paradigm.study/#route) | Full demo | Pan/drag/select behavior, toolbar, add menu, sticky-note creation, course preview dialog |
| Example-course gallery | [Homepage](https://www.paradigm.study/) | Full demo | Four course cards and expand/collapse behavior |
| Course detail preview | [Homepage route canvas](https://www.paradigm.study/#route) | Full demo | Course metadata, experience level, units, lessons, activity types, durations, catalog CTA |
| Signup, first step | [/signup](https://www.paradigm.study/signup) | Partial | Google OAuth option, email-first progressive form, consent copy, sign-in handoff |
| Login | [/login](https://www.paradigm.study/login) | Full initial screen | Google OAuth, email/password, forgot-password link, redirect preservation |
| Forgot password | [/forgot-password](https://www.paradigm.study/forgot-password) | Full initial screen | Email reset request and return-to-login action |
| Protected-route handoff | [/dashboard](https://www.paradigm.study/dashboard) | Auth gated | Redirect to `/login?redirect=%2Fdashboard` |
| Catalog handoff | `/home/catalog` from the course dialog | Auth gated | Redirect to login |
| AI Archetype quiz | [/ai-archetype](https://www.paradigm.study/ai-archetype) | Full | Start, 11 questions, answer selection, Back/Next states, result, share, retake, product CTA |
| Quiz-to-product bridge | [/ai-archetype](https://www.paradigm.study/ai-archetype) | Full until auth | Result CTA creates a prefilled Notebook prompt, then redirects to login |
| YC Reject Camp microsite | [/camp](https://www.paradigm.study/camp) | Full | Event pitch, schedule, benefits, obligations, applications-closed state |
| Legal and trust surfaces | [Terms](https://www.paradigm.study/legal/terms), [Privacy](https://www.paradigm.study/legal/privacy), [Refunds](https://www.paradigm.study/legal/refund) | Full | Product description, integrations, data use, age gate, beta billing state |
| 404 state | [/does-not-exist](https://www.paradigm.study/does-not-exist) | Full | Custom mascot illustration, concise explanation, return-home CTA |
| PWA metadata | [manifest.json](https://www.paradigm.study/manifest.json) | Full | Standalone display mode, app icons, theme and background colors |
| Public IA metadata | [sitemap.xml](https://www.paradigm.study/sitemap.xml), [robots.txt](https://www.paradigm.study/robots.txt) | Full | Indexed routes, locales, and names of protected product areas |

## Public landing experience

### Navigation and hero

The desktop header is intentionally sparse: brand, locale selector, and Log In. The locale selector offers English, Spanish, and Simplified Chinese. The hero pairs the serif headline "A School of One." with a staged product demonstration and two desktop CTAs: "Start learning" and "Take a closer look."

The hero demo cycles through three intake concepts:

- Upload files: slides, PDFs, or a photo.
- Share a link: video, article, or documentation.
- Drop text: notes or a learning goal.

These controls are a scripted marketing simulation when logged out, not a live ingestion workflow. The animation then shows a personalized path being built from the supplied context. This is effective because it makes the input-to-route mental model understandable before signup.

Source: [Homepage](https://www.paradigm.study/).

### Interactive learning-route canvas

The most informative public feature is a real React Flow canvas rather than a static mockup. It supports panning, dragging, selecting, keyboard movement, and toolbar actions:

- Fit view
- Arrange
- Add
- Delete

The sample route contains:

- A course card: "Investing for Beginners: Start with $1000"
- A checklist/document
- An interactive compound-growth visualization
- A web-page card
- Editable sticky notes

The Add menu exposes the content model more clearly than the marketing copy:

- Course
- Sticky Note
- Web Page
- Data Visualization
- Interactive Story
- Whiteboard
- Code Notebook
- Notes
- Upload File

Only Sticky Note is enabled in the public demo; the other menu items are visibly locked. Adding a note creates a new editable node locally.

Selecting the course opens a proper dialog with category, creator, description, experience level, units, lesson/quiz types, and durations. The visible preview includes units such as "Investing Basics" and "Platforms & Accounts." "Open in Paradigm" points toward the protected catalog and hands off to login.

Sources: [Homepage route section](https://www.paradigm.study/#route) and the first-party [React Flow CSS bundle](https://www.paradigm.study/_next/static/css/a585b75a635959c4.css).

### Assistant and memory narrative

"Clover" is presented as a proactive personal operator, not only a reactive chat box. The homepage demonstrates:

- Deadline reminders
- Mentor check-ins
- Study-streak encouragement
- Quiz refreshers
- Library due-date reminders
- Creating a course from event notes
- Building a cheat sheet around weak topics
- Confirming whether a report was submitted

This is marketing content rather than authenticated behavior I could verify, but it communicates the intended product relationship: a tutor that knows the learner's context and handles administrative details.

Source: [Homepage, "I remember your little things"](https://www.paradigm.study/).

### Community/course discovery

The course gallery demonstrates breadth rather than a narrow test-prep niche:

- Beginner app development
- Music production
- UCI introductory programming
- Counting for ages 3-5

"View all" expands the course fan and changes to "Collapse." Individual cards look clickable but did not expose additional content in the public gallery; the detailed course interaction lives in the route canvas instead.

Source: [Homepage](https://www.paradigm.study/).

### Pricing

The only live pricing state is "$0/mo" with explicit copy that paid plans and checkout are disabled during the public beta. The refund policy separately confirms there is no active beta subscription, paid trial, renewal, or automatic conversion.

Sources: [Homepage pricing](https://www.paradigm.study/) and [Refund Policy](https://www.paradigm.study/legal/refund).

## Auth and acquisition workflows

### Signup

Signup uses progressive disclosure:

1. Continue with Google, or
2. Enter an email and choose Continue.

No password field appears on the first screen. The later account-creation steps were not reached because doing so would require form submission. Consent to Terms and Privacy is placed directly beneath the primary action.

Source: [Signup](https://www.paradigm.study/signup).

### Login

Login offers:

- Continue with Google
- Email
- Password
- Forgot your password?
- Sign in
- Sign up

Protected routes preserve their destination in a `redirect` query parameter. For example, `/dashboard` redirects to `/login?redirect=%2Fdashboard`.

Source: [Login](https://www.paradigm.study/login).

### Password reset

The initial state is a single email field, "Send Reset Link," and "Back to Sign in." I did not submit the form, so delivery, confirmation, invalid-email, and expired-link states remain unobserved.

Source: [Forgot password](https://www.paradigm.study/forgot-password).

## AI Archetype campaign workflow

The AI Archetype microsite is a complete social-acquisition loop with a deliberately different visual identity.

1. Intro: "what kind of tech bro are you?"
2. Eleven scenario questions.
3. One answer must be selected before Next is enabled.
4. Back allows revision.
5. A result page presents an archetype, image, "essence," and numbered "receipts."
6. Actions include Share, Retake, and Go to Paradigm.
7. Share opens options for X/Twitter, Instagram, WhatsApp, Facebook, copy link, and download.
8. "Ask Paradigm about this result" creates a Notebook deep link with a prefilled reflection prompt.
9. Because Notebook is protected, the user is sent to login with that entire destination preserved.

The completed path produced "The Nonchalant." Its Notebook handoff included a prompt asking what the archetype says about the user's AI habits and where they are leaving value on the table. This is a strong example of converting a playful viral result into a personalized product session rather than ending at a share card.

Source: [AI Archetype](https://www.paradigm.study/ai-archetype).

## Other public surfaces

### YC Reject Camp

The camp page uses the core Paradigm type and color language but a campaign-specific layout. It contains:

- Event pitch and eligibility framing
- Four-day schedule
- Benefits such as housing, food, travel support, mentors, and filming
- Participant expectations
- A closed-application terminal state

The closed state replaces the form with an illustration, heading, explanation, deadline, and human contact email. It is a good low-anxiety empty-state pattern.

Source: [YC Reject Camp](https://www.paradigm.study/camp).

### 404

The custom 404 uses Clover walking, the heading "Page Not Found," a two-line explanation, and one "Return home" action. It stays on-brand without over-designing a dead end.

Source: [404 example](https://www.paradigm.study/does-not-exist).

## Product capabilities claimed by first-party policies

The public UI does not expose these authenticated workflows, but the Privacy Policy describes specific connected-service behavior:

- Google Drive: per-file picker access; selected files can be placed on the canvas.
- Google Calendar: find study windows and create requested study sessions.
- Gmail: read relevant metadata and snippets, without sending or modifying mail.
- Google Classroom: read courses, coursework, and the learner's submissions.
- Settings: disconnecting Google deletes stored tokens and revokes access.

The Terms describe AI tutoring, test preparation, user-uploaded materials, and study guidance. These are first-party product claims, not workflows verified in the authenticated UI.

Sources: [Privacy Policy, section 6](https://www.paradigm.study/legal/privacy) and [Terms of Use](https://www.paradigm.study/legal/terms).

## Design system

### Core visual character

The main brand is warm, editorial, and academic without looking institutional:

- Warm off-white backgrounds rather than pure white
- Deep ink/navy for authority
- Dusty blue as the primary soft accent
- Muted mint, rose, gold, lavender, and earth tones for content categories
- Fine borders and warm brown-tinted shadows
- Subtle dot-grid backgrounds that support the "workspace/canvas" metaphor
- Friendly Clover illustrations to soften an otherwise restrained system

Observed marketing tokens:

| Token | Value | Typical role |
|---|---:|---|
| Ink | `#011121` | Main text |
| Background | `#faf8f7` | Page background |
| Surface | `#fffdfc` | Cards and panels |
| Primary | `#00163e` | Primary actions |
| Accent | `#6e94cc` | Soft blue emphasis |
| Accent wash | `#e4ecf7` | Selected/secondary surfaces |
| Magic | `#6f63b6` | Purple accent/gradient |
| Mint | `#2b6d66` | Positive/learning accents |
| Rose | `#cf8276` | Warm contrast |

The PWA manifest uses `#FFFEF5` as its background and `#0b183d` as its theme color.

Sources: first-party [marketing CSS](https://www.paradigm.study/_next/static/css/d7f4b300650b40af.css) and [manifest.json](https://www.paradigm.study/manifest.json).

### Typography

The primary system uses a clear three-font hierarchy:

- Gowun Batang: display serif for expressive headlines.
- Geist Sans: UI and body copy.
- Geist Mono: metadata, labels, timestamps, and technical details.

Source Sans 3 is also loaded for broad language coverage. The main homepage H1 measured 58px/60.9px on desktop and 36px on a 390px viewport. Section headings measured 30px. Auth headings measured 44px desktop and 36px mobile. Body copy generally sits in the 14-16px range.

The AI Archetype campaign intentionally breaks from the core voice with Bebas Neue for 78px poster-like headlines and Inter for body/UI text. Its palette is black, warm cream, and fluorescent lime. That makes it feel like a shareable cultural artifact while retaining a small Paradigm brand anchor.

Source: observed computed styles on [Homepage](https://www.paradigm.study/), [Login](https://www.paradigm.study/login), [Camp](https://www.paradigm.study/camp), and [AI Archetype](https://www.paradigm.study/ai-archetype).

### Components and shape language

- Primary actions: deep navy, 8px radius, medium weight.
- Secondary auth actions: warm white, 1px border, 8px radius.
- Small chips and switching actions: full pills.
- Marketing cards: mostly 6px radius, fine borders, restrained warm shadows.
- Hero/course imagery: larger 18px-radius crops.
- Inputs: 48px height on auth screens, muted warm-gray fill.
- Dialogs: compact title bar, scrollable body, sticky CTA.
- Status states: illustration, heading, explanation, single fallback action.

The base token exposes `--radius: 0.5rem`. Observed page components use a controlled set of 6px, 8px, 18px, and pill radii rather than arbitrary rounding.

### Motion and feedback

Observed patterns include:

- Scripted typing and "thinking" animation in the hero
- Path-drawing animation while a route is generated
- Soft slide/fade transitions for onboarding/auth content
- Animated course-card fan expansion
- React Flow selection and drag feedback
- Disabled Next state until quiz selection
- Reduced-motion handling for smooth scrolling

The motion generally explains state changes rather than decorating every element.

### Responsive behavior

At a 390px viewport:

- The header keeps brand, locale, and Log In in one row.
- Main gutters collapse to 22-24px.
- The desktop two-column hero becomes a single column.
- The homepage H1 scales from 58px to 36px.
- The learning canvas remains 598px tall and pans internally; wide nodes do not cause document-level horizontal overflow.
- The course gallery becomes an overlapping stacked-card fan.
- The auth form becomes 342px wide with 24px side gutters and keeps the footer at the bottom.
- The desktop hero CTAs are hidden; the next visible signup CTA is near the bottom of the page. This is a notable conversion tradeoff to reconsider if taking inspiration from the design.

## UX strengths worth borrowing

1. Demonstrate the core interaction on the landing page. The live canvas conveys more than a product video would.
2. Give the AI a durable role. "Clover remembers and handles things" is clearer than a generic "AI-powered" label.
3. Make source material the starting point. Upload, link, and pasted text map naturally to how learners already work.
4. Keep signup progressive. Email first lowers the perceived commitment.
5. Bridge campaigns into product context. The quiz result becomes a prefilled Notebook conversation.
6. Use a small, semantic palette. Muted category colors help distinguish content without turning the product into a rainbow dashboard.
7. Preserve destination through auth. Deep links survive the login handoff.

## Risks and unresolved questions

- The actual product is almost entirely hidden before account creation, so the landing demo carries a large trust burden.
- It is not possible to judge lesson quality, tutor accuracy, authoring effort, progress mechanics, or retention loops from public access.
- The homepage promises proactive reminders and cross-service awareness; permission design and privacy explanation will be central to user trust.
- The mobile homepage hides its primary hero CTAs, leaving a long path to the next signup action.
- Some demo controls look fully functional while most Add-menu options are locked. A prospect may not know which capabilities exist today versus represent the roadmap.
- The course-gallery cards look actionable but only the expand/collapse control changed the public state during this review.
- The product spans preschool, university, professional skills, and test prep. That breadth is exciting, but an early product may need a much narrower initial user and outcome.
- Paid tiers do not currently exist in the live flow, so willingness-to-pay and packaging cannot be inferred.

## Authenticated areas not observed

`robots.txt` names the following protected or non-indexed route families:

- `/dashboard/`
- `/practice/`
- `/lesson/`
- `/notebook/`
- `/settings/`
- `/onboarding/`
- `/study/`
- `/courses/`
- `/home/`
- `/exam/`
- `/learn/`
- `/my-course/`

I directly confirmed login gating for Dashboard, Notebook, and the course catalog handoff. The other names are information-architecture signals only; no claim is made here about their current UI or completeness.

Source: [robots.txt](https://www.paradigm.study/robots.txt).

## Practical scope interpretation

If using Paradigm only as inspiration, a sensible first product slice would be:

1. Goal and source-material intake.
2. AI-generated linear route, without a freeform canvas initially.
3. Lesson/activity view with tutor chat.
4. Progress and resume state.
5. Simple notes.
6. Authentication and one protected home screen.

The visual canvas, proactive reminders, Google integrations, shared course catalog, authoring tools, advanced activity types, and social campaigns can be layered on after the core learning loop proves useful.
