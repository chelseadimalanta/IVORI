# Solenne: Gen-AI use and prompts

The ITM550 work-in-progress brief asks for the prompt used for each AI-generated content item (image, video, text), with a reference. This file is the running log. Copy it into the WIP report appendix.

## 1. Website (code, layout and copy)

- **Tool:** Claude (Anthropic), model Claude Opus 5.5, via claude.ai
- **Used for:** brand name shortlist, the colour palette, the single-page website (HTML, CSS, JavaScript) and its on-page copy.
- **Key prompts (in order):**
  1. "We need to do two things, rebrand. We need a new name, new color palette. [...] Right now we got to do a website mock-up."
  2. Uploaded my proposal feedback PDF: "understand the concept first. current name is [bad]."
  3. "Give me more. More premium. We're basing this off lululemon website basically. Aritzia. That aesthetic."
  4. "solenne it is. use all info i gave u when it comes to concept. [...] lets proceed with the website. simple lightweight. [...] base it on https://www.aritzia.com/en, https://shop.lululemon.com/en-ca/ and https://www.apple.com/"
  5. Uploaded the WIP brief: "check the rubric, lets tweak the page for it to be satisfactory [...] What else are we missing from the assignment, give me a to do list."
- **Reference (APA):** Anthropic. (2026). *Claude* (Opus 5.5) [Large language model]. https://claude.ai

## 2. Product images (to generate)

Use the same base prompt for every product so the set looks consistent. Fill in the item line, generate one image per product in its first colour, and log the tool and date below.

**Base prompt**
> Professional e-commerce product photo of a women's modest activewear piece: {ITEM}. Shown on an invisible ghost mannequin, front view, centred. Plain warm sand-coloured studio background, soft natural daylight, gentle shadow under the garment. Realistic fabric texture, crisp detail, premium minimalist style like Aritzia or Lululemon. No logos, no text, no people. Portrait 4:5.

| File name | {ITEM} |
|---|---|
| `flow-long-sleeve-onyx.jpg` | fitted long-sleeve top with a high crew neck and thumbholes, hem covering the hips, matte black brushed fabric |
| `stride-tunic-spruce.jpg` | long-sleeve athletic tunic top reaching mid-thigh with small side vents, high crew neck, deep spruce green |
| `layer-mock-neck-ivory.jpg` | fitted long-sleeve mock-neck base layer, below-hip length, soft ivory, fully opaque |
| `ease-half-zip-clay.jpg` | relaxed half-zip fleece pullover with funnel collar and thumbholes, hip length, warm clay red |
| `shelter-jacket-onyx.jpg` | lightweight water-resistant hooded jacket, mid-thigh length, full zip, black ripstop |
| `anchor-legging-onyx.jpg` | high-rise full-length leggings, ankle length, thick opaque matte black fabric |
| `drift-wide-leg-onyx.jpg` | high-rise floor-length wide-leg stretch pants, fluid drape, black |
| `motion-midi-skirt-onyx.jpg` | A-line athletic midi skirt to mid-calf with full-length black leggings built in underneath, black |
| `studio-wrap-skirt-spruce.jpg` | below-knee jersey wrap skirt with side waist tie, worn over leggings, spruce green |

**Lifestyle prompt (3 to 4 images for the home page)**
> Editorial lifestyle photo of {SCENE}. Women of diverse backgrounds and body types wearing modest activewear: long sleeves, longer hems, full-length leggings or athletic skirts; some wear sports hijabs. Muted palette of black, deep spruce green, sand and clay red. Natural light, candid, premium brand campaign style. No logos or text. Landscape 16:10.

Scenes: (a) a bright pilates studio with wood floors; (b) two friends walking along the Toronto waterfront in autumn; (c) a woman stretching at a gym before lifting; (d) a group yoga class from a low angle.

**Log** (fill in as you generate)

| Images | Tool | Date | Prompt used |
|---|---|---|---|
| 13 product photos (9 products, 4 with a second angle) | Google Gemini | Nov 4, 2026 | Base product prompt above, one item line per product |
| 3 lifestyle photos (waterfront, pilates studio, gym) | Google Gemini | Nov 4, 2026 | Lifestyle prompt above, scenes (b), (a) and (c) |

Originals are kept in `assets/`. The site uses compressed, renamed copies in `images/`. Gemini added a small SOLENNE wordmark to some product shots even though the prompt asked for no logos; I kept those because they fit the brand.

**Reference (APA):** Google. (2026). *Gemini* [Generative AI model]. https://gemini.google.com

## 3. Adding more photos to the site

1. Put the images in the `images/` folder in this repo.
2. In `index.html`, find `const IMAGES={};` and list each file, for example:
   ```js
   const IMAGES={
     'flow-long-sleeve':'images/flow-long-sleeve-onyx.jpg',
     'anchor-legging':'images/anchor-legging-onyx.jpg'
   };
   ```
   Use `'product-id/Colour'` as the key to set a photo for one colour only.
3. Commit and push. Products without a photo keep their drawing.
