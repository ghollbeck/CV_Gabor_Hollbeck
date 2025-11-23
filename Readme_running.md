# 2025-11-23 Fix LaTeX compilation error in `kurzversion/CV_Gabor_kurz.tex`

## Before
- Objective: Resolve LaTeX compilation failure caused by ampersand in `kurzversion/CV_Gabor_kurz.tex`.
- Planned diffs: Escape the literal ampersand in the MSc entry so it renders as text.
- Test plan: Recompile the CV with `latexmk -pdf kurzversion/CV_Gabor_kurz.tex`.
- Rollback strategy: Revert the change to the LaTeX source if the compilation still fails or introduces regressions.

## During
- Reproduced the compilation error locally with `latexmk -pdf kurzversion/CV_Gabor_kurz.tex`.
- Escaped the ampersand in the MSc focus line to eliminate the alignment token error.
- Re-ran `latexmk -pdf kurzversion/CV_Gabor_kurz.tex` to ensure the document builds; compilation succeeded with existing warnings only.

## After
- Final diffs: Escaped `&` ➜ `\&` in the MSc focus line within `kurzversion/CV_Gabor_kurz.tex`.
- Tests executed: `latexmk -pdf kurzversion/CV_Gabor_kurz.tex` (passes; warnings unchanged from prior runs).
- Known gaps / next steps: None identified.

