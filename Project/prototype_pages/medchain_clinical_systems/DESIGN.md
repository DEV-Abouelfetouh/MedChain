---
name: MedChain Clinical Systems
colors:
  surface: '#f8f9ff'
  surface-dim: '#cbdbf5'
  surface-bright: '#f8f9ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#eff4ff'
  surface-container: '#e5eeff'
  surface-container-high: '#dce9ff'
  surface-container-highest: '#d3e4fe'
  on-surface: '#0b1c30'
  on-surface-variant: '#3d4947'
  inverse-surface: '#213145'
  inverse-on-surface: '#eaf1ff'
  outline: '#6d7a77'
  outline-variant: '#bcc9c6'
  surface-tint: '#006a61'
  primary: '#00685f'
  on-primary: '#ffffff'
  primary-container: '#008378'
  on-primary-container: '#f4fffc'
  inverse-primary: '#6bd8cb'
  secondary: '#565e74'
  on-secondary: '#ffffff'
  secondary-container: '#dae2fd'
  on-secondary-container: '#5c647a'
  tertiary: '#0051d5'
  on-tertiary: '#ffffff'
  tertiary-container: '#316bf3'
  on-tertiary-container: '#fefcff'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#89f5e7'
  primary-fixed-dim: '#6bd8cb'
  on-primary-fixed: '#00201d'
  on-primary-fixed-variant: '#005049'
  secondary-fixed: '#dae2fd'
  secondary-fixed-dim: '#bec6e0'
  on-secondary-fixed: '#131b2e'
  on-secondary-fixed-variant: '#3f465c'
  tertiary-fixed: '#dbe1ff'
  tertiary-fixed-dim: '#b4c5ff'
  on-tertiary-fixed: '#00174b'
  on-tertiary-fixed-variant: '#003ea8'
  background: '#f8f9ff'
  on-background: '#0b1c30'
  surface-variant: '#d3e4fe'
typography:
  headline-xl:
    fontFamily: Plus Jakarta Sans
    fontSize: 40px
    fontWeight: '700'
    lineHeight: 48px
    letterSpacing: -0.02em
  headline-xl-mobile:
    fontFamily: Plus Jakarta Sans
    fontSize: 30px
    fontWeight: '700'
    lineHeight: 38px
    letterSpacing: -0.015em
  headline-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 32px
    fontWeight: '600'
    lineHeight: 40px
    letterSpacing: -0.015em
  headline-lg-mobile:
    fontFamily: Plus Jakarta Sans
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
    letterSpacing: -0.01em
  headline-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 18px
    fontWeight: '600'
    lineHeight: 26px
    letterSpacing: -0.005em
  body-lg:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
    letterSpacing: -0.005em
  body-md:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  body-sm:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
  label-lg:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '500'
    lineHeight: 20px
  label-md:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '500'
    lineHeight: 16px
  label-sm:
    fontFamily: Inter
    fontSize: 11px
    fontWeight: '600'
    lineHeight: 14px
    letterSpacing: 0.02em
  code-md:
    fontFamily: JetBrains Mono
    fontSize: 13px
    fontWeight: '500'
    lineHeight: 18px
  code-sm:
    fontFamily: JetBrains Mono
    fontSize: 11px
    fontWeight: '400'
    lineHeight: 14px
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  gutter: 1.5rem
  gutter-mobile: 1rem
  margin: 2rem
  margin-mobile: 1rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 1rem
  space-lg: 1.5rem
  space-xl: 2.5rem
---

## Brand & Style
The design system establishes a clinical, high-integrity visual language engineered for decentralized healthcare infrastructure, cryptographic patient records, and permissioned medical data access. The aesthetic combines institutional stability with cryptographic precision—balancing clinical clarity, absolute legibility, and high-density technical workflows.

### Aesthetic Foundation
- **Modern Clinical Precision:** Crisp architecture featuring sterile slate substrates, pure white elevated surfaces, and low-contrast borders. Interfaces feel sterile, surgical, and reliable.
- **Architectural Transparency:** Decentralized operations (smart contracts, consent revocations, cryptographic audits) are rendered transparent through structured ledger cards, hash-tag pills, and explicit state visualizers.
- **Target Audience:** Clinicians, radiologists, platform pharmacists, medical researchers, and patients managing cryptographically signed health credentials.
- **Emotional Intent:** Absolute security, compliance adherence (HIPAA/GDPR), zero-latency trust, and mental calm in high-stakes operational environments.

## Colors
The palette leverages a clinical hierarchy anchored by medical teal for primary verifications and actions, paired with deep clinical navy for grounding structures and institutional weight.

