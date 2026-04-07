import { useState } from "react";

const LAYERS = {
  brain: {
    label: "BRAIN",
    icon: "🧠",
    subtitle: "Strategy, Copy, Analysis & Production Engine",
    color: "#E8B931",
    bgColor: "#2A2520",
    tools: [
      {
        name: "Claude Opus 4.6 (Pro)",
        role: "Primary brain — the hub everything flows through",
        tasks: [
          "All strategy & planning",
          "All copywriting (ads, emails, web, social)",
          "Prompt generation for every tool in the stack",
          "Client proposals & reports via Skills (.docx, .pptx, .pdf, .xlsx)",
          "SEO/AEO/GEO content writing & optimization",
          "Brand Continuity Sheets (replaces Pomelli Business DNA)",
          "🔥 BRAND DESIGN: 13-phase Brand Architect system — produces world-class brand identity (Brand DNA, archetypes, verbal identity, color science, typography, logo specs, design system, sonic branding, GEO entity-building, 16-folder file delivery)",
          "Campaign management & optimization",
          "Building custom Skills for repeatable tasks",
          "Interactive UI mockups via Artifacts (backup for Stitch)",
          "Interactive tools via Artifacts (backup for Opal)",
        ],
        cost: "$20/mo (paid)",
        priority: "CORE",
        stable: true,
        note: "BRAND DESIGN ASSET: You own a 13-phase Brand Design Master Prompt (31,000-42,000 words output per client). This alone replaces $5,000-$25,000 agency brand packages. Paste into Claude at client onboarding — produces: Brand DNA, archetypes, customer personas, competitive semiotic audit, verbal identity, 50 design styles, color palette (with HEX/RGB/CMYK/Pantone), typography system, logo specs + NBP prompts, design system, sonic identity brief, GEO entity-building, brand guidelines, and 16-folder file delivery manifest. Run across multiple conversation turns with phase-by-phase approval.",
      },
      {
        name: "Gemini 3.1 Pro",
        role: "Second brain — cross-checks, GEO testing, data synthesis & Google ecosystem engine",
        tasks: [
          "GEO testing: what does Google's AI say about client? (direct service delivery)",
          "NotebookLM: upload client docs → persistent AI research library per client",
          "Second opinion on strategy for high-stakes deliverables",
          "Long document analysis (1M token context — entire websites, reports, data)",
          "Complex data synthesis (spreadsheets, analytics, multi-source research)",
          "Powers Google Antigravity when building landing pages & tools",
          "Powers Google Flow for creative asset management",
          "Client competitor analysis cross-check against Claude findings",
        ],
        cost: "Free (via your Google AI Pro access)",
        priority: "CORE",
        stable: true,
        note: "Not a replacement for Claude — a complement. Claude creates, Gemini cross-checks and powers Google tools. Use NotebookLM to build persistent client knowledge bases.",
      },
      {
        name: "Perplexity Deep Research",
        role: "Research scout — gathers intelligence before production begins",
        tasks: [
          "Competitor deep-dive analysis",
          "Industry/market research for new clients",
          "Content gap identification",
          "Trend monitoring & emerging opportunities",
          "Proposal preparation intelligence",
          "SEO/AEO/GEO audit research",
        ],
        cost: "Free (limited queries/day)",
        priority: "CORE",
        stable: true,
        note: "Use strategically — limited free queries. Save for high-value research.",
      },
      {
        name: "NotebookLM (Gemini 3.1 Pro)",
        role: "Client knowledge base — persistent AI research library per client",
        tasks: [
          "Upload all client materials (website content, brand docs, past campaigns)",
          "Chat with client documents to find insights quickly",
          "Cross-reference client goals against their existing content",
          "Prepare for client calls with instant context recall",
          "Generate audio summaries of client briefs",
        ],
        cost: "Free (included with Google AI Pro)",
        priority: "SUPPORT",
        stable: true,
        note: "Create one NotebookLM notebook per client. Upload everything they give you. Instant context for every conversation about that client.",
      },
    ],
  },
  visual: {
    label: "VISUAL",
    icon: "🎨",
    subtitle: "Image Generation & Design",
    color: "#4ECDC4",
    bgColor: "#1A2A28",
    tools: [
      {
        name: "Nanobanana Pro (Google AI Pro)",
        role: "Primary image generation — your visual workhorse (powered by Imagen 4)",
        tasks: [
          "Social media images",
          "Ad creatives",
          "Brand imagery & mood boards (backup for Mixboard)",
          "Product photography style images",
          "Reference frames for video generation",
          "Landing page hero images",
          "Up to 14 reference images for consistency across brand assets",
          "Image remixing with references (Whisk merged into Flow)",
          "Up to 2K resolution output",
          "🔥 BRAND DESIGN: 7-step logo workflow (concept → iterate → variations → grid → misuse → vectorize → export)",
          "🔥 BRAND DESIGN: 13-asset prompt library (logomark, wordmark, lockup, stacked, social headers, product shots, lifestyle, hero images, patterns, textures, icons, team photos, mood boards)",
          "SynthID watermarked (invisible — AI-generated marker)",
        ],
        cost: "Free (~100/day at 2K via Google AI Pro)",
        priority: "CORE",
        stable: true,
        note: "Powered by Imagen 4 (released Feb 2026). #1 ranked image gen 2026. Brand Design Master Prompt includes ready-to-paste NBP prompts for all 13 brand asset types + 4 logo prompt sets (logomark, wordmark, combined lockup, stacked). Use 14-reference-image feature to maintain character/style consistency across entire brand kit.",
      },
      {
        name: "Nanobanana 2 (Gemini App)",
        role: "Fast iterations & web-grounded generation",
        tasks: [
          "Quick image variations",
          "Real-time web search grounded images",
          "Rapid client revision cycles",
        ],
        cost: "Free (via Google AI Pro — 50 daily AI credits shared)",
        priority: "SUPPORT",
        stable: true,
      },
      {
        name: "Ideogram",
        role: "Text-in-image specialist — when you need readable text",
        tasks: [
          "Logo concepts with readable text (~90% accuracy)",
          "Posters with headlines",
          "Infographic designs",
          "Social graphics with text overlays",
          "Business cards",
          "Style References (up to 3 images) + Style Codes for brand consistency",
        ],
        cost: "Free (25 prompts/day slow queue, public)",
        priority: "SPECIALIST",
        stable: true,
        note: "Ideogram 3.0 (March 2025). ~90% text accuracy — best-in-class. Paid from $7/mo for private + priority. Use ONLY when images need readable text.",
      },
      {
        name: "Canva Free → Pro",
        role: "Design formatting, templates & platform sizing",
        tasks: [
          "Format images for each platform's dimensions",
          "Text overlays on AI-generated images",
          "Social media post templates (reusable)",
          "Presentation design for client pitches",
          "Brand kit storage (Pro only)",
        ],
        cost: "Free → $15/mo Pro from $50 budget when needed",
        priority: "SUPPORT",
        stable: true,
      },
      {
        name: "Kittl",
        role: "Typography/vector specialist — logos, branding, print design",
        tasks: [
          "Logo design with AI vector generator",
          "Typography-heavy designs (posters, merch, signage)",
          "Creative Flows pipelines for batch design",
          "Print-ready outputs (business cards, packaging)",
        ],
        cost: "Free tier + paid for premium ($10/mo)",
        priority: "SPECIALIST",
        stable: true,
        note: "Integrates Nano Banana + Seedream 3 + Imagen 4 internally. Stronger than Ideogram for layout-driven typography. Use for client branding deliverables.",
      },
      {
        name: "Recraft",
        role: "Native vector graphics (SVG) — infinite-scaling logos",
        tasks: [
          "True vector SVG output (unique in AI image gen)",
          "Logo creation that scales to any size without quality loss",
          "Icon sets and brand assets",
          "Style-consistent image series",
        ],
        cost: "Free tier",
        priority: "SPECIALIST",
        stable: true,
        note: "Only major AI tool producing native vector graphics. Critical for logos that need infinite scaling (billboards, print). Use alongside Ideogram for text + Kittl for layout.",
      },
      {
        name: "Brand Design Utilities (free web tools)",
        role: "Color, typography, logo, photography, mockup & sonic tools for brand execution",
        tasks: [
          "Coolors.co — generate, lock, export color palettes (PNG/ASE/CSS/JSON)",
          "Realtime Colors — see palette on real website layout instantly",
          "Colour Contrast Checker — WCAG 2.2 AA verification for accessibility",
          "Fontjoy — AI font pairing suggestions",
          "Google Fonts + Fontshare — free commercial-use font sourcing",
          "Vectorizer.ai — convert NBP raster logos to true vector (SVG/PDF)",
          "Huemint — AI palette visualization on brand mockups",
          "Unsplash + Pexels — free commercial-use stock photography (curate 20+ images per client brand library)",
          "Smartmockups — free professional device/product mockups (laptop, phone, business card, storefront, merch). Master prompt Phase 7.11 has step-by-step walkthrough",
          "Suno AI — free AI music generation from text prompts (sonic identity starting points from Phase 6 brief). AI audio = starting point, have human refine for final",
        ],
        cost: "All FREE (browser-based, no accounts needed for most)",
        priority: "SUPPORT",
        stable: true,
        note: "Used during Brand Design workflow Phases 4-7. ESSENTIAL: Coolors + Contrast Checker (color), Unsplash/Pexels (photography library), Smartmockups (15+ mockups per brand project), Vectorizer.ai (NBP logo → print vector). Suno AI handles Phase 6 sonic brief execution — generates music beds from the sonic identity description Claude produces.",
      },
    ],
  },
  video: {
    label: "VIDEO",
    icon: "🎬",
    subtitle: "AI Video Generation & Editing",
    color: "#FF6B6B",
    bgColor: "#2A1A1A",
    tools: [
      {
        name: "Kling 3.0 / Omni (Higgsfield Pro)",
        role: "Primary video generation + AI avatars + native voiceover + 4K",
        tasks: [
          "Cinematic ad videos (up to 15s per gen, custom duration)",
          "Character-consistent multi-shot (up to 6 cuts via vCoT storyboard)",
          "Product demos from single image (Click-to-Ad)",
          "Social media video ads",
          "Native lip-sync & dialogue (EN, ZH, JA, KO, ES + regional accents incl. Indian English)",
          "Native 4K 60fps output (new in 3.0)",
          "Visual Chain-of-Thought (vCoT) — AI auto-directs multi-shot sequences",
          "Elements 3.0 for character consistency (image + video reference locking)",
          "AI Avatar / Talking Head videos (single photo + audio → lifelike spokesperson, up to 1 min, 1080p 48fps)",
          "Native voiceover generation (accent, tone, pacing, emotion control)",
          "In-model video editing (trim, extend, refine without re-generating)",
          "LipSync Studio for existing video dubbing",
        ],
        cost: "$29/mo (Higgsfield Pro — 600 credits, credit-based system)",
        priority: "CORE",
        stable: true,
        note: "Kling 3.0 launched Feb 5, 2026. CREDIT WARNING: 600 credits/mo on Pro plan — a single advanced gen can use 40-70 credits. Budget carefully per client. Higgsfield also includes Sora 2, WAN 2.5, Veo 3.1, Seedream 4.0, and Nano Banana Pro access.",
      },
      {
        name: "Veo 3.1 (Google Flow / Gemini App)",
        role: "Image-to-video + best-in-class native audio + 4K upscaling",
        tasks: [
          "Turn Nanobanana Pro images into video",
          "Frames-to-video sequences (start + end frame control)",
          "Multi-reference mode (up to 3 reference images for character/style consistency)",
          "Best native audio quality of any AI video model — 3-layer audio (dialogue, SFX, ambient)",
          "Natural lip-sync (<120ms accuracy) + lifelike body language + full sound design",
          "Scene extension — chain 7s segments for 2+ minute videos",
          "Vertical video (9:16) for social — upload vertical image to generate",
          "4K upscaling via Flow/API (native gen at 1080p)",
          "Max 8 seconds per generation (base)",
        ],
        cost: "Free (1000 credits/mo via Google AI Pro) + also available on Higgsfield Pro",
        priority: "CORE",
        stable: true,
        note: "Best audio in your stack. Route audio-critical video through Veo 3.1. Jan 2026 update added reference images + vertical video. You have Veo 3.1 from TWO sources: Google Flow (free) and Higgsfield Pro (paid). 1000 Google credits shared across video features — track weekly.",
      },
      {
        name: "Sora 2 (Higgsfield)",
        role: "Long-form narrative video",
        tasks: [
          "Longest single generation (25 seconds)",
          "Story-driven brand narratives",
          "Extended sequences",
        ],
        cost: "Included in Higgsfield Pro",
        priority: "SPECIALIST",
        stable: true,
      },
      {
        name: "CapCut",
        role: "Video editing & final assembly",
        tasks: [
          "Arrange AI-generated clips into final video",
          "Auto-captions & subtitles",
          "Music & sound effects library",
          "Platform-specific export",
          "Transitions & effects",
        ],
        cost: "Free",
        priority: "CORE",
        stable: true,
      },
      {
        name: "ElevenLabs (free tier)",
        role: "Standalone AI voice & audio — edge cases where video native audio isn't enough",
        tasks: [
          "Standalone voiceovers for non-video content (podcast intros, audio ads, IVR)",
          "Voice cloning for consistent brand voice across deliverables",
          "Multilingual voice generation (29+ languages incl. Hindi)",
          "Audio for email marketing campaigns and website explainers",
        ],
        cost: "Free (10,000 chars/month — ~10 min audio)",
        priority: "SPECIALIST",
        stable: true,
        note: "Use ONLY when Kling/Veo native audio won't work (standalone audio without video). 10K chars/mo free is enough for 2-3 short voiceovers. For BRAND DESIGN sonic identity: ElevenLabs handles voice/notification sounds, Suno AI (in Brand Design Utilities) handles music beds. Both execute Phase 6 sonic brief that Claude produces.",
      },
    ],
  },
  build: {
    label: "BUILD",
    icon: "🏗️",
    subtitle: "Landing Pages, Web Tools & Production Hubs",
    color: "#A78BFA",
    bgColor: "#1E1A2A",
    tools: [
      {
        name: "Google Antigravity (powered by Gemini 3.1 Pro)",
        role: "Agentic development platform — websites, landing pages, apps & tools (desktop app, requires install)",
        tasks: [
          "Landing pages from plain English description (agent builds autonomously)",
          "Interactive tools (calculators, quizzes, assessments)",
          "Client websites and full web applications",
          "Built-in Nanobanana image generation for visual assets",
          "Supports Claude Opus 4.6 + Gemini 3.1 Pro as AI models",
          "Planning Mode for safe, reviewed builds",
          "Browser sub-agent for automated QA testing",
          "Agent Manager for parallel task execution",
          "Stitch MCP integration for design-to-code pipeline",
        ],
        cost: "Free (public preview — download at antigravity.google)",
        priority: "CORE",
        stable: false,
        note: "NOT a web tool — must be downloaded and installed (Mac/Win/Linux). Agent-first IDE, not a simple page builder. More powerful than described in v3.2 but requires moderate tech comfort. Use Planning Mode to review agent work before execution.",
      },
      {
        name: "Google Flow (powered by Gemini 3.1 Pro)",
        role: "Unified creative workspace — image → video pipeline",
        tasks: [
          "Nanobanana Pro image generation",
          "Tag images with @ → feed into Veo 3.1",
          "Frames-to-video pipeline",
          "Smart asset grid for organized projects",
          "Collections for multi-scene storytelling",
          "Whisk remixing (merged into Flow March 2026)",
          "Lasso editing for video refinement",
        ],
        cost: "Free (via Google AI Pro)",
        priority: "CORE",
        stable: true,
        note: "Gemini 3.1 Pro handles prompt interpretation and asset management. Your primary creative studio.",
      },
      {
        name: "Higgsfield Platform",
        role: "Multi-model video hub & Cinema Studio",
        tasks: [
          "Access Kling 3.0, Sora 2, WAN 2.5, Veo 3.1, Seedream 4.0, Nano Banana Pro",
          "Cinema Studio — real optical physics",
          "50+ camera presets",
          "Click-to-Ad from product URL",
          "Character Elements 3.0 for consistency (image + video reference)",
          "LipSync Studio",
          "Motion Control 3.0 (March 2026)",
        ],
        cost: "Included in Higgsfield Pro ($29/mo)",
        priority: "CORE",
        stable: true,
        note: "15+ AI models under one subscription. CHINESE MODELS ALREADY INCLUDED: Kling 3.0 + Kling 2.6 (Kuaishou), WAN 2.5 (Alibaba), Seedream 4.0 (ByteDance). You're already deeply using Chinese AI — no need for separate Chinese model subscriptions. Credit-based system — track usage carefully. Commercial use rights included.",
      },
    ],
  },
  labs: {
    label: "SPEED BOOSTERS",
    icon: "⚡",
    subtitle: "Google Labs — Use but NEVER depend on",
    color: "#F59E0B",
    bgColor: "#2A2410",
    tools: [
      {
        name: "Pomelli",
        role: "Auto brand DNA + on-brand content generation + Photoshoot + Animate",
        tasks: [
          "Scans website → extracts brand identity (Business DNA)",
          "Generates on-brand social campaigns",
          "Photoshoot: product photo → studio quality via Nano Banana (Feb 2026)",
          "Animate: static → video via Veo 3.1 (Jan 2026)",
          "Natural language editing of generated content",
        ],
        cost: "Free (beta — 300 image gens/month cap)",
        priority: "BOOSTER",
        stable: false,
        note: "✅ NOW GLOBAL: Expanded to 170+ countries (March 2026). India access confirmed. Previously US/CA/AU/NZ only. Still experimental — backup (BETTER): Claude Brand Continuity Sheet + Nanobanana Pro.",
      },
      {
        name: "Stitch",
        role: "AI-native UI design canvas — mockups, prototypes, React export",
        tasks: [
          "UI designs from text prompts or uploaded sketches",
          "Export to Figma or HTML/CSS",
          "React app export from selected screens (new March 2026)",
          "Visual prototyping for client pitches",
          "Design system extraction from any URL",
          "MCP server for Antigravity pipeline (Stitch → Antigravity)",
          "Agent Manager for parallel design exploration",
        ],
        cost: "Free (350 gens/mo standard, 50/mo experimental)",
        priority: "BOOSTER",
        stable: false,
        note: "Major redesign March 2026: 3D canvas, voice agent, React export, MCP integration. Stitch → Antigravity pipeline is now one of the most powerful no-code combos available. Backup still BETTER: Claude Artifacts + Antigravity.",
      },
      {
        name: "Mixboard",
        role: "AI mood board for visual exploration",
        tasks: [
          "Drop images → suggested textures, colors",
          "Visual direction exploration",
          "Brand refresh concepts",
        ],
        cost: "Free (experimental)",
        priority: "BOOSTER",
        stable: false,
        note: "Backup (EQUAL): Nanobanana Pro + Canva layout.",
      },
      {
        name: "Opal",
        role: "AI mini-app builder",
        tasks: [
          "Calculators & quizzes from description",
          "Quick lead magnet tools",
          "Simple interactive widgets",
        ],
        cost: "Free (experimental)",
        priority: "BOOSTER",
        stable: false,
        note: "Backup (BETTER): Claude Artifacts + Antigravity.",
      },
    ],
  },
  automate: {
    label: "AUTOMATE",
    icon: "⚙️",
    subtitle: "Social Scheduling, CRM, Email & Workflows",
    color: "#F97316",
    bgColor: "#2A2018",
    tools: [
      {
        name: "Metricool",
        role: "Social media scheduling + competitor analytics + link-in-bio",
        tasks: [
          "Schedule & publish posts across Instagram, LinkedIn, Facebook, X, TikTok, YouTube",
          "Competitor social analytics (compare up to 5 competitors on free tier)",
          "Content calendar with drag-and-drop planning",
          "Link-in-bio tool for Instagram",
          "Website + social analytics in one dashboard (connects GA4)",
          "Ad performance tracking (Google, Meta, TikTok ads)",
        ],
        cost: "Free (1 brand, 20 posts/mo, 5 competitors) → $25/mo Starter (10 brands)",
        priority: "CORE",
        stable: true,
        note: "CRITICAL for Service #1 (Social Media). Free tier handles your own agency launch. Starter at $25/mo scales to 10 clients. Chosen over Buffer because free tier includes competitor analytics (directly serves Service #12 Competitor Research) and scales better for agency use.",
      },
      {
        name: "Gumloop",
        role: "Beginner automation builder",
        tasks: ["AI-connected workflows", "Lead notifications", "Content distribution"],
        cost: "Free tier",
        priority: "LATER",
        stable: true,
        note: "Phase 4+ tool.",
      },
      {
        name: "HubSpot CRM",
        role: "Client & lead tracking",
        tasks: ["Track interactions", "Lead capture", "Pipeline management", "Contact database"],
        cost: "Free",
        priority: "SUPPORT",
        stable: true,
      },
      {
        name: "Mailchimp / Beehiiv",
        role: "Email marketing delivery",
        tasks: ["Client email sequences", "Your newsletter", "Automated emails"],
        cost: "Free tiers",
        priority: "SUPPORT",
        stable: true,
      },
    ],
  },
  measure: {
    label: "MEASURE",
    icon: "📊",
    subtitle: "SEO Research, Analytics, Tracking & Reporting",
    color: "#22D3EE",
    bgColor: "#1A2428",
    tools: [
      {
        name: "Ubersuggest",
        role: "SEO keyword research, backlink analysis & site audits — your #1 differentiator needs a dedicated tool",
        tasks: [
          "Keyword research (volume, difficulty, CPC) for client industries",
          "Competitor backlink analysis",
          "Site audit (technical SEO issues, page speed, crawl errors)",
          "Rank tracking for client keywords",
          "Content ideas based on top-performing pages in client's niche",
        ],
        cost: "Free (3 searches/day) → $29/mo Individual when first SEO client signs",
        priority: "CORE",
        stable: true,
        note: "CRITICAL for Services #3 (SEO), #4 (AEO), #5 (GEO). Triple-Threat Visibility is your #1 differentiator — Search Console only tracks YOUR site, not competitors. Free 3 searches/day + Perplexity covers Phase 0B. Upgrade to $29/mo at first SEO client (Wave 2, Month 2-3). Chosen over Semrush ($139/mo) and Ahrefs ($129/mo) for budget.",
      },
      {
        name: "Google Analytics 4",
        role: "Website traffic & behavior tracking",
        tasks: ["Visitor behavior", "Conversions", "Traffic sources", "UTM tracking"],
        cost: "Free",
        priority: "CORE",
        stable: true,
      },
      {
        name: "Google Search Console",
        role: "SEO & AI Overview tracking",
        tasks: ["Search rankings", "AI Overview appearances", "Technical SEO issues", "CTR tracking"],
        cost: "Free",
        priority: "CORE",
        stable: true,
      },
      {
        name: "Looker Studio",
        role: "Visual dashboard builder",
        tasks: ["Client dashboards", "Multi-source data", "Monthly report templates"],
        cost: "Free",
        priority: "SUPPORT",
        stable: true,
      },
      {
        name: "Google Trends",
        role: "Search trend research & content planning",
        tasks: ["Identify trending topics in client's industry", "Compare search interest between keywords", "Seasonal trend analysis for campaign timing", "Validate content topics before writing"],
        cost: "Free",
        priority: "SUPPORT",
        stable: true,
      },
      {
        name: "Grok (X/Twitter — free tier)",
        role: "Real-time X social listening + GEO testing platform",
        tasks: [
          "Real-time brand sentiment monitoring on X (reputation management)",
          "Trending topic detection for social content timing",
          "Competitor mention tracking on X",
          "GEO testing: what does X's AI recommend about client's industry?",
          "DeepSearch for X + web combined research",
        ],
        cost: "Free (10 messages per 2-hour window)",
        priority: "SPECIALIST",
        stable: true,
        note: "Narrow specialist — only for X/Twitter social listening and GEO testing. NOT for copywriting, strategy, or production. Free tier is limited but sufficient for periodic checks. Never use Grok output directly for clients without heavy editing.",
      },
      {
        name: "Google Alerts",
        role: "Free brand mention monitoring — reputation management foundation",
        tasks: [
          "Track brand mentions across the web (client name, competitor names)",
          "Monitor industry keywords for content opportunities",
          "Early warning system for negative press or reviews",
          "Set up on Day 1 for your own agency name",
        ],
        cost: "Free (no limits)",
        priority: "SUPPORT",
        stable: true,
        note: "Zero setup cost, zero learning curve. Covers the 'monitor' part of Service #13 (Reputation Mgmt). Set up alerts for your agency name immediately. Add client brand alerts at onboarding. For advanced monitoring (social + review sites), add Mention.com ($29/mo) or Brand24 ($79/mo) when a client pays for Service #13.",
      },
    ],
  },
};

