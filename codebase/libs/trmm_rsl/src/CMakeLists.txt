###############################################################
#
# CMakeLists.txt - auto generated from Makefile
#
# library name: trmm_rsl
#
# written by script createCMakeLists.lib.py
#
# dir: lrose-core/codebase/libs/trmm_rsl/src
###############################################################

project (libtrmm_rsl)

# include directories

include_directories (./include)
include_directories (../../FiltAlg/src/include)
include_directories (../../FiltAlgVirtVol/src/include)
include_directories (../../Fmq/src/include)
include_directories (../../Mdv/src/include)
include_directories (../../Ncxx/src/include)
include_directories (../../Radx/src/include)
include_directories (../../Refract/src/include)
include_directories (../../Solo/src/include)
include_directories (../../Spdb/src/include)
include_directories (../../advect/src/include)
include_directories (../../cidd/src/include)
include_directories (../../contour/src/include)
include_directories (../../dataport/src/include)
include_directories (../../didss/src/include)
include_directories (../../dsdata/src/include)
include_directories (../../dsserver/src/include)
include_directories (../../euclid/src/include)
include_directories (../../grib/src/include)
include_directories (../../grib2/src/include)
include_directories (../../hydro/src/include)
include_directories (../../kd/src/include)
include_directories (../../physics/src/include)
include_directories (../../qtplot/src/include)
include_directories (../../radar/src/include)
include_directories (../../rapformats/src/include)
include_directories (../../rapmath/src/include)
include_directories (../../rapplot/src/include)
include_directories (../../shapelib/src/include)
include_directories (../../tdrp/src/include)
include_directories (../../titan/src/include)
include_directories (../../toolsa/src/include)
include_directories (../../trmm_rsl/src/include)
include_directories (${CMAKE_INSTALL_PREFIX}/include)
if (DEFINED MAMBA_BUILD)
# MAMBA builds ignore system libs, use mamba libs
  include_directories (${MAMBA_INCLUDE_PATH})
else()
  if (DEFINED netCDF_INSTALL_PREFIX)
    include_directories (${netCDF_INSTALL_PREFIX}/include)
  endif()
  if (DEFINED HDF5_C_INCLUDE_DIR)
    include_directories (${HDF5_C_INCLUDE_DIR})
  endif()
  if(IS_DIRECTORY /usr/include/hdf5/serial)
    include_directories (/usr/include/hdf5/serial)
  endif()
  if(IS_DIRECTORY /usr/local/include)
    include_directories (/usr/local/include)
  endif()
  # NOTE: cannot add /usr/include using include_directories()
  #add_compile_options(-I/usr/include)
  
endif(DEFINED MAMBA_BUILD)
# source files

set (SRCS
      ./rsl/africa.c
      ./rsl/africa_to_radar.c
      ./rsl/anyformat_to_radar.c
      ./rsl/cappi.c
      ./rsl/carpi.c
      ./rsl/cube.c
      ./rsl/dorade.c
      ./rsl/dorade_print.c
      ./rsl/dorade_to_radar.c
      ./rsl/edge_to_radar.c
      ./rsl/endian.c
      ./rsl/farea.c
      ./rsl/fix_headers.c
      ./rsl/fraction.c
      ./rsl/get_win.c
      ./rsl/gts.c
      ./rsl/gzip.c
      ./rsl/hdf_to_radar.c
      ./rsl/histogram.c
      ./rsl/image_gen.c
      ./rsl/interp.c
      ./rsl/lassen_to_radar.c
      ./rsl/mcgill.c
      ./rsl/mcgill_to_radar.c
      ./rsl/nsig.c
      ./rsl/nsig2_to_radar.c
      ./rsl/prune.c
      ./rsl/radar.c
      ./rsl/radar_to_hdf_1.c
      ./rsl/radar_to_hdf_2.c
      ./rsl/radar_to_uf.c
      ./rsl/radtec.c
      ./rsl/radtec_to_radar.c
      ./rsl/rainbow.c
      ./rsl/rainbow_to_radar.c
      ./rsl/range.c
      ./rsl/rapic-lex.c
      ./rsl/rapic.c
      ./rsl/rapic_routines.c
      ./rsl/rapic_to_radar.c
      ./rsl/ray_indexes.c
      ./rsl/read_write.c
      ./rsl/reverse.c
      ./rsl/sort_rays.c
      ./rsl/toga.c
      ./rsl/toga_to_radar.c
      ./rsl/toolkit_memory_mgt.c
      ./rsl/uf_to_radar.c
      ./rsl/volume.c
      ./rsl/wsr88d.c
      ./rsl/wsr88d_get_site.c
      ./rsl/wsr88d_m31.c
      ./rsl/wsr88d_to_radar.c
   )

if(APPLE)
# for apple, force static build
  add_library (trmm_rsl STATIC ${SRCS})
else(APPLE)
# build shared library
  add_library (trmm_rsl SHARED ${SRCS})
endif(APPLE)

# install

INSTALL(TARGETS trmm_rsl
        DESTINATION ${CMAKE_INSTALL_PREFIX}/lib
       )
INSTALL(DIRECTORY include/trmm_rsl
        DESTINATION ${CMAKE_INSTALL_PREFIX}/include
       )

