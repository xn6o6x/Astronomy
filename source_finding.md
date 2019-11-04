---
title: Source findiing-IRAF
tags: Astronomy, IRAF
---

# Source findiing-IRAF

---
## Daofind

1. ==digiphot.apphot.fitskypars==
![](https://i.imgur.com/1G49oPt.png)

2. ==digiphot.apphot.findpars==
![](https://i.imgur.com/GUOWKCN.png)

3. ==digiphot.apphot.datapars==
![](https://i.imgur.com/7UNnikp.png)

4. ==digiphot.apphot.photpars==
![](https://i.imgur.com/XqvnBBd.png)

5. ==digiphot.apphot.daofind==
![](https://i.imgur.com/FXhhY5y.png)

---
## Check results

1. ==display m67_b_final.fits== Open `ds9` first, then run `display`.
![](https://i.imgur.com/LX1bnz3.jpg)

2. ==tvmark 1 m67_b_final.fits.coo.1 col=204== `col`: color
![](https://i.imgur.com/x6cvhe6.jpg)

3. ==txdump m67_b_final.fits.coo.1 XCENTER,YCENTER > filename.reg==

4. ==region > load > filename.reg > format: xy==
![](https://i.imgur.com/00nxpsK.jpg)



