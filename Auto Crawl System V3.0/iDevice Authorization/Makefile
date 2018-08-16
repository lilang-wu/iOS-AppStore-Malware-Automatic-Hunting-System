GO_EASY_ON_ME=1
THEOS_DEVICE_IP = $(DEVICE_IP)#10.64.82.103
ARCHS = arm64
#TARGET = iphone:latest:9.3

include $(THEOS)/makefiles/common.mk

TWEAK_NAME = appstoresignin
appstoresignin_FILES = Tweak.xm
#SetupTest_FRAMEWORK = IOKit #PTFakeTouch
appstoresignin_OBJCFLAGS= -IStoreServiceHeaders -IProtocols

#appstoresignin_LDFLAGS += staticT.a
#SetupTest_LDFLAGS += -lz.1 -lstdc++ -lxml2 -lz -licucore -lsqlite3 -lc++
appstoresignin_LDFLAGS += StoreServices.framework/StoreServices.tbd

include $(THEOS_MAKE_PATH)/tweak.mk

after-install::
	install.exec "killall -9 SpringBoard"