const WORKFLOWS = [
  {
    name: "New Client Onboarding",
    steps: [
      { tool: "NotebookLM", action: "Create client notebook → upload all their materials (website content, brand docs, past campaigns)", gemini: true },
      { tool: "Perplexity", action: "Deep research: industry, competitors, market landscape" },
      { tool: "Gemini 3.1 Pro", action: "Cross-check competitor findings + analyze large client data sets", gemini: true },
      { tool: "Claude", action: "Build Brand Continuity Sheet + full client strategy document" },
      { tool: "Claude Skills", action: "Generate proposal as .docx/.pdf deliverable" },
    ],
    time: "3-5 hours",
    gate: "Gate 2 + 3 (add Gate 4 if proposal >$1K)",
  },
  {
    name: "Social Media Content (Monthly)",
    steps: [
      { tool: "NotebookLM", action: "Review client notebook for brand voice + recent updates", gemini: true },
      { tool: "Claude", action: "Content calendar + all captions + image prompts" },
      { tool: "Nanobanana Pro", action: "Generate all images (batch)" },
      { tool: "Canva", action: "Format for each platform + text overlays" },
      { tool: "Metricool", action: "Schedule all posts across platforms + set optimal posting times" },
    ],
    time: "4-6 hours for 16-20 posts",
    gate: "All 3 Gates",
  },
  {
    name: "Video Ad Campaign",
    steps: [
      { tool: "Claude", action: "Script + storyboard + 5-layer video prompts" },
      { tool: "Nanobanana Pro", action: "Character references + scene frames" },
      { tool: "Flow", action: "Tag images → Veo 3.1 for atmospheric clips", gemini: true },
      { tool: "Kling 3.0 (Higgsfield)", action: "Multi-shot scenes with dialogue + character Elements" },
      { tool: "CapCut", action: "Assemble, captions, music, export per platform" },
    ],
    time: "3-5 hours per video",
    gate: "All 3 Gates",
  },
  {
    name: "Landing Page Build",
    steps: [
      { tool: "Claude", action: "Full page copy + design specification + conversion strategy" },
      { tool: "Stitch (optional)", action: "Quick visual mockup for client approval before building" },
      { tool: "Antigravity (Gemini 3.1 Pro)", action: "Build full functional page from spec", gemini: true },
      { tool: "Nanobanana Pro", action: "Hero images (or via Antigravity built-in)" },
      { tool: "GA4", action: "Add tracking pixel + conversion goals" },
    ],
    time: "3-5 hours per page",
    gate: "All 3 Gates",
  },
  {
    name: "SEO / AEO / GEO Audit",
    steps: [
      { tool: "Ubersuggest", action: "Keyword research + competitor backlink analysis + site audit for technical SEO issues" },
      { tool: "Perplexity", action: "Deep research: competitor rankings, content landscape" },
      { tool: "Gemini 3.1 Pro", action: "GEO TEST: Ask Gemini questions about client's industry — record what Google's AI recommends", gemini: true },
      { tool: "ChatGPT", action: "GEO TEST: Ask same questions — record what OpenAI's AI recommends" },
      { tool: "Claude", action: "GEO TEST: Ask same questions — record what Anthropic's AI recommends + Full audit analysis" },
      { tool: "Perplexity", action: "GEO TEST: Ask same questions — record what Perplexity recommends" },
      { tool: "Grok (X)", action: "GEO TEST: Ask same questions — record what X's AI recommends + check X sentiment about client" },
      { tool: "DeepSeek (optional)", action: "GEO TEST: 6th platform — what does Chinese AI recommend? ⚠️ Never feed client data — use only generic industry queries" },
      { tool: "Search Console", action: "Pull current ranking data + AI Overview appearance data" },
      { tool: "Claude Skills", action: "Generate professional audit report (.pdf) with all platform results" },
    ],
    time: "5-7 hours per audit",
    gate: "Gate 2 + 3 + 4",
  },
  {
    name: "Brand & Visual Design (13-Phase Master System)",
    steps: [
      { tool: "Perplexity", action: "Deep research: competitor visual identity, industry trends, semiotic landscape" },
      { tool: "NotebookLM", action: "Upload ALL client materials → build persistent brand context library", gemini: true },
      { tool: "Claude (Brand Master Prompt)", action: "Phase 1-2: Brand DNA (mission, archetypes, personas, SWOT, storytelling) + Verbal Identity (voice, tone, messaging hierarchy, tagline)" },
      { tool: "Gemini 3.1 Pro", action: "Second opinion: review brand strategy + archetype selection for blind spots", gemini: true },
      { tool: "Claude (Brand Master Prompt)", action: "Phase 3-4: Creative Direction (2-3 directions from 50 styles) + Visual Identity (color palette HEX/RGB/CMYK/Pantone, typography system, logo specs, imagery style)" },
      { tool: "Coolors + Contrast Checker", action: "Visualize palette → verify ALL text/bg combos pass WCAG 2.2 AA (4.5:1 normal, 3:1 large)" },
      { tool: "Nanobanana Pro", action: "Logo concept generation (7-step workflow) + 13-asset brand kit (A-M prompt library) using 14-reference-image consistency" },
      { tool: "Ideogram", action: "Logo versions needing readable text (wordmarks, tagline lockups)" },
      { tool: "Kittl", action: "Typography-driven logo refinement + print-ready brand assets (business cards, signage)" },
      { tool: "Recraft + Vectorizer.ai", action: "Final logo as native SVG vector — infinite scaling. Vectorize any NBP raster logos" },
      { tool: "Unsplash + Pexels", action: "Curate 20+ stock images for brand photography library (lifestyle, product, people, textures, backgrounds). Apply color grading preset in Canva for consistency" },
      { tool: "Smartmockups + Canva", action: "Generate 15+ professional mockups: device frames (laptop, phone, tablet), stationery (cards, letterhead), environmental (storefront, signage), merch (tote, mug)" },
      { tool: "Canva", action: "Brand guidelines document + social templates + stationery templates + presentation deck" },
      { tool: "Claude (Brand Master Prompt)", action: "Phase 5-9: Design system tokens + Sonic identity brief + GEO entity-building (schema markup, AI-optimized descriptions) + Brand guidelines compilation" },
      { tool: "Suno AI + ElevenLabs", action: "Sonic execution: Suno AI generates music beds from Phase 6 brief. ElevenLabs generates voice assets. AI audio = starting points for human refinement" },
      { tool: "Claude (Brand Master Prompt)", action: "Phase 10-12: Launch strategy + 16-folder file manifest + QA self-review (22 sections, 85+ audit items). Final verdict: PASS/CONDITIONAL/FAIL" },
      { tool: "Claude Skills", action: "Export: Brand Guidelines .pdf + Brand DNA One-Pager .pdf + Color Reference Card .pdf + Typography Specimen .pdf + README.pdf" },
    ],
    time: "10-20 hours per full brand project (across multiple sessions — use bridging message for conversation continuity)",
    gate: "All 4 Gates (Gate 4 mandatory — run every phase through Gemini for cross-check)",
  },
  {
    name: "Website Copywriting",
    steps: [
      { tool: "NotebookLM", action: "Upload client's existing site content + competitor sites for context", gemini: true },
      { tool: "Perplexity", action: "Research target keywords + questions audience asks" },
      { tool: "Claude", action: "Write full website copy: homepage, about, services, FAQ — SEO + AEO optimized" },
      { tool: "Google Trends", action: "Validate keyword choices against current search trends" },
      { tool: "Claude", action: "Add schema markup recommendations + meta descriptions for each page" },
      { tool: "Claude Skills", action: "Deliver as .docx with page-by-page structure" },
    ],
    time: "4-8 hours per website (5-15 pages)",
    gate: "All 3 Gates",
  },
  {
    name: "Local Marketing Setup",
    steps: [
      { tool: "Claude", action: "Audit client's current Google Business Profile + local directory presence" },
      { tool: "Perplexity", action: "Research local competitors + local search landscape" },
      { tool: "Gemini 3.1 Pro", action: "GEO TEST: what does Google's AI recommend for '[service] in [city]'?", gemini: true },
      { tool: "Claude", action: "Optimize Google Business Profile description + categories + posts" },
      { tool: "Claude", action: "Write local SEO content targeting '[service] near me' + '[service] in [city]' queries" },
      { tool: "Nanobanana Pro", action: "Generate Google Business Profile photos (storefront, team, products)" },
      { tool: "Claude Skills", action: "Local marketing report + directory submission checklist as .pdf" },
    ],
    time: "3-5 hours per client setup",
    gate: "Gate 2 + 3",
  },
];

