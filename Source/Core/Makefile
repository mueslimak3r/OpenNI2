include ../../ThirdParty/PSCommon/BuildSystem/CommonDefs.mak

BIN_DIR = ../../Bin

INC_DIRS = \
	../../Include \
	../../ThirdParty/PSCommon/XnLib/Include \
	../Drivers/OniFile/Formats \
	../Drivers/OniFile \
	../../ThirdParty/LibJPEG

SRC_FILES = \
	*.cpp \
	../Drivers/OniFile/Formats/XnCodec.cpp \
	../Drivers/OniFile/Formats/XnStreamCompression.cpp \
	../../ThirdParty/LibJPEG/*.c \

# OSX-M1
ifeq ("$(OSTYPE)","Darwin")
	INC_DIRS += \
		/usr/local/include \
		/opt/homebrew/Cellar/libusb/1.0.27/include/ \
		/opt/local/include
	LIB_DIRS += \
		/usr/local/lib \
		/opt/homebrew/Cellar/libusb/1.0.27/lib \
		/opt/local/lib
	LDFLAGS += \
		-framework CoreFoundation \
		-framework IOKit
endif

LIB_NAME = OpenNI2

LIB_DIRS = ../../ThirdParty/PSCommon/XnLib/Bin/$(PLATFORM)-$(CFG)
USED_LIBS = XnLib dl pthread
ifneq ("$(OSTYPE)","Darwin")
        USED_LIBS += rt  
endif

DEFINES += OPENNI2_EXPORT

CFLAGS += -Wall

include ../../ThirdParty/PSCommon/BuildSystem/CommonCppMakefile
