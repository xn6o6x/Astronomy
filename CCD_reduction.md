---
titles: CCD reduction-IRAF
tags: Astronomy, IRAF
---

# CCD reduction-IRAF
---
## Conbine Bias
1. ==!rm master_bias.fits== if file exsits
2. ==imred.ccdred==
3. ==epar zerocombine== edit parameters
![](https://i.imgur.com/jsIRhyG.png)
- ccdtype 
`“dark”` when combine dark
`“ ”` when combine flat and bias
- vi
`:q` quit without saving changes
`:wq` save changes and quit vi
`:g` run
4. ==zerocombine== or `:g` in epar

---
## Subtract Bias
1. ==ls -1 flat*.fits m67*.fits > other_than_bias.list==
`ls -1` show in one line
3. ==imarith @other_than_bias.list - master_bias.fits @other_than_bias.list==
4. ==ls -1 flat_b*.fits > flat_b.list==

---
## Combine Flat
1. ==imred.ccdred==
2. ==epar flatcombine==
![](https://i.imgur.com/QDUofvu.png)

---
## Normalize Flat
1. ==imstat master_flat_b.fits==
![](https://i.imgur.com/EO3oO1P.png)
2. ==imarith master_flat_b.fits / 35706 master_flat_b.fits==

---
## Divided by Flat
1. ==ls -1 m67b*.fits > m67_b.list==
2. ==imarith @m67_b.list / master_flat_b.fits @m67_b.list==

---
## Combine Image
1. ==epar imcombine==
![](https://i.imgur.com/rwr8MDO.png)