const QC_GATES = [
  { gate: "Gate 1", name: "PRODUCTION", question: "Does it technically work?", color: "#4ECDC4", checks: "Read-aloud test • Full-size visual inspection • Full video playthrough • Click every element • Send test email • SEO checklist" },
  { gate: "Gate 2", name: "STRATEGY", question: "Does it serve the client's goal?", color: "#E8B931", checks: "Brief alignment • Audience fit • Platform fit • CTA clarity • Differentiation • GEO citation-worthiness" },
  { gate: "Gate 3", name: "CLIENT-READY", question: "Is it professional enough to charge for?", color: "#A78BFA", checks: "Brand consistency • Zero errors • Correct formats • Organized delivery • Portfolio-worthy" },
  { gate: "Gate 4", name: "SECOND OPINION", question: "Does another AI agree? (High-stakes only)", color: "#F59E0B", checks: "Run strategy through Gemini 3.1 Pro • Compare with Claude's analysis • Flag disagreements • Investigate conflicts • Use for: proposals >$1K, GEO audits, brand strategies" },
];

const BUDGET = {
  paid: [
    { item: "Claude Pro", cost: "$20/mo", note: "Primary brain — all production flows through here", color: "#E8B931" },
    { item: "Higgsfield Pro", cost: "$29/mo", note: "Kling 3.0, Sora 2, Veo 3.1, Cinema Studio — 600 credits/mo (budget carefully)", color: "#FF6B6B" },
  ],
  free: [
    { item: "Google AI Pro (Gemini 3.1 Pro + tools)", cost: "FREE*", note: "*User has free access. ~100 NBP/day, 1000 Veo credits, Flow, NB2, NotebookLM. Retail $19.99/mo" },
    { item: "Google Antigravity (desktop IDE)", cost: "FREE", note: "Landing pages & web apps. Must download — not browser-based" },
    { item: "Google Labs (Stitch✅, Pomelli✅, Mixboard, Opal)", cost: "FREE", note: "Both Stitch + Pomelli upgraded March 2026" },
    { item: "Ideogram", cost: "FREE", note: "25 prompts/day for text-in-image" },
    { item: "Kittl + Recraft + Brand Utilities (10 tools)", cost: "FREE", note: "Coolors, Fontjoy, Vectorizer.ai, Unsplash, Pexels, Smartmockups, Suno AI + more" },
    { item: "Canva Free", cost: "FREE", note: "Design formatting and templates" },
    { item: "CapCut", cost: "FREE", note: "Video editing and assembly" },
    { item: "Perplexity Deep Research", cost: "FREE", note: "Research with daily limits" },
    { item: "HubSpot + Mailchimp/Beehiiv", cost: "FREE", note: "CRM + email marketing" },
    { item: "GA4 + Search Console + Looker", cost: "FREE", note: "Full analytics and reporting" },
    { item: "Ubersuggest (3 searches/day)", cost: "FREE", note: "SEO keyword research + competitor backlinks + site audits" },
    { item: "Google Trends + Google Alerts", cost: "FREE", note: "Search trends + brand mention monitoring" },
    { item: "Metricool (1 brand, 20 posts/mo)", cost: "FREE", note: "Social scheduling + competitor analytics + link-in-bio" },
    { item: "Grok (X/Twitter)", cost: "FREE", note: "Real-time X social listening + GEO testing (10 msg/2hr)" },
    { item: "ElevenLabs (10K chars/mo)", cost: "FREE", note: "Standalone AI voice for non-video audio needs" },
  ],
  remaining: "$50/mo",
  remainingUses: "Domain, Canva Pro upgrade, ad testing, emergency tool needs",
  upgradeTriggers: [
    { trigger: "First paying client", action: "Consider Canva Pro ($15/mo)", reason: "Brand kits, background remover, resize — saves time per client" },
    { trigger: "First SEO client (Wave 2)", action: "Ubersuggest Individual ($29/mo)", reason: "Unlimited keyword research, site audits, backlink data — essential for Services #3-5" },
    { trigger: "3+ social media clients", action: "Metricool Starter ($25/mo)", reason: "Manage 10 brands, unlimited posts, 100 competitors — scales your Service #1" },
    { trigger: "$1,000/mo revenue", action: "Consider Perplexity Pro ($20/mo)", reason: "Unlimited deep research for multiple client audits" },
    { trigger: "$2,500/mo revenue", action: "Consider additional Higgsfield credits", reason: "More video generations for active video clients" },
    { trigger: "$5,000/mo revenue", action: "Consider Make.com ($9/mo) + GEO tracking tool", reason: "Automation workflows + measure AI visibility properly" },
  ],
};

