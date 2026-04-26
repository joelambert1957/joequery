# Ask Joe — StoryHost AI Facilitator

An AI facilitator built on Joe Lambert's voice and frameworks, with an integrated AI Green Meter for environmental transparency.

## What it does

- Answers questions about digital storytelling, the Seven Elements, Signpost Stories, narrative gerontology, aging, and facilitation
- Tracks the real-time environmental cost (energy, water, carbon) of each AI exchange
- Compares session impact to everyday equivalents

## Deploy to Netlify (5 minutes)

1. Upload this folder to a new GitHub repository (or drag-drop the folder to Netlify)
2. In Netlify → Site settings → Environment variables, add:
   ```
   ANTHROPIC_API_KEY = sk-ant-your-key-here
   ```
3. Deploy. Netlify auto-detects the `netlify.toml` and builds the function.

## Embed on Squarespace (storyhost.net)

In any Squarespace page, add an **Embed block** (under "More" in the block picker) and paste:

```html
<iframe 
  src="https://YOUR-NETLIFY-SITE.netlify.app" 
  width="100%" 
  height="680" 
  frameborder="0" 
  style="border:none; border-radius:8px;">
</iframe>
```

Replace `YOUR-NETLIFY-SITE` with your actual Netlify subdomain.

## File structure

```
ask-joe/
├── index.html                    ← the full UI (chat + meter)
├── netlify.toml                  ← Netlify build config
├── .env.example                  ← copy to .env for local dev
├── README.md
└── netlify/
    └── functions/
        └── chat.js               ← serverless Claude API proxy
```

## The system prompt

Joe's voice and frameworks are baked into `netlify/functions/chat.js`. Edit the `SYSTEM_PROMPT` constant to update what Ask Joe knows or emphasizes. It currently covers:
- Seven Elements of Digital Storytelling
- Signpost Stories framework
- Narrative gerontology (Tornstam, Freeman, McAdams, Carstensen, Myerhoff, Kegan)
- Freirean pedagogy and cultural democracy
- Trauma and healing (van der Kolk, Menakem)
- Joe's voice, politics, and cultural references

## Cost

Claude Sonnet 4 (the model used): approximately $3 per million input tokens, $15 per million output tokens.
A typical conversation exchange costs ~$0.002–0.005. At 100 conversations/month: ~$0.50–1.00/month.

## Environmental transparency

The green meter estimates environmental cost per exchange based on actual token counts returned by the API. Methodology: Jegham et al. (2025), Google/Gemini (2025), Seedling.earth (2025). Anthropic does not publish per-query data; all figures are third-party extrapolations at US grid intensity (~350 g CO₂e/kWh).
