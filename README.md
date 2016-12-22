# h5utils_patch
This repository contains a patch for h5utils version 1.12.1 (http://ab-initio.mit.edu/wiki/index.php/H5utils), that fixed the compilation bug with libpng:
gcc -DHAVE_CONFIG_H -I.     -g -O2 -MT writepng.o -MD -MP -MF .deps/writepng.Tpo -c -o writepng.o writepng.c
In file included from /usr/include/pngconf.h:50:0,
                 from /usr/include/png.h:371,
                 from writepng.c:28:
writepng.c: In function ‘writepng’:
writepng.c:312:24: error: dereferencing pointer to incomplete type ‘png_struct {aka struct png_struct_def}’
      if (setjmp(png_ptr->jmpbuf)) {
                        ^
writepng.c:437:19: error: dereferencing pointer to incomplete type ‘png_info {aka struct png_info_def}’
      free(info_ptr->palette);


apply the patch with patch -p0 -i hdf5_h5utils_libpng_patch

