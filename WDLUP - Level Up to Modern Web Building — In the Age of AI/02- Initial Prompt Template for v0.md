# ==============================
# INSTRUCTION (what to do)
# ==============================
Build a fully static, responsive marketing/personal website using:
- Next.js (App Router), TypeScript
- Tailwind CSS
- MUI (Material UI) components where appropriate

Non-negotiable constraints:
- Accessibility-first (semantic HTML, keyboard navigation, visible focus states, sufficient contrast)
- Responsive design (mobile-first, good tablet/desktop layouts)
- Avoid inline styles (do not use React style prop). Prefer Tailwind classes and/or MUI theming/styled approaches.
- Keep it fully static: no server actions, no API routes, no auth, no databases. (Static content only.)
- Create clean component structure and reusable section components.

Editing & future-proofing:
- Put ALL site copy, links, and repeated content in a single content file (e.g., src/content/content.ts)
- Make the content structure i18n-ready by default:
  - Use content.en and content.es dictionaries, even if we only render one language for now
  - Do NOT implement complex i18n routing unless explicitly requested
- Add clear TODO placeholders for missing assets or copy

SEO & shareability (auto-generate from provided content; do not ask the user for SEO copy):
- Generate a sensible default <title> and meta description using suitable 'name/title' and 'taglines' definitions.
- Use semantic HTML and correct heading hierarchy (exactly one H1 on each page).
- Add Open Graph + Twitter card metadata (title/description derived from the same sources).
- Generate robots.txt and sitemap.xml suitable for a static site.
- Include favicon placeholders and reasonable defaults.
- Use descriptive link text and internal navigation that supports scanning.
- Add alt text placeholders for non-decorative images; decorative images should have empty alt.

Analytics integration (disabled by default):
- Google Analytics (GA4). Implement it so analytics is enabled only if a Google Analytics ID is provided in the content/config file.
- If the ID is missing/empty, do not load any analytics scripts and do not reference analytics anywhere.

## STRUCTURAL INTEGRITY REQUIREMENTS:

- Respect the existing initialized project structure.
- Do not introduce a /src directory unless the project already uses one.
- Ensure all import paths match the tsconfig alias configuration.
- If alias configuration is unclear, use relative imports.
- Verify all pages render correctly before declaring completion.
- Avoid file structure conflicts.

## POST-GENERATION VALIDATION:

Before declaring the project complete:
- Ensure no unresolved imports exist.
- Ensure all routes render visible content.
- Ensure layout.tsx renders children correctly.
- Ensure no blank screens.

# ==============================
# CONTEXT (background info)
# - v0 3-input framework:
#   1) Product surface
#   2) Context of use
#   3) Constraints & taste
# ==============================

## (1) PRODUCT SURFACE
Type of site: {{site_type}}            # e.g., personal, consultant, portfolio, small business
Pages or sections: {{structure}}        # e.g., single-page w/ anchors OR multi-page sitemap
Required modules/sections:
{{modules_list}}                        # e.g., Hero, Services, Work, Testimonials, About, Contact, FAQ, Footer

## (2) CONTEXT OF USE
Used by: {{audience}}                   # e.g., potential clients, recruiters, collaborators
In what moment: {{moment}}              # e.g., quickly evaluating credibility, ready to contact
To achieve: {{outcome}}                 # e.g., book a call, send an inquiry, download a CV

Primary CTA: {{primary_cta}}            # e.g., "Book a call", "Contact me", "Get a quote"
Secondary CTAs: {{secondary_ctas}}      # optional

## (3) CONSTRAINTS & TASTE (design rules)
Visual style: {{style_keywords}}        # e.g., minimalist, black & white, editorial, clean
Color constraints: {{colors}}           # e.g., black/white + 1 accent
Typography direction: {{typography}}    # e.g., modern sans + subtle mono accents
UI rules: {{ui_rules}}                  # e.g., lots of whitespace, sharp corners, subtle animations
Inspiration references (optional): {{inspo_links}}

Above-the-fold priority (first 20 seconds):
- Must show: {{above_fold_must_show}}                # headline, CTA, proof, etc.

# ==============================
# OUTPUT INDICATOR (format requirements)
# ==============================
Output a Next.js project structure with:
- App Router routes/pages that match the chosen structure
- src/components/sections/* for section components (Hero, About, etc.)
- Reusable section components
- A single content file: src/content/content.ts with the different dictionaries for each language
- Tailwind for layout/spacing/typography, MUI used consistently for common UI primitives
- TODO placeholders for missing content/assets


Also include:
1) PROMPTING_GUIDE.md (for a non-technical user) with:
   - A short explanation of iterative prompting in v0
   - A reusable SPEC/STATE (anti-drift) block template
   - The “Incremental Change / Patch Request” prompt pattern (“Change ONLY X, keep everything else unchanged”)
   - 8 ready-to-use refinement prompts (layout, typography, spacing, mobile, CTA, accessibility, content, final polish)
   - a description of the generated site, that we can keep as updateable context for consistency


# ==============================
# INPUT DATA (the actual content to use)
# ==============================
Use these placeholders as initial copy and structure them well.
Mark any missing content clearly as TODO placeholders.

Brand/name:
- Name: {{name}}
- Tagline: {{tagline}}
- Short bio: {{short_bio}}

Offer / services (if applicable):
{{services_list}}

Work / portfolio items (if applicable):
{{portfolio_items}}

Proof / credibility (pick whatever exists):
{{testimonials_or_metrics_or_credentials, or otherwise indicate we'll be using an integration for this like Senja}}

Links:
- Email: {{email_or_placeholder}}
- WhatsApp: {{whatsapp_or_placeholder}}
- Scheduling link (optional): {{scheduling_link}}
- Social links (LinkedIn/GitHub/Instagram/etc.): {{social_links}}

Assets:
- Headshot/photo (optional): {{headshot_status}}      # provided | not provided (use placeholder)
- Logo (optional): {{logo_status}}                    # provided | not provided (typographic logo)
- Images/screenshots (optional): {{image_assets}}     # provided | not provided (use placeholders)

Internationalization (i18n):
- Languages (if yes): {{languages}}
- Default language: {{default_language}}

Analytics (optional):
- Google Analytics ID (GA4): {{ga_id_or_empty}}   # e.g., G-XXXXXXXXXX (leave empty to disable)

Notes / extra constraints:
{{extra_notes}}


IMAGE STRATEGY (CONDITIONAL):

If image assets are marked as "not provided":
- Generate high-quality placeholder images using v0 image generation.
- Use a consistent visual style aligned with the brand.
- Keep image generation minimal to reduce usage.
- For product listings with multiple items, generate ONE high-quality representative product image and reuse it across items.

If image assets are marked as "provided":
- Do NOT generate new images.
- Use placeholder image containers clearly labeled for replacement.
- Use clear visual placeholder labels (e.g., “Replace with your logo”) instead of code comments.
