This is a highly experimental version of the Solex_ser_recon code developed by Valerie Desnoux and improved by Douglas Smith (thelondonsmiths), djibb, and others.  It may or may not stay in sync with that codebase.  For a version of Sole_ser_recon_EN that supports both SER and AVI files and is intended to stay close to thelondonsmith's code, see
  https://github.com/mattconsidine/Solex_ser_recon_AVI

Solar disk reconstruction from SHG (spectroheliography) SER files. AVI files are also supported.
If no spectral line can be recognised in the video file, the program will stop.

Install the most recent version of Python from python.org. During Windows installation, check the box to update the PATH.

For Windows, double click the windows_setup file to install the needed Python libraries.

Usage: 

Graphical user interface: launch SHG_MAIN (by double clicking under Windows). A Windows Desktop shortcut can also be created.
In the Python GUI window, enter the name of the video file(s) to be processed. Batch processing is possible but will halt if a file is unsuitable.
Command line interface, e.g. : python SHG_MAIN.py your_video_file1.SER [your_video_file2.SER ... if batch processing]

Check the "Show graphics" box for a live reconstruction display, a graphic of the geometry correction and a quick view of the final images. 
This will increase processing time significantly. This feature is not recommended for batch processing.

If the "Save .fits files" box is checked, the following files will be stored in the same directory as the video file:

- xx_mean.fits: average image of all the frames in the video of the spectral line
- xx_img.fits: raw image reconstruction
- xx_corr.fits: image corrected for outliers
- xx_flat.fits: corrected flat image
- xx_recon.fits: final image, corrected for tilt
- xx_clahe.fits: final image, with Contrast Limited Adaptive Histogram Equalization

If the "Save CLAHE.png only" box is checked, then only the final PNG image with Contrast Limited Adaptive Histogram Equalization will be saved.

Y/X ratio: enter a specific Y/X ratio, if this is known. Leave blank for auto-correction. Enter 1 if no correction desired.

Tilt angle: enter a specific tilt angle in degrees. Leave blank for auto-correction. Enter 0 if no tilt correction desired.

Pixel offset: offset in pixels from the minimum of the line to reconstruct the image on another wavelength (displaced from the central minimum).

Geometry correction may fail under certain circumstances and the program will stop. In this case, enter the Y/X ratio and Tilt angle manually (try 1, 0 initially).

For rapid processing during data acquisition, make sure "Show graphics" is off. Automatic geometry correction will also take some additional time.
Moroever, if Y/X is set to 1, distortion due to inappropriate scanning speed vs frame rate can be recognised and optimised.
Similarly, if Tilt is set to 0, instrument misalignment can be recognised and corrected.

Geometry graphics window can be killed by pushing 'X'.
Composite results window should be killed by pushing any key on the keyboard.
