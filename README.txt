site-changes — drop-in archive
================================

This archive contains six .qmd files at the paths they should occupy in your
Quarto site root. Unzip from your repo root and the directory structure lines
up with the existing one.

Files in this archive
---------------------

  teaching.qmd                                  REPLACES existing
  teaching/biostatistics/index.qmd              NEW
  teaching/biostatistics/splines-live.qmd       REPLACES existing
  projects.qmd                                  NEW
  projects/cardionir/index.qmd                  NEW
  projects/iberia/index.qmd                     NEW

What unzipping does NOT do
--------------------------

The four existing CardioNIR pages still live at their old paths. They need
to be moved into projects/cardionir/ to be picked up by the new family
listing. After unzipping, run from the repo root:

  git mv projects/cardionir-metabolomics.qmd projects/cardionir/metabolomics.qmd
  git mv projects/cardionir-pad-nirs.qmd     projects/cardionir/pad-nirs.qmd
  git mv projects/cardionir-pipeline.qmd     projects/cardionir/pipeline.qmd
  git mv projects/cardionir-proteomics.qmd   projects/cardionir/proteomics.qmd

Clear the stale freeze cache for any pages that moved:

  rm -rf _freeze/splines-live
  rm -rf _freeze/teaching/splines-live
  rm -rf _freeze/projects/cardionir-metabolomics
  rm -rf _freeze/projects/cardionir-pad-nirs
  rm -rf _freeze/projects/cardionir-pipeline
  rm -rf _freeze/projects/cardionir-proteomics

Then render and preview:

  quarto render
  quarto preview

Sanity checks
-------------

  /teaching.html              -> single card linking to Biostatistics
  /teaching/biostatistics/    -> listing with the splines lesson card
  /teaching/biostatistics/splines-live.html
                              -> live document, slider drives the spline fit
  /projects.html              -> two cards: CardioNIR, IBERIA
  /projects/cardionir/        -> listing of the four sub-analyses
  /projects/iberia/           -> standalone landing page (sub-pages forthcoming)

If the four CardioNIR sub-pages render with empty card text in the family
listing, their YAML headers are missing `description:` and `categories:`.
Look at splines-live.qmd for the pattern.

Have fun.
