The ENVI file reader has not been updated in quite some time however it is used as a dependency in a lot of hyperspectral applications.

With that in mind I have updated the code with the following:

- a check for the presence of geographical information so that it works with non-georeferenced imagery, and
- inserted `machine` into the `bil ` and `bip` interleave cases `fread` calls to handle big-endian ordered data.

---

I = ENVIREAD(FILENAME) Reads an ENVI binary file into an array using the information from the corresponding header file FILENAME.hdr. The output structure I contains fields I.x, I.y, I.z and I.info containing the x-coordinate vector, y-coordinate vector, images data and header info, respectively. I.z will be in whatever number format (double, int, etc.) as in the envi file.

I= ENVIREAD(FILENAME,HEADERFILE); Uses the header information in headerfile.
'
Thanks to Yushin Ahn for his modifications.
NOTES:
-Geo-registration does not currently support rotated images.

- No support for importing complex data .

Copyright (c) 2009, Ian Howat
All rights reserved.

Ian Howat (2024). ENVI file reader, updated 2/9/2010 (https://www.mathworks.com/matlabcentral/fileexchange/15629-envi-file-reader-updated-2-9-2010), MATLAB Central File Exchange. Retrieved November 20, 2024.