function PriorityBadge({ priority }) {
  const s = { CORE: { bg: "#16a34a", t: "#fff" }, SUPPORT: { bg: "#475569", t: "#e2e8f0" }, SPECIALIST: { bg: "#7c3aed", t: "#fff" }, LATER: { bg: "#92400e", t: "#fde68a" }, BOOSTER: { bg: "#d97706", t: "#fff" } }[priority] || { bg: "#475569", t: "#e2e8f0" };
  return <span style={{ fontSize: "9px", fontWeight: 700, letterSpacing: "0.08em", padding: "2px 8px", borderRadius: "3px", backgroundColor: s.bg, color: s.t, textTransform: "uppercase", fontFamily: "monospace" }}>{priority}</span>;
}

function StabilityBadge({ stable }) {
  return <span style={{ fontSize: "9px", fontWeight: 700, padding: "2px 6px", borderRadius: "3px", backgroundColor: stable ? "#065f4620" : "#7c2d1220", color: stable ? "#10b981" : "#ef4444", border: `1px solid ${stable ? "#10b98130" : "#ef444430"}`, fontFamily: "monospace" }}>{stable ? "STABLE" : "EXPERIMENTAL"}</span>;
}

export default function Ecosystem() {
  const [activeLayer, setActiveLayer] = useState("brain");
  const [activeView, setActiveView] = useState("ecosystem");
  const [expandedTool, setExpandedTool] = useState(null);
  const layer = LAYERS[activeLayer];

  return (
    <div style={{ minHeight: "100vh", backgroundColor: "#0F0F0F", color: "#E8E6E1", fontFamily: "'Inter', -apple-system, sans-serif" }}>
      {/* Header */}
      <div style={{ padding: "24px 20px 16px", borderBottom: "1px solid #222" }}>
        <div style={{ fontSize: "9px", letterSpacing: "0.2em", color: "#666", fontWeight: 600, textTransform: "uppercase", fontFamily: "monospace" }}>
          Vibe Marketing Agency • Updated March 28, 2026
        </div>
        <h1 style={{ fontSize: "24px", fontWeight: 800, margin: "4px 0 0", letterSpacing: "-0.03em" }}>
          Tool Ecosystem v4.1
        </h1>
        <p style={{ color: "#777", fontSize: "12px", marginTop: "4px", marginBottom: "12px", lineHeight: 1.4 }}>
          34 tools • Brand Design Master System integrated • Metricool + Ubersuggest + ElevenLabs added • 4-gate QC • 8 workflows
        </p>
        <div style={{ display: "flex", gap: "3px", flexWrap: "wrap" }}>
          {[
            { id: "ecosystem", label: "Tools" },
            { id: "workflows", label: "Workflows" },
            { id: "budget", label: "Budget" },
            { id: "qc", label: "QC System" },
            { id: "backups", label: "Backups" },
            { id: "gemini", label: "🔵 Gemini Map" },
          ].map(v => (
            <button key={v.id} onClick={() => setActiveView(v.id)} style={{
              padding: "7px 12px", fontSize: "11px", fontWeight: 600, border: "none", borderRadius: "5px", cursor: "pointer",
              backgroundColor: activeView === v.id ? "#E8E6E1" : "transparent",
              color: activeView === v.id ? "#0F0F0F" : "#888",
            }}>{v.label}</button>
          ))}
        </div>
      </div>

      {/* ECOSYSTEM VIEW */}
      {activeView === "ecosystem" && (
        <div>
          <div style={{ display: "flex", overflowX: "auto", padding: "10px 20px", gap: "4px", borderBottom: "1px solid #1a1a1a" }}>
            {Object.entries(LAYERS).map(([key, l]) => (
              <button key={key} onClick={() => { setActiveLayer(key); setExpandedTool(null); }} style={{
                padding: "6px 10px", fontSize: "10px", fontWeight: 700, border: `1.5px solid ${activeLayer === key ? l.color : "#333"}`,
                borderRadius: "5px", cursor: "pointer", whiteSpace: "nowrap",
                backgroundColor: activeLayer === key ? l.color + "18" : "transparent",
                color: activeLayer === key ? l.color : "#777",
              }}>{l.icon} {l.label}</button>
            ))}
          </div>
          <div style={{ padding: "20px" }}>
            <h2 style={{ fontSize: "20px", fontWeight: 800, color: layer.color, margin: 0 }}>{layer.icon} {layer.label}</h2>
            <p style={{ color: "#888", fontSize: "12px", margin: "3px 0 16px" }}>{layer.subtitle}</p>
            <div style={{ display: "flex", flexDirection: "column", gap: "8px" }}>
              {layer.tools.map((tool, i) => {
                const isExp = expandedTool === `${activeLayer}-${i}`;
                return (
                  <div key={i} onClick={() => setExpandedTool(isExp ? null : `${activeLayer}-${i}`)} style={{
                    backgroundColor: layer.bgColor, border: `1px solid ${isExp ? layer.color + "60" : "#2a2a2a"}`,
                    borderRadius: "10px", padding: "14px", cursor: "pointer",
                  }}>
                    <div style={{ display: "flex", justifyContent: "space-between", alignItems: "flex-start", gap: "8px" }}>
                      <div style={{ flex: 1 }}>
                        <div style={{ fontSize: "14px", fontWeight: 700, marginBottom: "2px" }}>{tool.name}</div>
                        <div style={{ fontSize: "11px", color: "#999" }}>{tool.role}</div>
                      </div>
                      <div style={{ display: "flex", flexDirection: "column", alignItems: "flex-end", gap: "4px" }}>
                        <PriorityBadge priority={tool.priority} />
                        <StabilityBadge stable={tool.stable} />
                      </div>
                    </div>
                    <div style={{ fontSize: "11px", color: "#4ECDC4", fontFamily: "monospace", marginTop: "6px" }}>{tool.cost}</div>
                    {tool.note && !isExp && <div style={{ fontSize: "10px", color: tool.note.includes("⚠️") ? "#ef4444" : "#666", marginTop: "4px", lineHeight: 1.3 }}>{tool.note.substring(0, 90)}{tool.note.length > 90 ? "..." : ""}</div>}
                    {isExp && (
                      <div style={{ borderTop: `1px solid ${layer.color}25`, paddingTop: "10px", marginTop: "8px" }}>
                        {tool.note && <div style={{ fontSize: "11px", padding: "8px 10px", borderRadius: "6px", marginBottom: "10px", lineHeight: 1.4, backgroundColor: tool.note.includes("⚠️") ? "#7f1d1d20" : "#1a1a1a", color: tool.note.includes("⚠️") ? "#fca5a5" : "#aaa", border: `1px solid ${tool.note.includes("⚠️") ? "#7f1d1d40" : "#252525"}` }}>{tool.note}</div>}
                        <div style={{ fontSize: "9px", fontWeight: 700, color: "#666", letterSpacing: "0.1em", marginBottom: "6px", textTransform: "uppercase" }}>Tasks</div>
                        <div style={{ display: "flex", flexWrap: "wrap", gap: "3px" }}>
                          {tool.tasks.map((task, j) => (
                            <span key={j} style={{ fontSize: "10px", padding: "3px 8px", borderRadius: "4px", backgroundColor: layer.color + "12", color: layer.color, lineHeight: 1.3 }}>{task}</span>
                          ))}
                        </div>
                      </div>
                    )}
                  </div>
                );
              })}
            </div>
          </div>
        </div>
      )}

      {/* WORKFLOWS VIEW */}
      {activeView === "workflows" && (
        <div style={{ padding: "20px" }}>
          <h2 style={{ fontSize: "18px", fontWeight: 800, marginBottom: "4px" }}>Production Workflows</h2>
          <p style={{ color: "#777", fontSize: "12px", marginBottom: "6px" }}>Steps marked with <span style={{ color: "#4285F4", fontWeight: 700 }}>●</span> use Gemini 3.1 Pro</p>
          <div style={{ display: "flex", flexDirection: "column", gap: "12px" }}>
            {WORKFLOWS.map((wf, i) => (
              <div key={i} style={{ backgroundColor: "#161616", border: "1px solid #252525", borderRadius: "10px", padding: "16px" }}>
                <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: "12px", flexWrap: "wrap", gap: "6px" }}>
                  <h3 style={{ fontSize: "14px", fontWeight: 700, margin: 0 }}>{wf.name}</h3>
                  <div style={{ display: "flex", gap: "6px" }}>
                    <span style={{ fontSize: "10px", color: "#4ECDC4", fontFamily: "monospace", fontWeight: 600 }}>{wf.time}</span>
                    <span style={{ fontSize: "9px", padding: "2px 6px", borderRadius: "3px", backgroundColor: "#A78BFA20", color: "#A78BFA", fontWeight: 700, fontFamily: "monospace" }}>{wf.gate}</span>
                  </div>
                </div>
                {wf.steps.map((step, j) => (
                  <div key={j} style={{ display: "flex", gap: "0" }}>
                    <div style={{ display: "flex", flexDirection: "column", alignItems: "center", width: "20px", flexShrink: 0 }}>
                      <div style={{ width: "7px", height: "7px", borderRadius: "50%", backgroundColor: step.gemini ? "#4285F4" : j === wf.steps.length - 1 ? "#4ECDC4" : "#E8B931", flexShrink: 0, marginTop: "5px" }} />
                      {j < wf.steps.length - 1 && <div style={{ width: "1px", flex: 1, minHeight: "16px", backgroundColor: "#333" }} />}
                    </div>
                    <div style={{ padding: "0 0 8px 6px" }}>
                      <span style={{ fontSize: "10px", fontWeight: 700, color: step.gemini ? "#4285F4" : step.tool.includes("optional") ? "#d97706" : "#aaa", fontFamily: "monospace" }}>{step.tool}</span>
                      <div style={{ fontSize: "11px", color: "#777", marginTop: "1px" }}>{step.action}</div>
                    </div>
                  </div>
                ))}
              </div>
            ))}
          </div>
        </div>
      )}

      {/* BUDGET VIEW */}
      {activeView === "budget" && (
        <div style={{ padding: "20px" }}>
          <h2 style={{ fontSize: "18px", fontWeight: 800, marginBottom: "16px" }}>Monthly Budget</h2>
          <div style={{ fontSize: "11px", fontWeight: 700, color: "#E8B931", letterSpacing: "0.08em", textTransform: "uppercase", marginBottom: "8px" }}>Paid Subscriptions</div>
          {BUDGET.paid.map((b, i) => (
            <div key={i} style={{ display: "flex", justifyContent: "space-between", alignItems: "center", padding: "12px 14px", backgroundColor: "#161616", border: "1px solid #252525", borderRadius: "8px", marginBottom: "6px" }}>
              <div><div style={{ fontSize: "13px", fontWeight: 600 }}>{b.item}</div><div style={{ fontSize: "10px", color: "#777", marginTop: "1px" }}>{b.note}</div></div>
              <div style={{ fontSize: "15px", fontWeight: 800, color: b.color, fontFamily: "monospace" }}>{b.cost}</div>
            </div>
          ))}
          <div style={{ textAlign: "right", fontSize: "12px", color: "#888", margin: "4px 0 16px", fontFamily: "monospace" }}>
            Subscriptions: <span style={{ color: "#E8E6E1", fontWeight: 700 }}>$49/mo</span>
          </div>
          <div style={{ fontSize: "11px", fontWeight: 700, color: "#4ECDC4", letterSpacing: "0.08em", textTransform: "uppercase", marginBottom: "8px" }}>Free Tools ({BUDGET.free.length} entries covering 31+ tools)</div>
          <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: "4px", marginBottom: "16px" }}>
            {BUDGET.free.map((t, i) => (
              <div key={i} style={{ fontSize: "10px", padding: "8px 10px", backgroundColor: "#161616", border: "1px solid #252525", borderRadius: "6px" }}>
                <div style={{ fontWeight: 700, color: "#aaa" }}>{t.item} <span style={{ color: "#4ECDC4" }}>{t.cost}</span></div>
                <div style={{ color: "#666", marginTop: "2px", lineHeight: 1.3 }}>{t.note}</div>
              </div>
            ))}
          </div>
          <div style={{ padding: "14px", backgroundColor: "#0a2a1a", border: "1px solid #16a34a30", borderRadius: "8px" }}>
            <div style={{ fontSize: "11px", fontWeight: 700, color: "#4ECDC4", textTransform: "uppercase", letterSpacing: "0.08em" }}>Remaining Monthly Budget</div>
            <div style={{ fontSize: "24px", fontWeight: 800, color: "#4ECDC4", fontFamily: "monospace" }}>{BUDGET.remaining}</div>
            <div style={{ fontSize: "11px", color: "#888", marginTop: "2px" }}>{BUDGET.remainingUses}</div>
          </div>

          <div style={{ fontSize: "11px", fontWeight: 700, color: "#F97316", letterSpacing: "0.08em", textTransform: "uppercase", marginTop: "20px", marginBottom: "8px" }}>Revenue-Triggered Upgrades</div>
          {BUDGET.upgradeTriggers.map((u, i) => (
            <div key={i} style={{ padding: "10px 12px", backgroundColor: "#1E1810", border: "1px solid #3D2E1A", borderRadius: "8px", marginBottom: "6px" }}>
              <div style={{ fontSize: "9px", fontWeight: 700, color: "#F97316", letterSpacing: "0.06em", textTransform: "uppercase", fontFamily: "monospace" }}>{u.trigger}</div>
              <div style={{ fontSize: "12px", fontWeight: 600, color: "#E8E6E1", marginTop: "2px" }}>{u.action}</div>
              <div style={{ fontSize: "10px", color: "#888", marginTop: "1px" }}>{u.reason}</div>
            </div>
          ))}
        </div>
      )}

      {/* QC SYSTEM VIEW */}
      {activeView === "qc" && (
        <div style={{ padding: "20px" }}>
          <h2 style={{ fontSize: "18px", fontWeight: 800, marginBottom: "4px" }}>Four-Gate Quality System</h2>
          <p style={{ color: "#777", fontSize: "12px", marginBottom: "16px" }}>Gate 4 (Second Opinion) uses Gemini 3.1 Pro for high-stakes deliverables</p>
          {QC_GATES.map((g, i) => (
            <div key={i} style={{ padding: "14px", backgroundColor: "#161616", border: `1px solid ${g.color}30`, borderRadius: "10px", marginBottom: "8px" }}>
              <div style={{ display: "flex", alignItems: "center", gap: "8px", marginBottom: "6px" }}>
                <span style={{ fontSize: "10px", fontWeight: 800, padding: "3px 8px", borderRadius: "4px", backgroundColor: g.color + "20", color: g.color, fontFamily: "monospace" }}>{g.gate}</span>
                <span style={{ fontSize: "14px", fontWeight: 700 }}>{g.name}</span>
              </div>
              <div style={{ fontSize: "15px", fontWeight: 800, color: g.color, marginBottom: "6px" }}>{g.question}</div>
              <div style={{ fontSize: "11px", color: "#999", lineHeight: 1.6 }}>{g.checks}</div>
            </div>
          ))}
          <div style={{ marginTop: "16px" }}>
            <h3 style={{ fontSize: "14px", fontWeight: 700, color: "#E8B931", marginBottom: "10px" }}>Re-Audit Cycles</h3>
            {[
              { cycle: "After every delivery", time: "5 min", checks: "Brief match • Tool efficiency • Time vs estimate • One improvement • Surprise log" },
              { cycle: "Every Sunday", time: "30 min", checks: "Tool health • Credit monitoring (Veo + Higgsfield) • Quality trends • Client satisfaction • Skill gaps" },
              { cycle: "First of every month", time: "2 hours", checks: "Tool pricing changes • Competitor scan • Price review • Workflow optimization • Revenue vs target • Client pipeline" },
            ].map((c, i) => (
              <div key={i} style={{ padding: "10px 12px", backgroundColor: "#1a1a1a", border: "1px solid #252525", borderRadius: "8px", marginBottom: "6px" }}>
                <div style={{ display: "flex", justifyContent: "space-between" }}>
                  <span style={{ fontSize: "13px", fontWeight: 700 }}>{c.cycle}</span>
                  <span style={{ fontSize: "10px", color: "#4ECDC4", fontFamily: "monospace", fontWeight: 600 }}>{c.time}</span>
                </div>
                <div style={{ fontSize: "11px", color: "#888", marginTop: "3px" }}>{c.checks}</div>
              </div>
            ))}
          </div>
        </div>
      )}

      {/* BACKUPS VIEW */}
      {activeView === "backups" && (
        <div style={{ padding: "20px" }}>
          <h2 style={{ fontSize: "18px", fontWeight: 800, marginBottom: "16px" }}>Zero-Compromise Backups</h2>
          {[
            { tool: "Pomelli", backup: "Claude Brand Sheet + Nanobanana Pro", verdict: "BETTER", vc: "#16a34a", detail: "Pomelli now global (170+ countries, March 2026) — use it directly. Backup still better for depth: deeper analysis, better copy" },
            { tool: "Stitch", backup: "Claude Artifacts + Antigravity", verdict: "BETTER", vc: "#16a34a", detail: "Stitch redesigned March 2026 with React export + MCP. Now a serious tool, but backup still builds functional products." },
            { tool: "Mixboard", backup: "Nanobanana Pro + Canva layout", verdict: "EQUAL", vc: "#E8B931", detail: "Same quality, slightly more manual" },
            { tool: "Opal", backup: "Claude Artifacts + Antigravity", verdict: "BETTER", vc: "#16a34a", detail: "More powerful and customizable" },
            { tool: "Antigravity", backup: "v0 free tier + Claude Artifacts + Lovable", verdict: "EQUAL", vc: "#E8B931", detail: "v0 and Lovable build pages from descriptions. Claude generates React. Multiple strong alternatives exist." },
            { tool: "Grok (X social listening)", backup: "Manual X search + third-party free tools", verdict: "WEAKER", vc: "#ef4444", detail: "No free tool replicates Grok's live X data stream. Manual search is slower. Accept the gap — Grok is free and works." },
            { tool: "Claude (hypothetical)", backup: "Gemini 3.1 Pro for analysis + strategy", verdict: "PARTIAL", vc: "#F97316", detail: "Gemini handles analysis/strategy but cannot create documents via Skills or generate tool-specific prompts as well" },
            { tool: "HeyGen (removed)", backup: "Kling Avatar via Higgsfield Pro", verdict: "REPLACED", vc: "#16a34a", detail: "Kling Avatar does everything HeyGen does — photo + audio → talking avatar, 1080p 48fps, up to 1 min. Already in your Higgsfield Pro." },
            { tool: "ElevenLabs (removed → re-added)", backup: "Kling 3.0 + Veo 3.1 native audio", verdict: "RE-ADDED", vc: "#16a34a", detail: "Re-added as free tier SPECIALIST for standalone audio (non-video voiceovers). Video native audio from Kling/Veo covers 90% of needs. ElevenLabs free tier covers the other 10%." },
          ].map((b, i) => (
            <div key={i} style={{ padding: "12px", backgroundColor: "#161616", border: "1px solid #252525", borderRadius: "10px", marginBottom: "8px" }}>
              <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: "4px" }}>
                <span style={{ fontSize: "13px" }}><span style={{ color: "#888" }}>If </span><span style={{ fontWeight: 700, color: "#F59E0B" }}>{b.tool}</span><span style={{ color: "#888" }}> disappears:</span></span>
                <span style={{ fontSize: "9px", fontWeight: 800, padding: "2px 8px", borderRadius: "3px", backgroundColor: b.vc + "20", color: b.vc, fontFamily: "monospace" }}>BACKUP: {b.verdict}</span>
              </div>
              <div style={{ fontSize: "12px", fontWeight: 600, marginBottom: "2px" }}>→ {b.backup}</div>
              <div style={{ fontSize: "10px", color: "#888" }}>{b.detail}</div>
            </div>
          ))}
          <div style={{ marginTop: "16px", padding: "14px", backgroundColor: "#0a2a1a", border: "1px solid #16a34a30", borderRadius: "10px" }}>
            <div style={{ fontSize: "12px", fontWeight: 700, color: "#4ECDC4", marginBottom: "4px" }}>THE PRINCIPLE</div>
            <div style={{ fontSize: "13px", lineHeight: 1.5 }}>
              <span style={{ fontWeight: 700, color: "#F59E0B" }}>Speed boosters</span>, never <span style={{ fontWeight: 700, color: "#ef4444" }}>foundations</span>. Core stable stack handles 100% of client work independently.
            </div>
          </div>
        </div>
      )}

      {/* GEMINI MAP VIEW */}
      {activeView === "gemini" && (
        <div style={{ padding: "20px" }}>
          <h2 style={{ fontSize: "18px", fontWeight: 800, marginBottom: "4px" }}>
            <span style={{ color: "#4285F4" }}>●</span> Gemini 3.1 Pro Integration Map
          </h2>
          <p style={{ color: "#777", fontSize: "12px", marginBottom: "16px" }}>Every place Gemini 3.1 Pro adds value in your agency</p>

          {[
            { area: "🧠 Brain Layer", role: "SECOND BRAIN", items: [
              "Second opinion on high-stakes strategy documents",
              "Complex data synthesis (spreadsheets, multi-source reports)",
              "Cross-check Claude's analysis for blind spots",
              "Client competitor analysis verification",
            ]},
            { area: "📚 NotebookLM", role: "CLIENT KNOWLEDGE BASE", items: [
              "One notebook per client — upload ALL their materials",
              "Chat with client docs for instant context before calls",
              "Cross-reference goals against existing content",
              "Audio summaries of long client briefs",
            ]},
            { area: "🔍 GEO Service Delivery", role: "6 TESTING PLATFORMS", items: [
              "Gemini 3.1 Pro: what does Google's AI recommend?",
              "ChatGPT: what does OpenAI's AI recommend?",
              "Claude: what does Anthropic's AI recommend?",
              "Perplexity: what does Perplexity recommend?",
              "Grok: what does X's AI recommend? + real-time X sentiment",
              "DeepSeek (optional): what does Chinese AI recommend? ⚠️ No client data — generic queries only",
              "Compare all 6 platforms → most comprehensive GEO audit in the market",
            ]},
            { area: "🏗️ Google Antigravity", role: "BUILD ENGINE (Desktop IDE)", items: [
              "Powers landing page & web app generation from descriptions",
              "Handles code generation, testing, and deployment autonomously",
              "Built-in image generation via Nanobanana",
              "Browser sub-agent for automated QA testing",
              "Agent Manager for parallel task execution",
              "Must be downloaded — not browser-based",
            ]},
            { area: "🎬 Google Flow", role: "CREATIVE STUDIO ENGINE", items: [
              "Prompt interpretation for image + video generation",
              "Asset management and smart grid organization",
              "Frames-to-video pipeline orchestration",
            ]},
            { area: "✅ Quality Control", role: "GATE 4: SECOND OPINION", items: [
              "Run proposals >$1K through Gemini before sending",
              "Verify GEO audit findings with Gemini's perspective",
              "Cross-check brand strategy recommendations",
              "Flag disagreements between Claude and Gemini for investigation",
            ]},
          ].map((section, i) => (
            <div key={i} style={{ padding: "14px", backgroundColor: "#161616", border: "1px solid #4285F430", borderRadius: "10px", marginBottom: "8px" }}>
              <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: "8px" }}>
                <span style={{ fontSize: "14px", fontWeight: 700 }}>{section.area}</span>
                <span style={{ fontSize: "9px", fontWeight: 800, padding: "2px 8px", borderRadius: "3px", backgroundColor: "#4285F420", color: "#4285F4", fontFamily: "monospace" }}>{section.role}</span>
              </div>
              {section.items.map((item, j) => (
                <div key={j} style={{ fontSize: "11px", color: "#aaa", padding: "3px 0 3px 16px", lineHeight: 1.4, borderLeft: "2px solid #4285F430", marginBottom: "2px" }}>{item}</div>
              ))}
            </div>
          ))}

          <div style={{ marginTop: "16px", padding: "14px", backgroundColor: "#1a1a2e", border: "1px solid #4285F430", borderRadius: "10px" }}>
            <div style={{ fontSize: "12px", fontWeight: 700, color: "#4285F4", marginBottom: "6px" }}>CLAUDE vs GEMINI vs GROK: WHEN TO USE WHICH</div>
            <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr 1fr", gap: "8px" }}>
              <div>
                <div style={{ fontSize: "10px", fontWeight: 700, color: "#E8B931", marginBottom: "4px" }}>CLAUDE (Primary)</div>
                <div style={{ fontSize: "10px", color: "#aaa", lineHeight: 1.5 }}>All copywriting • All prompts • Strategy docs • Client proposals • Skills (.docx .pdf) • Artifacts • Campaign mgmt • Brand sheets</div>
              </div>
              <div>
                <div style={{ fontSize: "10px", fontWeight: 700, color: "#4285F4", marginBottom: "4px" }}>GEMINI (Support)</div>
                <div style={{ fontSize: "10px", color: "#aaa", lineHeight: 1.5 }}>GEO testing • NotebookLM • Second opinions • Data analysis • Powers Antigravity • Powers Flow • Cross-check</div>
              </div>
              <div>
                <div style={{ fontSize: "10px", fontWeight: 700, color: "#1DA1F2", marginBottom: "4px" }}>GROK (Specialist)</div>
                <div style={{ fontSize: "10px", color: "#aaa", lineHeight: 1.5 }}>X social listening • Trend detection • Brand sentiment on X • GEO testing (5th platform) • Never for production</div>
              </div>
            </div>
          </div>
        </div>
      )}

      <div style={{ padding: "16px 20px", borderTop: "1px solid #1a1a1a", textAlign: "center" }}>
        <p style={{ fontSize: "10px", color: "#444", margin: 0, fontFamily: "monospace" }}>
          Ecosystem v4.1 • 34 tools • Brand Design Master System • 6-platform GEO • Updated March 28, 2026
        </p>
      </div>
    </div>
  );
}
