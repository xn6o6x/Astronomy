---
titles: Calibration
tags: Astronomy, IRA, DS9
---

# [WCStools](http://tdc-www.harvard.edu/software/wcstools/wcstools.readme.html) Installation

1. Download the current version of the WCSTools package from [here](http://tdc-www.harvard.edu/software/wcstools/wcstools.tar.gz).
2. Unzip and Untar this file, go to that directory and type
    ```bash=
    make all
    ```
3. Set environment variable
    ```bash=
    open .zshrc
    ```
    and add
    ```bash=
    export PATH="/Users/jackarroy/wcstools-3.9.5/bin:$PATH"
    ```
    and you can run `imwcs` anywhere.
    
4. Otherwise
    ```bash=
    cd wcstools-3.9.5/bin
    ./imwcs
    ```
---
# Calibration

1. **Astrometry calibration**: Astrometry determines how the pixel in an image are matched to positions on the sky.
2. **Flux calibration**: Convert the measured instrumental magnitudes to real UBVRI magnitudes

## Step 1. Decide `ra_ct`, `dec_ct`, `PA_N`
 
1. open reference and task images at ds9
2. change the color scale until see the clear morphology
3. rotate and zoom in/out the task image to match the reference image
4. put cursor on the flux peak to get the coordinate from the reference image
`ra = 8:49:22.5605`, `dec = +36:42:37.086`, `PA = -52.5`

## Step 2. Get Star List

![](https://i.imgur.com/Y8ZO3xC.png)
![](https://i.imgur.com/1DRU0K5.png)
![](https://i.imgur.com/dVWUiYQ.png)

<iframe width="100%" height="500" src="https://hackmd.io/@juian/HJdr93BqH" frameborder="0"></iframe>

## Step 3. Calibrate Astrometry (`WCStools`)
```bash=
imwcs -c sdss test1_rot_addnoise.fits -vw -p 0.396 -h 200 -j ra_ct dec_ct -d starlist -e -a pa_N -o ouput_file.fits
```
    


## Step 4. Get Flux and x,y (`IRAF.Phot`)

Phot.Image=[your image]
Phot.coords=[output of starfind/daofind]
Photpar.apertur=6
Photpar.Zmag=0
Fitskypar.Annulus=20

- IRAF.txdump xcenter, ycenter, flux
- Python: {xcenter, ycenter} + {CD1_1, CD1_2, CD2_1, CD2_2} => ra, dec

## Step 5. SDSS fluxes
Search for SDSS fluxes within the image area

## Step 6. SDSS catalog
Match with SDSS catalog (dis_max=FWHM of PSF) to do flux calibration