### Strategic Color Roles
- **Primary (`#0D9488` - Medical Teal):** The operational signifier. Designates active verifiable states, validated records, cryptographic proofs, primary calls to action, and interactive focus states.
- **Secondary (`#0F172A` - Clinical Navy):** The structural base. Governs headings, sidebar backgrounds in navigation modes, terminal outputs, and dominant typography to deliver unwavering authority.
- **Tertiary (`#2563EB` - Data Cobalt):** Dedicated to cryptographic linkages, public-key explorer redirects, signature transactions, and raw metric telemetry.
- **Neutral (`#64748B` - Slate Neutral):** Provides precise control over subtle boundary lines, secondary text, metadata timestamps, and resting state icons.

### Semantic Tiers
- **Approved / Active / Dispensed (`#059669` / `#0D9488`):** Unambiguous verification indicators for approved access tokens and verified medical dispensations.
- **Pending / In-Review (`#D97706` / `#F59E0B`):** Warm amber states denoting unconfirmed ledger transactions, awaiting doctor signature, or multi-sig delays.
- **Revoked / Terminated / Critical (`#E11D48` / `#BE123C`):** High-alert crimson for patient consent revocation, mismatched hash alerts, and contraindication flags.
- **Backgrounds & Surfaces:** Outer canvas defaults to `#F8FAFC`, structural panels use `#F1F5F9`, and interactive card surfaces utilize `#FFFFFF` with precise 1px stroke boundaries.

## Typography
The typographic hierarchy implements three specialized typefaces for clinical order:
1. **Plus Jakarta Sans (Headlines):** Delivers clean geometry, crisp modern terminals, and humanistic warmth to neutralize institutional sterility without compromising authority.
2. **Inter (Body & Controls):** Provides neutral, utilitarian micro-legibility for clinical notes, patient diagnostics, table columns, and form fields.
3. **JetBrains Mono (Technical Metadata & Telemetry):** Reserved for raw blockchain transaction hashes (`0x...`), smart contract IDs, FHIR resource paths, and HL7 data payloads.

### Hierarchy Guidelines
- Always display cryptographic addresses, signatures, and transaction IDs in `code-md` or `code-sm`.
- Form section headers must adhere to `headline-sm` with an uppercase tracking configuration for distinct separation.
- High-density table content uses `body-md` for patient values and `label-sm` for table headers with subdued contrast (`#64748B`).

## Layout & Spacing
The layout model employs a strict, high-density 12-column fluid grid system engineered for diagnostic dashboards, record ledgers, and audit tools.

### Grid Architecture
- **Desktop (≥ 1280px):** 12-column layout, 24px (`1.5rem`) gutters, 32px (`2rem`) outer canvas margins. Maximum readable container width is capped at 1440px for single-column medical records, while data tables span 100% of the viewport width.
- **Tablet (768px – 1279px):** 8-column layout, 16px (`1rem`) gutters, 24px (`1.5rem`) outer margin. Sidebars collapse to icon-only rails.
- **Mobile (< 768px):** 4-column layout, 16px (`1rem`) gutters, 16px (`1rem`) margins. Multi-pane diagnostic views stack sequentially into segmented cards.

### Spacing Principles
- Compact spacing scale (`space-xs` through `space-sm`) is dedicated strictly to inside table cells, status tags, and metadata groupings.
- Structural breathing room (`space-md` through `space-xl`) isolates interactive operational modules (e.g., patient identity summaries from immutable audit logs).

## Elevation & Depth
This design system rejects heavy, muddy shadows in favor of a crisp clinical layering model based on subtle borders, surface-container shifts, and tinted ambient diffusion.

### The Depth Scale
- **Level 0 (Canvas Substrate):** `#F8FAFC`. The foundational backdrop for the entire viewport.
- **Level 1 (Card & Workspace Panels):** Pure white (`#FFFFFF`) with a 1px border stroke of `#E2E8F0`. Elevation is anchored by an ambient micro-diffusion: `0 1px 3px 0 rgba(15, 23, 42, 0.04), 0 1px 2px -1px rgba(15, 23, 42, 0.02)`.
- **Level 2 (Popovers, Dropdowns, Role Pickers):** Pure white surface, bordered by `#CBD5E1`, with elevation `0 4px 6px -1px rgba(15, 23, 42, 0.08), 0 2px 4px -2px rgba(15, 23, 42, 0.04)`.
- **Level 3 (Modal Dialogs & Emergency Access Confirmations):** Pure white surface, paired with an overlay backdrop blur of 4px using `rgba(15, 23, 42, 0.45)`. Shadow: `0 20px 25px -5px rgba(15, 23, 42, 0.12), 0 8px 10px -6px rgba(15, 23, 42, 0.06)`.

