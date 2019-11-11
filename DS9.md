---
titles: DS9
tags: Astronomy, DS9
---

# DS9

[DS9 Preference](http://spiff.rit.edu/tass/ds9/prefs.html)
[Introduction to Astronomy Images and the DS9 Image Viewer](http://www.jb.man.ac.uk/~gbendo/Sci/Pict/DS9guide.pdf)
[The FITS Image Format and Image Display with DS9](http://faculty.virginia.edu/ASTR5110/PRACTICAL4/astr5110_practical4_v4.3.pdf)

---
## Scale > ==**log**==

[DS9 Scale Menu](http://spiff.rit.edu/tass/ds9/mscale.html)

- With some images, clicking on Scale in the menu bar and then selecting 99.5%, `Zscale`, or `Zmax` sometimes produces better results.
- `Zscale Algorithm`: display the image values near the **median image value** without the time consuming  process of computing a full image histogram. This is particularly useful for astronomical images which generally have a very peaked histogram corresponding to the background sky in direct imaging or the continuum in a two dimensional spectrum. [Read more](https://iraf.net/forum/viewtopic.php?showtopic=134139)

---
## Brightness & Contrast

- Move the cursor to the image window.
- Hold the right mouse button down.
- While holding the right mouse button down, move the curson within the image window.

---
## Text Information
### WCS vs. FK5

- The fourth line labelled `“WCS”` shows the coordinates at the position of the cursor in **astronomical coordinates** (or the **World Coordinate System**).
    - ==**World Coordinate System (WCS)**== is a set of transformations that map pixel locations in an image to their real-world units, such as their position on the sky sphere. These transformations can work both forward (from pixel to sky) and backward (from sky to pixel). [Read more](https://adl1995.github.io/an-introduction-to-coordinate-systems-used-in-astronomy.html)
- In the default system (labelled `“FK5”`), the first number is **right ascension**, and the second number is **declination**.
    - ==**Fifth Fundamental Catalogue (FK5)**== is part of the “Catalogue of Fundamental Stars” which provides a series of six astrometric catalogues of high precision positional data for a small selection of stars to define a celestial reference frame. J2000 refers to the instant of 12 PM (mid-day) on 1st January, 2000. FK5 was published in 1991 and added 3,117 new stars. [Read more](https://adl1995.github.io/an-introduction-to-coordinate-systems-used-in-astronomy.html)

### Physical

- The fifth line labelled `“Physical”` shows the coordinates at the position of the cursor in terms of the physical location on the astronomical detector used to make the image.
- For most FITS images, either the image does not contain the correct information needed to display physical coordinates properly, or this type of physical coordinate system is not applicable, so you can ignore it.

---
## Change Default Setting
Preferences > Menu
1. **scale > log**
2. **color > sls**

---
## Tips

### Fix Cursor
`region mode > circle > double click`