# $Id: GNUmakefile,v 1.11 2004/12/08 21:20:43 marcel Exp $


OBJC_RUNTIME_LIB=ng

#include $(GNUSTEP_MAKEFILES)/common.make

FRAMEWORK_NAME = ObjectiveHTTPD

GNUSTEP_LOCAL_ADDITIONAL_MAKEFILES=base.make
GNUSTEP_BUILD_DIR = ~/Build/ObjectiveHTTPD

include $(GNUSTEP_MAKEFILES)/common.make


LIBRARY_NAME = libObjectiveHTTPD
CC = clang


OBJCFLAGS += -Wno-import -fobjc-runtime=gnustep


ObjectiveHTTPD_HEADER_FILES = \


ObjectiveHTTPD_HEADER_FILES_INSTALL_DIR = /ObjectiveHTTPD


libObjectiveHTTPD_OBJC_FILES = \
    MPWHTTPServer.m \
    MPWSchemeHttpServer.m \
    MPWPOSTProcessor.m \


libObjectiveHTTPD_C_FILES = \




LIBRARIES_DEPEND_UPON +=  -lMPWFoundation -lgnustep-base

LDFLAGS += -L /home/gnustep/Build/MPWFoundation/obj -L /home/gnustep/Build/ObjectiveSmalltalk/obj


libObjectiveHTTPD_INCLUDE_DIRS += -I.headers -I. -I../MPWFoundation/.headers/  -I../ObjectiveSmalltalk/.headers/

-include GNUmakefile.preamble
include $(GNUSTEP_MAKEFILES)/library.make
-include GNUmakefile.postamble

before-all ::
	
#	@$(MKDIRS) $(libMPWFoundation_HEADER_FILES_DIR)
#	cp *.h $(libMPWFoundation_HEADER_FILES_DIR)
#	cp Collections.subproj/*.h $(libMPWFoundation_HEADER_FILES_DIR)
#	cp Comm.subproj/*.h        $(libMPWFoundation_HEADER_FILES_DIR)
#	cp Streams.subproj/*.h     $(libMPWFoundation_HEADER_FILES_DIR)
#	cp Threading.subproj/*.h   $(libMPWFoundation_HEADER_FILES_DIR)

after-clean ::
	rm -rf .headers


test    : libObjectiveHTTPD tester
	LD_LIBRARY_PATH=/home/gnustep/GNUstep/Library/Libraries:/usr/local/lib:/home/gnustep/Build/MPWFoundation/obj/:/home/gnustep/Build/ObjectiveSmalltalk/obj/  ./TestObjectiveSmalltalk/testobjectivesmalltalk

tester  :
	clang -fobjc-runtime=gnustep-1.9 -I../MPWFoundation/.headers/ -I.headers -o testobjectivehttpd testobjectivehttpd.m -L/home/gnustep/Build/MPWFoundation/obj -L/home/gnustep/Build/ObjectiveHTTPD/obj -lObjectiveHTTPD -lMPWFoundation -lgnustep-base -L/usr/local/lib/ -lobjc