### Ledger Depth Metaphor
Cards containing immutable data (ledger blocks, audited access events) adopt a flat surface with a distinct left accent line (3px solid `#0D9488` or `#E2E8F0`) rather than drop shadows, underscoring systemic permanence.

## Shapes
The design system operates with **Soft** geometric discipline (`roundedness: 1`), conveying clinical exactitude, stability, and institutional rigor.

### Shape Scale Rules
- **Base Components (Inputs, Buttons, Cells):** `rounded` (0.25rem / 4px). Creates sharp, reliable affordances that maximize screen real estate in dense medical data tables.
- **Containers & Record Cards:** `rounded-lg` (0.5rem / 8px). Used on patient summaries, diagnostic result panels, and cryptographic signature modules.
- **Modals & Flyouts:** `rounded-xl` (0.75rem / 12px). Softens dominant focus points during interactive flows.
- **Semantic Pills & Status Badges:** Fully rounded (`9999px` pill) to distinguish metadata attributes from actionable buttons and interactive cards.

## Components

### 1. Buttons
- **Primary Action (Verified Transaction / Submit):** Solid `#0D9488` background, white label, 4px border radius. Hover: `#0F766E`. Active: `#115E59`. Focus: 2px offset with ring `#0D9488`.
- **Secondary (Navy Outline / Authority):** Border 1px `#CBD5E1`, text `#0F172A`, background `#FFFFFF`. Hover: background `#F8FAFC`, border `#94A3B8`.
- **Danger (Revoke Access / Kill Session):** Background `#FFF1F2`, text `#BE123C`, border 1px `#FECDD3`. Hover: background `#FEE2E2`, border `#FDA4AF`.
- **Sizing:** Compact (32px height for in-table actions), Standard (40px height for forms).

### 2. Status & Role Badges
- **Status Badges:** Pill-shaped with a 6px status dot indicator.
  - *Active / Approved:* Background `#F0FDF4`, text `#15803D`, dot `#22C55E`.
  - *Pending / Mining:* Background `#FFFBEB`, text `#B45309`, dot `#F59E0B`.
  - *Revoked / Expired:* Background `#FFF1F2`, text `#BE123C`, dot `#F43F5E`.
- **Role Badges (Clinician, Patient, Auditor, Node Validator):** Squared pill (4px radius), `JetBrains Mono` label-sm text, background `#F1F5F9`, border `#E2E8F0`, text `#334155`.

### 3. High-Density Medical Data Tables
- **Header:** Sticky top, background `#F8FAFC`, border-bottom 1px `#E2E8F0`, text `label-sm` in `#64748B` with uppercase tracking.
- **Rows:** Minimum height 48px, background `#FFFFFF`, alternating hover state to `#F8FAFC`. Direct row border-bottom 1px `#F1F5F9`.
- **Cells:** Numeric and code data (vital signs, hashes, IDs) align right or use monospaced formatting. Inline action menus are pinned to the right edge.

### 4. Input Fields & Search Bars
- **Text Inputs:** Height 40px, background `#FFFFFF`, 1px border `#CBD5E1`, 4px radius. Focus: border `#0D9488`, box-shadow `0 0 0 2px rgba(13, 148, 136, 0.15)`.
- **Cryptographic Address Inputs:** Include embedded copy-to-clipboard action and ENS/record resolution indicator icon on the right edge.

### 5. Checkboxes & Radio Controls
- **Checkboxes:** 16x16px square with 3px radius. Unchecked: `#FFFFFF` with 1.5px border `#94A3B8`. Checked: `#0D9488` with crisp white checkmark SVG.

### 6. Cards & Containers
- **Standard Card:** Background `#FFFFFF`, border 1px `#E2E8F0`, 8px radius. Card header includes a 16px bottom border separator when housing dense medical histories.
- **Audit Block Card:** Styled with a solid 3px left border in `#0D9488`, featuring an inline block-height number tag in `JetBrains Mono`.

### 7. Specialized Domain Components
- **QR Code Containers:** Precision frame for patient identity verification and public key sharing. 1px border `#E2E8F0`, 8px padding, `#FFFFFF` interior, accompanied by an explicit time-to-live countdown badge below the code.
- **Consent Revocation Bar:** Persistent, high-priority utility banner rendered in `#FFF1F2` with `#BE123C` text, detailing currently active delegated emergency access sessions.