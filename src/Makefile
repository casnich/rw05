#########################################
#    Makefile for Radware on Mac OS X
#    What you need:    Xcode; X11 development libraries (X11-SDK)
#    Optional development libraries: readline; lesstif; gtk2
########################################

#   make all                to make all programs
#   make install            to install, if all goes well
#   make clean              to clean up this dir
#   make very-clean         to clean up this and all subdirectories,
#                               leaving only the source code

#------------------------------------------------------------------------
#    CHANGE  these next two lines if X11 and/or Motif are installed elsewhere 

     X_WIN_TOP  = /usr/X11R6
     MOTIF_TOP  = /opt/local

#------------------------------------------------------------------------
#    CHANGE  the next 3 lines to suit your installation preferences

    INSTALL_DIR = ${HOME}/rw_current
        INSTALL = /usr/bin/install -m 0644 -o home -g users
    INSTALL_BIN = /usr/bin/install -m 0755 -o home -g users

#------------------------------------------------------------------------

             CC = gcc
             FC = $(CC)
         CFLAGS = -O2 -Wall -I$(MOTIF_TOP)/include -DHAVE_GNU_READLINE

         RANLIB = ranlib
             AR = ar rv
             RM = -rm -f
         RM_CMD = $(RM) *.o core* *[~%] *.trace

           LIBS = -lX11 -lm -lreadline -lncurses
     MOTIF_LIBS = -lXm -lMrm -lXt -lXext -lXp
   STATIC_MOTIF = -lXm -lMrm -lXpm -lXt -lSM -lICE -lXext -lXp

# -----------------------------------------------------------------------
#  UNCOMMENT and CHANGE (if necessary)  the line defining HISLIBS
#  if you have orphlib.a on your system, and you want to be able to read .his files.
#  UNCOMMENT the line defining FC as gcc if orphlib was compiled using gcc
#        HISLIBS = /home/radfordd/upak/orphlib.a
#             FC = g77

#------------------------------------------------------------------------

      LIB_PATHS = -L. -L$(X_WIN_TOP)/lib
   XM_LIB_PATHS = -L$(MOTIF_TOP)/lib
           GTK2 = TRUE

 SUB_MAKE_FLAGS = "CC = ${CC}" "CFLAGS = ${CFLAGS}" \
                  "RANLIB = ${RANLIB}" "HISLIBS = ${HISLIBS}" "GTK2 = ${GTK2}"

##############  Methods  ##################

include Makefile.common
include Makefile.install_ucb
