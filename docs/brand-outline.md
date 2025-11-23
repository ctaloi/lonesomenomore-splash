# Lonesome No More - Brand Outline & Design System

**Version:** 1.0
**Last Updated:** January 2025
**Purpose:** Comprehensive brand guidelines for developers, designers, and AI agents working on Lonesome No More

---

## Table of Contents

1. [Brand Overview](#brand-overview)
2. [Design Tokens](#design-tokens)
3. [Typography](#typography)
4. [Color System](#color-system)
5. [Spacing & Layout](#spacing--layout)
6. [Components](#components)
7. [Voice & Tone](#voice--tone)
8. [Imagery & Visual Style](#imagery--visual-style)
9. [Accessibility](#accessibility)
10. [Code Examples](#code-examples)

---

## Brand Overview

### Mission
Lonesome No More provides personalized AI companionship through simple phone conversations, helping seniors stay connected while giving families peace of mind.

### Brand Personality
- **Warm & Compassionate** - Like a trusted family friend
- **Trustworthy & Professional** - Handling sensitive information with care
- **Accessible & Simple** - No technical barriers
- **Nature-Inspired** - Grounded, organic, calm

### Target Audience
**Primary:** Adult children (40-65) caring for aging parents
**Secondary:** Senior living facilities, professional caregivers
**End Users:** Seniors (70+) who may have limited tech experience

### Core Values
- **Human Connection** - Technology should bring people together
- **Dignity & Respect** - Every senior deserves personalized care
- **Simplicity** - Complexity is a barrier to care
- **Family-Owned Heart** - Labor of love, built in Buffalo, NY

---

## Design Tokens

### CSS Variables
All design tokens are defined as CSS custom properties in `:root`. Always use these variables instead of hard-coded values.

```css
:root {
    /* Colors - Nature-inspired palette optimized for seniors */
    --primary-color: #5F7A61;        /* Deep sage green - wellness, nature */
    --secondary-color: #D4735E;      /* Warm terra cotta - warmth, connection */
    --accent-color: #E8AA6B;         /* Honey amber - optimism, energy */
    --text-dark: #2C2C2C;            /* Deep charcoal - high contrast */
    --text-medium: #5A5A5A;          /* Warm gray - readable secondary text */
    --bg-cream: #FBF8F3;             /* Warm cream - inviting background */
    --bg-light: #FFFEFB;             /* Soft white with warm tint */

    /* Shadow System - Subtle, nature-inspired */
    --shadow-xs: 0 1px 2px rgba(92, 122, 97, 0.05);
    --shadow-sm: 0 2px 8px rgba(92, 122, 97, 0.08);
    --shadow-md: 0 4px 16px rgba(92, 122, 97, 0.1);
    --shadow-lg: 0 8px 24px rgba(92, 122, 97, 0.12);
    --shadow-xl: 0 12px 32px rgba(92, 122, 97, 0.15);
    --shadow-2xl: 0 16px 48px rgba(92, 122, 97, 0.18);

    /* Spacing Scale - 8px base unit */
    --space-xs: 8px;
    --space-sm: 16px;
    --space-md: 24px;
    --space-lg: 32px;
    --space-xl: 48px;
    --space-2xl: 64px;
    --space-3xl: 80px;

    /* Border Radius Scale */
    --radius-sm: 8px;
    --radius-md: 12px;
    --radius-lg: 16px;
    --radius-xl: 20px;
    --radius-2xl: 24px;

    /* Transitions - Smooth, professional feel */
    --transition-fast: 150ms cubic-bezier(0.4, 0, 0.2, 1);
    --transition-base: 250ms cubic-bezier(0.4, 0, 0.2, 1);
    --transition-slow: 350ms cubic-bezier(0.4, 0, 0.2, 1);
}
```

### Form-Specific Tokens
For forms and data entry interfaces:

```css
--input-border: #D1D5DB;
--input-focus: #5F7A61;
--error-color: #DC2626;
--success-color: #059669;
```

---

## Typography

### Font Families

**Primary Font (Body Text):** Inter
- Used for: Body copy, UI elements, forms, captions
- Fallback: `-apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif`

**Display Font (Headlines):** Merriweather
- Used for: Page titles, section headers, major headings
- Weight: 300 (Light), 400 (Regular), 700 (Bold)

### Implementation
```css
body {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
}

h1, h2, h3, .section-title, .logo {
    font-family: 'Merriweather', serif;
}
```

### Type Scale

| Element | Size | Weight | Line Height | Usage |
|---------|------|--------|-------------|-------|
| Hero Title (h1) | 3.8rem | 700 | 1.2 | Main page title with logo |
| Page Title | 2.5rem | 700 | 1.3 | Welcome screens, major sections |
| Section Title (h2) | 2.4rem | 700 | 1.3 | Section headers |
| Subsection (h3) | 1.5-2rem | 700 | 1.3 | Card titles, subsections |
| Large Body | 1.3rem | 400 | 1.85 | Intro paragraphs, emphasis |
| Body Text | 1.05-1.25rem | 400 | 1.7-1.8 | Standard content |
| Small Text | 0.9-0.95rem | 400 | 1.6 | Captions, helper text |

### Senior-Friendly Typography Rules

**DO:**
- Use minimum 19px base font size (larger than standard 16px)
- Maintain 1.6+ line height for readability
- Use high contrast (text-dark on light backgrounds)
- Keep paragraph widths under 720px (60-75 characters)

**DON'T:**
- Use font sizes smaller than 0.9rem
- Use pure gray on white (always use warm grays)
- Use italic for long passages
- Use all-caps for more than a few words

---

## Color System

### Primary Palette

#### Sage Green (`--primary-color: #5F7A61`)
**Meaning:** Wellness, nature, trust, calm
**Usage:**
- Primary buttons and CTAs (when not using secondary)
- Section titles and headers
- Icons for health/wellness features
- Borders on focus states

**Accessibility:** WCAG AA compliant on white backgrounds for large text

#### Terra Cotta (`--secondary-color: #D4735E`)
**Meaning:** Warmth, human connection, energy
**Usage:**
- Primary action buttons (beta signup, phone calls)
- Profile image borders (Sophie, Ms. Walker)
- Accent icons (hearts, people)
- Hover states for important actions

**Examples:**
```css
.btn-beta {
    background: linear-gradient(135deg, var(--secondary-color), #C8654F);
}
```

#### Honey Amber (`--accent-color: #E8AA6B`)
**Meaning:** Optimism, energy, highlights
**Usage:**
- Coming soon badges
- Notification highlights
- Underlines and decorative elements
- "Learn more" links

### Text Colors

```css
--text-dark: #2C2C2C;      /* Primary text - high contrast */
--text-medium: #5A5A5A;    /* Secondary text, descriptions */
```

**Usage Rules:**
- Headlines and body text: `--text-dark`
- Descriptions, helper text, captions: `--text-medium`
- Never use pure black (#000000)
- Never use text lighter than `--text-medium` on light backgrounds

### Background Colors

```css
--bg-cream: #FBF8F3;       /* Main page background */
--bg-light: #FFFEFB;       /* Card backgrounds, sections */
```

**Usage:**
- Page body: `--bg-cream`
- Cards, modals, elevated surfaces: `--bg-light`
- Alternating sections for visual rhythm

### Semantic Colors

#### Success
```css
--success-color: #059669;  /* Confirmations, completed states */
```

#### Error
```css
--error-color: #DC2626;    /* Validation errors, warnings */
```

### Gradients

**Primary Gradient (Sage to Amber):**
```css
background: linear-gradient(90deg, var(--primary-color), var(--accent-color));
```
Used for: Progress bars, underlines, decorative elements

**Secondary Gradient (Terra Cotta):**
```css
background: linear-gradient(135deg, var(--secondary-color), #C8654F);
```
Used for: Primary CTAs, important buttons

**Section Background Gradients:**
```css
background: linear-gradient(135deg,
    rgba(232, 170, 107, 0.04) 0%,
    rgba(95, 122, 97, 0.04) 100%);
```
Used for: Subtle section differentiation

---

## Spacing & Layout

### Spacing Scale (8px Base Unit)

All spacing should use multiples of 8px for visual consistency:

```css
--space-xs: 8px;    /* Tight spacing - icon gaps, small padding */
--space-sm: 16px;   /* Form field gaps, button padding */
--space-md: 24px;   /* Card padding, section spacing */
--space-lg: 32px;   /* Large card padding */
--space-xl: 48px;   /* Section padding vertical */
--space-2xl: 64px;  /* Major section breaks */
--space-3xl: 80px;  /* Page section padding */
```

### Layout Containers

**Standard Container:**
```css
.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}
```

**Narrow Content (Reading):**
```css
max-width: 900px;   /* Forms, long-form content */
max-width: 720px;   /* Optimal reading width */
max-width: 600px;   /* Focused content, thank you pages */
```

### Grid Patterns

**Three Column Grid:**
```css
.steps-grid, .benefits-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 35px;
}

@media (max-width: 980px) {
    grid-template-columns: 1fr;
}
```

**Four Column Grid:**
```css
.beta-benefits-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: var(--space-lg);
}

@media (max-width: 980px) {
    grid-template-columns: repeat(2, 1fr);
}

@media (max-width: 600px) {
    grid-template-columns: 1fr;
}
```

### Section Padding

```css
section {
    padding: var(--space-3xl) var(--space-md);  /* 80px vertical, 24px horizontal */
}

@media (max-width: 768px) {
    section {
        padding: var(--space-2xl) var(--space-md);  /* 64px vertical on mobile */
    }
}
```

---

## Components

### Buttons

#### Primary Button (Sage Green)
```css
.btn-primary {
    background: var(--primary-color);
    color: white;
    padding: 14px 32px;
    border-radius: var(--radius-md);
    font-size: 1.05rem;
    font-weight: 600;
    border: none;
    cursor: pointer;
    transition: all var(--transition-base);
}

.btn-primary:hover {
    background: #4D6350;
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(95, 122, 97, 0.2);
}
```

#### Beta/Action Button (Terra Cotta)
```css
.btn-beta {
    background: linear-gradient(135deg, var(--secondary-color), #C8654F);
    color: white;
    padding: 18px 40px;
    border-radius: var(--radius-md);
    font-size: 1.2rem;
    font-weight: 600;
    box-shadow: 0 4px 16px rgba(212, 115, 94, 0.3);
    transition: all var(--transition-base);
}

.btn-beta:hover {
    transform: translateY(-4px);
    box-shadow: 0 8px 24px rgba(212, 115, 94, 0.4);
    background: linear-gradient(135deg, #C8654F, var(--secondary-color));
}
```

#### Secondary Button (Outlined)
```css
.btn-secondary {
    background: white;
    color: var(--text-dark);
    border: 2px solid var(--input-border);
    padding: 14px 32px;
    border-radius: var(--radius-md);
    font-size: 1.05rem;
    font-weight: 600;
    transition: all var(--transition-base);
}

.btn-secondary:hover {
    border-color: var(--primary-color);
    color: var(--primary-color);
}
```

#### Success Button
```css
.btn-success {
    background: var(--success-color);
    color: white;
    font-size: 1.15rem;
    padding: 16px 40px;
    border-radius: var(--radius-md);
    font-weight: 600;
}
```

### Cards

#### Step Card (How It Works)
```css
.step-card {
    background: var(--bg-light);
    padding: var(--space-xl) var(--space-lg);
    border-radius: var(--radius-lg);
    text-align: center;
    box-shadow: var(--shadow-sm);
    border: 1px solid rgba(95, 122, 97, 0.08);
    transition: all var(--transition-base);
}

.step-card:hover {
    transform: translateY(-12px) scale(1.02);
    box-shadow: var(--shadow-xl);
    border-color: var(--primary-color);
}
```

**Visual Elements:**
- Numbered badge (1, 2, 3) with circular background
- Top colored border that scales in on hover
- Subtle radial gradient overlay

#### Benefit Card
```css
.benefit-card {
    background: var(--bg-light);
    text-align: center;
    padding: var(--space-xl) var(--space-lg);
    border-radius: var(--radius-lg);
    border: 1px solid rgba(95, 122, 97, 0.08);
    box-shadow: var(--shadow-sm);
    transition: all var(--transition-base);
}

.benefit-card:hover {
    transform: translateY(-6px);
    box-shadow: var(--shadow-xl);
}
```

#### Testimonial Card
```css
.testimonial-card {
    background: var(--bg-light);
    padding: var(--space-xl) var(--space-lg);
    border-radius: var(--radius-lg);
    border: 1px solid rgba(95, 122, 97, 0.08);
    box-shadow: var(--shadow-sm);
    position: relative;
}

/* Left accent bar on hover */
.testimonial-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 4px;
    height: 100%;
    background: linear-gradient(180deg, var(--secondary-color), var(--accent-color));
    border-radius: var(--radius-sm) 0 0 var(--radius-sm);
    transform: scaleY(0);
    transition: transform var(--transition-base);
}

.testimonial-card:hover::before {
    transform: scaleY(1);
}
```

#### Section Card (Form Pages)
```css
.section-card {
    background: white;
    border-radius: var(--radius-xl);
    padding: 40px;
    box-shadow: var(--shadow-lg);
    border: 1px solid rgba(95, 122, 97, 0.1);
    margin-bottom: 30px;
}
```

### Form Elements

#### Text Inputs
```css
input[type="text"],
input[type="email"],
input[type="tel"],
textarea,
select {
    width: 100%;
    padding: 12px 16px;
    border: 2px solid var(--input-border);
    border-radius: var(--radius-md);
    font-size: 1rem;
    font-family: inherit;
    transition: all var(--transition-base);
    background: white;
}

input:focus,
textarea:focus,
select:focus {
    outline: none;
    border-color: var(--input-focus);
    box-shadow: 0 0 0 3px rgba(95, 122, 97, 0.1);
}
```

#### Labels
```css
label {
    display: block;
    font-weight: 600;
    margin-bottom: 8px;
    color: var(--text-dark);
    font-size: 1rem;
}

.label-optional {
    font-weight: 400;
    color: var(--text-medium);
    font-size: 0.9rem;
}
```

#### Field Descriptions
```css
.field-description {
    font-size: 0.9rem;
    color: var(--text-medium);
    margin-top: 4px;
    font-style: italic;
    line-height: 1.5;
}
```

#### Example Boxes
```css
.example-box {
    background: rgba(95, 122, 97, 0.05);
    border-left: 4px solid var(--accent-color);
    padding: 16px 20px;
    margin-top: 16px;
    border-radius: 4px;
}

.example-label {
    font-weight: 600;
    color: var(--primary-color);
    margin-bottom: 8px;
    font-size: 0.9rem;
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

.example-text {
    color: var(--text-dark);
    font-style: italic;
    line-height: 1.7;
}
```

### Icons

**Library:** Font Awesome 6.4.0

**Icon Sizing:**
- Small icons (in text): 1rem - 1.2rem
- Standard icons: 1.5rem - 2rem
- Feature icons: 2.5rem - 3.2rem
- Hero icons: 4rem - 5rem

**Icon Colors:**
- Primary features: `var(--primary-color)`
- Warm/human features: `var(--secondary-color)`
- Highlights/energy: `var(--accent-color)`

**Common Icon Usage:**
```html
<i class="fas fa-heart"></i>          <!-- Love, care, favorites -->
<i class="fas fa-phone"></i>          <!-- Call to action -->
<i class="fas fa-comments"></i>       <!-- Conversation, chat -->
<i class="fas fa-user-circle"></i>    <!-- User profiles -->
<i class="fas fa-clock"></i>          <!-- 24/7 availability -->
<i class="fas fa-shield-alt"></i>     <!-- Privacy, security -->
```

### Profile Images

```css
.profile-image {
    width: 180px;
    height: 180px;
    border-radius: 50%;
    object-fit: cover;
    border: 6px solid var(--primary-color); /* or var(--secondary-color) */
    box-shadow: 0 8px 24px rgba(95, 122, 97, 0.25);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.profile-image:hover {
    transform: scale(1.05);
    box-shadow: 0 12px 32px rgba(95, 122, 97, 0.35);
}
```

**Border Colors:**
- Primary color (sage): For AI companions (Sophie)
- Secondary color (terra cotta): For warm, personal touches (Ms. Walker)

### Badges

```css
.coming-soon-badge {
    display: inline-block;
    background: var(--accent-color);
    color: white;
    padding: 12px 32px;
    border-radius: 50px;
    font-size: 1.1rem;
    font-weight: 600;
    letter-spacing: 0.5px;
    text-transform: uppercase;
    box-shadow: 0 4px 12px rgba(232, 170, 107, 0.3);
}
```

### Progress Indicators

```css
.progress-bar {
    width: 100%;
    height: 8px;
    background: #E5E7EB;
    border-radius: 999px;
    overflow: hidden;
}

.progress-fill {
    height: 100%;
    background: linear-gradient(90deg, var(--primary-color), var(--accent-color));
    border-radius: 999px;
    transition: width 0.3s ease;
}
```

### Section Headers

```css
.section-title {
    font-family: 'Merriweather', serif;
    font-size: 2.4rem;
    color: var(--primary-color);
    text-align: center;
    margin-bottom: var(--space-2xl);
    font-weight: 700;
    letter-spacing: -0.01em;
}

/* Decorative underline */
.section-title::after {
    content: '';
    position: absolute;
    bottom: -16px;
    left: 50%;
    transform: translateX(-50%);
    width: 80px;
    height: 5px;
    background: linear-gradient(90deg, var(--accent-color), var(--secondary-color));
    border-radius: 3px;
    box-shadow: 0 2px 8px rgba(232, 170, 107, 0.3);
}
```

---

## Voice & Tone

### Brand Voice Characteristics

**Warm & Personal**
- Write like you're talking to a family member
- Use "you" and "your loved one"
- Be conversational, not corporate

**Clear & Simple**
- Short sentences and paragraphs
- Avoid jargon and technical terms
- Explain AI concepts in human terms

**Empathetic & Reassuring**
- Acknowledge the difficulty of caregiving
- Show understanding of senior challenges
- Provide reassurance about privacy and safety

**Authentic & Honest**
- Don't overpromise
- Be transparent about beta status
- Acknowledge limitations

### Tone by Context

#### Marketing Pages (Landing Page)
- **Warm and reassuring**
- Lead with benefits, not features
- Use emotional storytelling
- Example: "Companionship for your loved ones, peace of mind for you"

#### Forms & Onboarding
- **Helpful and encouraging**
- Explain why you're asking
- Provide examples generously
- Example: "The more detail you provide, the more personalized the experience"

#### Error/Validation Messages
- **Gentle and constructive**
- Never blame the user
- Provide clear next steps
- Example: "We need your email to send weekly summaries" (not "Error: Email required")

#### Success States
- **Celebratory but humble**
- Acknowledge the user's effort
- Set clear expectations for next steps
- Example: "Thank you! We're excited to set up personalized AI companionship for your loved one."

### Writing Guidelines

**DO:**
- Use contractions (we'll, you're, it's)
- Lead with empathy ("We know caring for aging parents is hard")
- Use active voice ("We'll call them" not "They will be called")
- Write in second person ("you") for families, third person ("they/them") for seniors
- Use specific examples (actual names, scenarios)
- Keep paragraphs under 4 lines

**DON'T:**
- Use medical jargon without explanation
- Say "elderly" or "the elderly" (say "seniors" or "older adults")
- Use infantilizing language ("sweetie," "dear")
- Make promises you can't keep
- Use fear-based marketing
- Write in all caps (except acronyms)

### Key Messaging

**What We Do:**
- "Personalized AI companionship through phone conversations"
- NOT: "Automated calling system" or "Chatbot service"

**Our Value:**
- "Meaningful conversations" not "entertainment"
- "Peace of mind" not "monitoring"
- "Companionship" not "therapy" or "care"

**The Technology:**
- "AI companion" not "artificial intelligence bot"
- "Remembers everything" not "stores conversation data"
- "Natural conversations" not "voice recognition technology"

### Copywriting Patterns

**Headlines:**
- Benefit-driven: "Companionship for your loved ones, peace of mind for you"
- Question format: "What if your loved one always had someone to talk to?"
- Direct value: "24/7 AI Companionship Through Simple Phone Calls"

**Subheadings:**
- Add context and detail to headlines
- Keep under 25 words
- Use active, descriptive language

**Body Copy:**
- Start with the user's pain point
- Explain the solution simply
- End with a clear call to action

**Button Copy:**
- Action-oriented verbs: "Get Started," "Join Beta," "Call Now"
- Avoid generic "Submit" or "Click Here"
- Add context when helpful: "Review & Submit Beta Intake"

### Example Copy Patterns

**Feature Introduction:**
```
[Icon/Visual]
Truly Personalized

Choose the perfect voice and personality. We learn their history,
interests, and preferences to make every conversation genuinely
meaningful and engaging.
```

**How It Works Step:**
```
[Step Number Badge]
Share Their Story

Tell us about your loved one's background, interests, favorite topics,
and life experiences. We'll use this to create truly personalized
conversations.
```

**Call to Action:**
```
Ready to set up AI companionship for your loved one?

[Primary Button: Get Started]

Questions? Call us at (833) 817-4646 or email hello@lonesomenomore.com
```

---

## Imagery & Visual Style

### Photography Style

**Characteristics:**
- **Authentic & Unstaged** - Real people, real moments
- **Warm Lighting** - Natural, golden hour, soft indoor lighting
- **Close, Personal Framing** - Focus on faces and hands
- **Genuine Emotion** - Real smiles, tender moments

**What to Show:**
- Seniors engaged in conversation (on phone)
- Intergenerational family moments
- Seniors in their natural environments (home, garden)
- Close-ups of hands holding phones
- Facial expressions showing joy, contentment, engagement

**What to Avoid:**
- Stock photo "models" looking overly posed
- Clinical/medical environments
- Isolated, sad seniors
- Technology-heavy imagery (laptops, tablets, complex devices)
- Overly active seniors (don't whitewash aging)

### Profile Images (AI Companions)

**Current Examples:**
- Sophie: AI companion for demo calls
- Ms. Walker: AI onboarding specialist

**Style Rules:**
- Circular crop (50% border-radius)
- 6px colored border (primary or secondary color)
- Drop shadow: `0 8px 24px rgba(95, 122, 97, 0.25)`
- Hover effect: scale(1.05) with enhanced shadow
- Warm, approachable expressions
- Professional but friendly appearance

**Border Color Meaning:**
- Sage green border: Primary AI companions
- Terra cotta border: Warm, personal roles (onboarding, family-focused)

### Iconography

**Primary Library:** Font Awesome 6.4.0 (free tier)

**Icon Style:**
- Use solid icons (`fas`) for most cases
- Regular icons (`far`) for less emphasis
- Maintain consistent sizing within sections

**Semantic Color Usage:**
```
Hearts, care, favorites → Secondary color (terra cotta)
Wellness, nature, trust → Primary color (sage)
Energy, highlights, new → Accent color (amber)
Technical, neutral → Text medium gray
```

### Illustrations

**Not currently in use, but if added:**
- Hand-drawn, sketch-like quality
- Nature-inspired motifs (leaves, birds, gardens)
- Warm color palette matching brand
- Supportive, not primary focus

### Background Treatments

**Subtle Texture:**
```css
/* Noise overlay for depth */
body::before {
    content: '';
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url("data:image/svg+xml,...");
    pointer-events: none;
    opacity: 0.4;
}
```

**Gradient Orbs (Ambient Background):**
```css
/* Floating, blurred gradient circles */
.hero::before {
    content: '';
    position: absolute;
    width: 600px;
    height: 600px;
    background: radial-gradient(circle,
        rgba(232, 170, 107, 0.12) 0%,
        rgba(232, 170, 107, 0.04) 40%,
        transparent 70%);
    border-radius: 50%;
    filter: blur(60px);
    animation: float 20s ease-in-out infinite;
}
```

**Radial Gradients (Section Backgrounds):**
```css
background: radial-gradient(ellipse 150% 100% at 50% 0%,
    rgba(232, 170, 107, 0.06) 0%,
    transparent 50%);
```

---

## Accessibility

### Senior-Friendly Design Principles

**Already Implemented:**

1. **Large Base Font Size**
   - 19px body text (vs industry standard 16px)
   - Minimum 0.9rem (17px) for small text
   - Never go below this threshold

2. **High Contrast Text**
   - Text-dark (#2C2C2C) on light backgrounds
   - Warm grays (#5A5A5A) for secondary text
   - Never pure gray on white

3. **Generous Line Height**
   - 1.6-1.8 for body text
   - 1.3 for headlines
   - Ample breathing room

4. **Large Touch Targets**
   - Buttons minimum 44px height
   - 16px+ padding on all sides
   - Adequate spacing between interactive elements

5. **Simple, Clear Language**
   - Short sentences
   - Familiar vocabulary
   - No jargon without explanation

### WCAG Compliance

**Target:** WCAG 2.1 AA

**Color Contrast:**
- Text-dark on bg-light: 14.8:1 (AAA) ✓
- Text-medium on bg-light: 7.4:1 (AA) ✓
- Primary color large text: 4.8:1 (AA) ✓

**Focus States:**
```css
*:focus-visible {
    outline: 3px solid var(--accent-color);
    outline-offset: 2px;
}

a:focus-visible {
    outline: 2px solid var(--accent-color);
    outline-offset: 4px;
    border-radius: var(--radius-sm);
}
```

**Keyboard Navigation:**
- All interactive elements must be keyboard accessible
- Logical tab order (top to bottom, left to right)
- Skip links for long forms
- Clear focus indicators

**ARIA Labels:**
```html
<!-- Expandable sections -->
<button aria-expanded="false" aria-controls="faq-1">
    Question text
</button>

<!-- Progress indicators -->
<div role="progressbar" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">

<!-- Form validation -->
<input aria-invalid="true" aria-describedby="email-error">
<span id="email-error" role="alert">Please enter a valid email</span>
```

### Motion & Animation

**Respect User Preferences:**
```css
@media (prefers-reduced-motion: reduce) {
    *,
    *::before,
    *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
        scroll-behavior: auto !important;
    }
}
```

**Animation Guidelines:**
- Subtle, purposeful animations only
- No auto-playing videos or carousels
- Hover states should not be required for information
- Loading states for async operations

### Form Accessibility

**Labels:**
- Every input must have a visible label
- Never use placeholder as label
- Clear, descriptive label text

**Helper Text:**
```html
<label for="email">Your Email</label>
<input type="email" id="email" aria-describedby="email-help">
<p class="field-description" id="email-help">
    We'll send weekly summaries to this email
</p>
```

**Required Fields:**
```html
<label for="name">Your Name *</label>
<input type="text" id="name" required aria-required="true">
```

**Error Handling:**
- Clear, specific error messages
- Use color + icon (not color alone)
- Announce errors to screen readers with `role="alert"`

---

## Code Examples

### Creating a New Section

```html
<section class="[section-name]">
    <div class="container">
        <h2 class="section-title">Section Title</h2>
        <p style="text-align: center; max-width: 700px; margin: 0 auto 40px;
                  font-size: 1.15rem; color: var(--text-medium);">
            Section introduction text
        </p>

        <!-- Section content here -->
    </div>
</section>
```

### Creating a Card Grid

```html
<div class="benefits-grid">
    <div class="benefit-card">
        <div class="benefit-icon">
            <i class="fas fa-heart"></i>
        </div>
        <h3 class="benefit-title">Benefit Title</h3>
        <p class="benefit-description">
            Description of the benefit in clear, simple language.
        </p>
    </div>
    <!-- Repeat for more cards -->
</div>
```

### Creating a CTA Button

```html
<a href="beta-intake.html" class="btn btn-beta">
    <i class="fas fa-clipboard-list"></i>
    Get Started
</a>
```

### Creating a Form Field

```html
<div class="form-group">
    <label for="field-name">Field Label *</label>
    <input type="text" id="field-name" name="field_name" required>
    <p class="field-description">
        Helper text explaining why you need this information
    </p>
</div>
```

### Creating an Example Box

```html
<div class="example-box">
    <div class="example-label">Example Good Answer:</div>
    <div class="example-text">
        "Provide a detailed, specific example here that shows
        exactly what kind of response you're looking for."
    </div>
</div>
```

### Creating a Profile Section

```html
<div style="text-align: center; margin-bottom: 24px;">
    <img src="profile.jpg" alt="Name" class="profile-image"
         style="width: 180px; height: 180px; border-radius: 50%;
                object-fit: cover; border: 6px solid var(--primary-color);
                box-shadow: 0 8px 24px rgba(95, 122, 97, 0.25);">
    <div style="margin-top: 16px; font-family: 'Merriweather', serif;
                font-size: 1.3rem; font-weight: 600; color: var(--primary-color);">
        Person Name
    </div>
    <div style="font-size: 0.95rem; color: var(--text-medium); font-style: italic;">
        Role or Title
    </div>
</div>
```

### Creating Responsive Grids

```css
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: var(--space-lg);
}

/* Tablet */
@media (max-width: 980px) {
    .grid-container {
        grid-template-columns: repeat(2, 1fr);
    }
}

/* Mobile */
@media (max-width: 600px) {
    .grid-container {
        grid-template-columns: 1fr;
    }
}
```

### Adding Hover Effects

```css
.card {
    transition: all var(--transition-base);
}

.card:hover {
    transform: translateY(-6px);
    box-shadow: var(--shadow-xl);
}
```

### Creating FAQ Accordion

```html
<div class="faq-item">
    <button class="faq-question" aria-expanded="false">
        <span>Question text here?</span>
        <i class="fas fa-chevron-down faq-icon"></i>
    </button>
    <div class="faq-answer">
        <p>Answer text here with helpful information.</p>
    </div>
</div>
```

```javascript
document.querySelectorAll('.faq-question').forEach(button => {
    button.addEventListener('click', () => {
        const faqItem = button.parentElement;
        const isActive = faqItem.classList.contains('active');

        // Close all FAQs
        document.querySelectorAll('.faq-item').forEach(item => {
            item.classList.remove('active');
        });

        // Open clicked FAQ if it wasn't active
        if (!isActive) {
            faqItem.classList.add('active');
            button.setAttribute('aria-expanded', 'true');
        }
    });
});
```

---

## File Structure

```
lonesomenomore-splash/
├── index.html              # Main landing page
├── beta-intake.html        # Beta onboarding form
├── logo.png               # Primary logo (100x100px)
├── sophie.jpg             # AI companion profile (180x180px)
├── ms-walker.jpg          # Onboarding specialist profile (180x180px)
└── docs/
    └── brand-outline.md   # This document
```

---

## Quick Reference Cheatsheet

### Colors
```
Primary:    #5F7A61  (Sage green)
Secondary:  #D4735E  (Terra cotta)
Accent:     #E8AA6B  (Honey amber)
Text Dark:  #2C2C2C
Text Med:   #5A5A5A
BG Cream:   #FBF8F3
BG Light:   #FFFEFB
```

### Typography
```
Display:    Merriweather (headlines, titles)
Body:       Inter (everything else)
Base Size:  19px
Min Size:   0.9rem (17px)
Line H:     1.7-1.8
```

### Spacing
```
8px   16px   24px   32px   48px   64px   80px
XS    SM     MD     LG     XL     2XL    3XL
```

### Shadows
```
XS → SM → MD → LG → XL → 2XL
(Use sparingly, prefer SM and MD)
```

### Border Radius
```
8px   12px   16px   20px   24px
SM    MD     LG     XL     2XL
```

### Breakpoints
```
Mobile:  < 600px
Tablet:  < 768px
Desktop: < 980px
Wide:    1200px max container
```

---

## Version History

**v1.0 - January 2025**
- Initial brand outline created
- Documented existing design system from index.html and beta-intake.html
- Established voice & tone guidelines
- Created accessibility standards
- Added code examples and quick reference

---

## Contact & Questions

For questions about these brand guidelines or to suggest updates:

**Email:** hello@lonesomenomore.com
**Phone:** (833) 817-4646
**Location:** Buffalo, NY

---

*A family-owned labor of ❤️ • Built in Buffalo, NY*
