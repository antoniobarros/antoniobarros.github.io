# CardioNIR — NIRS in PAD: Website Page

## Files included

```
_quarto.yml                              ← Updated config (adds Projects dropdown)
projects/
  cardionir-pad-nirs.qmd                 ← The showcase page
  cardionir-pad-nirs-banner.svg          ← Banner / thumbnail image
```

## How to integrate

1. **Copy the `projects/` folder** into the root of your Quarto site repo.

2. **Update `_quarto.yml`**: either replace yours with the provided one, or
   manually add the Projects dropdown to your existing navbar. The only change
   is replacing the existing navbar `left:` entries with:

   ```yaml
   left:
     - href: index.qmd
       text: Home
     - href: research.qmd
       text: Research
     - href: publications.qmd
       text: Publications
     - text: Projects
       menu:
         - href: projects/cardionir-pad-nirs.qmd
           text: "CardioNIR — NIRS in PAD"
     - href: teaching.qmd
       text: Teaching
     - href: cv.qmd
       text: CV
     - href: posts.qmd
       text: Blog
   ```

   As you add more project pages, just add more `- href: ...` entries under
   the `menu:` list.

3. **Render**: `quarto render` (or `quarto preview`) as usual.

## Customisation notes

- All CSS uses Bootstrap `var(--bs-...)` tokens, so it adapts to both
  your **Flatly** (light) and **Darkly** (dark) themes automatically.
- The banner SVG is used as the listing `image:` in the YAML front matter.
  You can replace it with a PNG/JPG screenshot of the paper figures if
  you prefer.
- A BibTeX entry is included on the page. If you want it in your global
  `references.bib`, just paste it there.
- The page uses `title-block-banner: "#1a2a3a"` for a dark header band
  that pairs well with the Flatly navbar colour.
