# __BEGIN_LICENSE__
#  Copyright (c) 2006-2013, United States Government as represented by the
#  Administrator of the National Aeronautics and Space Administration. All
#  rights reserved.
#
#  The NASA Vision Workbench is licensed under the Apache License,
#  Version 2.0 (the "License"); you may not use this file except in
#  compliance with the License. You may obtain a copy of the License at
#  http://www.apache.org/licenses/LICENSE-2.0
#
#  Unless required by applicable law or agreed to in writing, software
#  distributed under the License is distributed on an "AS IS" BASIS,
#  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
#  See the License for the specific language governing permissions and
#  limitations under the License.
# __END_LICENSE__


########################################################################
# sources
########################################################################

# 'make clean' should get rid of any QT meta-object compiled files.
CLEANFILES = *.moc.cc

if ENABLE_EXCEPTIONS

noinst_HEADERS =                \
  MainWidget.h                  \
  ImageTileGenerator.h          \
  MainWindow.h                  \
  PlatefileTileGenerator.h      \
  TestPatternTileGenerator.h    \
  TextureCache.h                \
  TileGenerator.h               \
  Tree.h                        \
  WebTileGenerator.h            \
  Utils.h

vwv_SOURCES =                   \
  $(BUILT_SOURCES)              \
  MainWidget.cc                 \
  ImageTileGenerator.cc         \
  MainWindow.cc                 \
  TestPatternTileGenerator.cc   \
  TextureCache.cc               \
  TileGenerator.cc              \
  Utils.cc                      \
  vwv.cc

BUILT_SOURCES =                 \
  MainWidget.moc.cc             \
  MainWindow.moc.cc

vwv_LDADD    = @PKG_GUI_LIBS@ @PKG_CARTOGRAPHY_LIBS@

if MAKE_MODULE_PLATE
  vwv_LDADD += @PKG_PLATE_LIBS@
  vwv_SOURCES += PlatefileTileGenerator.cc \
                 WebTileGenerator.cc
  BUILT_SOURCES += WebTileGenerator.moc.cc
endif

bin_PROGRAMS = vwv

endif

########################################################################
# general
########################################################################

AM_CPPFLAGS = @VW_CPPFLAGS@ @PKG_GUI_CPPFLAGS@
if MAKE_MODULE_PLATE
  AM_CPPFLAGS += @PKG_PLATE_CPPFLAGS@
endif
AM_LDFLAGS = @VW_LDFLAGS@

includedir = $(prefix)/include/vw

include $(top_srcdir)/config/rules.mak
