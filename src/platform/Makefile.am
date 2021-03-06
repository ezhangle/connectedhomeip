#
#    Copyright (c) 2020 Project CHIP Authors
#    Copyright (c) 2014-2018 Nest Labs, Inc.
#    Copyright (c) 2018 Google LLC
#
#    Licensed under the Apache License, Version 2.0 (the "License");
#    you may not use this file except in compliance with the License.
#    You may obtain a copy of the License at
#
#        http://www.apache.org/licenses/LICENSE-2.0
#
#    Unless required by applicable law or agreed to in writing, software
#    distributed under the License is distributed on an "AS IS" BASIS,
#    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
#    See the License for the specific language governing permissions and
#    limitations under the License.
#

#
#    Description:
#      This file is the GNU automake template for the CHIP Device Layer
#      library.

include $(abs_top_nlbuild_autotools_dir)/automake/pre.am

SUBDIRS                                 = \
    $(NULL)

EXTRA_DIST                              = \
    $(NULL)

#
# Local headers to build against and distribute but not to install
# since they are not part of the CHIP SDK public API.
#
noinst_HEADERS                          = \
    @top_srcdir@/src/include/platform/ConfigurationManager.h \
    @top_srcdir@/src/include/platform/ConnectivityManager.h \
    @top_srcdir@/src/include/platform/SoftwareUpdateManagerImpl.h \
    @top_srcdir@/src/include/platform/GeneralUtils.h \
    @top_srcdir@/src/include/platform/PlatformManager.h \
    @top_srcdir@/src/include/platform/PersistedStorage.h \
    @top_srcdir@/src/include/platform/SoftwareUpdateManager.h \
    @top_srcdir@/src/include/platform/TimeSyncManager.h \
    @top_srcdir@/src/include/platform/CHIPDeviceConfig.h \
    @top_srcdir@/src/include/platform/CHIPDeviceError.h \
    @top_srcdir@/src/include/platform/CHIPDeviceEvent.h \
    @top_srcdir@/src/include/platform/CHIPDeviceLayer.h \
    @top_srcdir@/src/include/platform/internal/BLEManager.h \
    @top_srcdir@/src/include/platform/internal/EventLogging.h \
    @top_srcdir@/src/include/platform/internal/GenericConfigurationManagerImpl.h \
    @top_srcdir@/src/include/platform/internal/GenericConfigurationManagerImpl.ipp \
    @top_srcdir@/src/include/platform/internal/GenericPlatformManagerImpl.h \
    @top_srcdir@/src/include/platform/internal/GenericPlatformManagerImpl.ipp \
    @top_srcdir@/src/include/platform/internal/GenericPlatformManagerImpl_POSIX.h \
    @top_srcdir@/src/include/platform/internal/GenericPlatformManagerImpl_POSIX.ipp \
    @top_srcdir@/src/include/platform/internal/GenericSoftwareUpdateManagerImpl.h \
    @top_srcdir@/src/include/platform/internal/GenericSoftwareUpdateManagerImpl.ipp \
    @top_srcdir@/src/include/platform/internal/GenericPlatformManagerImpl_FreeRTOS.h \
    @top_srcdir@/src/include/platform/internal/GenericPlatformManagerImpl_FreeRTOS.ipp \
    @top_srcdir@/src/include/platform/internal/CHIPDeviceLayerInternal.h \
    @top_srcdir@/src/platform/nRF5/ConnectivityManagerImpl.h \
    @top_srcdir@/src/platform/nRF5/nRF5Config.h \
    @top_srcdir@/src/platform/nRF5/CHIPDevicePlatformConfig.h \
    @top_srcdir@/src/platform/nRF5/CHIPDevicePlatformEvent.h \
    @top_srcdir@/src/platform/nRF5/PlatformManagerImpl.h \
    @top_srcdir@/src/platform/EFR32/CHIPDevicePlatformConfig.h \
    @top_srcdir@/src/platform/EFR32/GroupKeyStoreImpl.h \
    @top_srcdir@/src/platform/EFR32/efr32-chip-mbedtls-config.h \
    @top_srcdir@/src/platform/EFR32/EFR32Config.h \
    @top_srcdir@/src/platform/EFR32/gatt_db.h \
    @top_srcdir@/src/platform/EFR32/freertos_bluetooth.h \
    @top_srcdir@/src/platform/EFR32/ConnectivityManagerImpl.h \
    @top_srcdir@/src/platform/EFR32/BLEManagerImpl.h \
    @top_srcdir@/src/platform/EFR32/ConfigurationManagerImpl.h \
    @top_srcdir@/src/platform/EFR32/PlatformManagerImpl.h \
    @top_srcdir@/src/platform/EFR32/SoftwareUpdateManagerImpl.h \
    @top_srcdir@/src/platform/EFR32/CHIPDevicePlatformEvent.h \
    @top_srcdir@/src/platform/EFR32/NetworkProvisioningServerImpl.h \
    @top_srcdir@/src/platform/ESP32/CHIPDevicePlatformConfig.h \
    @top_srcdir@/src/platform/ESP32/ConnectivityManagerImpl.h \
    @top_srcdir@/src/platform/ESP32/BLEManagerImpl.h \
    @top_srcdir@/src/platform/ESP32/ConfigurationManagerImpl.h \
    @top_srcdir@/src/platform/ESP32/PlatformManagerImpl.h \
    @top_srcdir@/src/platform/ESP32/SoftwareUpdateManagerImpl.h \
    @top_srcdir@/src/platform/ESP32/CHIPDevicePlatformEvent.h \
    @top_srcdir@/src/platform/ESP32/NetworkProvisioningServerImpl.h \
    @top_srcdir@/src/platform/ESP32/ESP32Utils.h \
    @top_srcdir@/src/platform/ESP32/ESP32Config.h \
    @top_srcdir@/src/platform/Linux/CHIPDevicePlatformConfig.h \
    @top_srcdir@/src/platform/Linux/CHIPDevicePlatformEvent.h \
    @top_srcdir@/src/platform/Linux/ConfigurationManagerImpl.h \
    @top_srcdir@/src/platform/Linux/PlatformManagerImpl.h \
    $(NULL)

if CONFIG_DEVICE_LAYER

lib_LIBRARIES                           = libDeviceLayer.a

libDeviceLayer_a_CPPFLAGS               = \
    -I$(top_srcdir)/src/include           \
    -I$(top_srcdir)/src/lib               \
    -I$(top_srcdir)/src/system            \
    -I$(top_srcdir)/src                   \
    $(NLASSERT_CPPFLAGS)                  \
    $(NLIO_CPPFLAGS)                      \
    $(LWIP_CPPFLAGS)                      \
    $(SOCKETS_CPPFLAGS)                   \
    $(NULL)

libDeviceLayer_a_SOURCES                = \
    PersistedStorage.cpp                  \
    SystemEventSupport.cpp                \
    SystemTimerSupport.cpp                \
    GeneralUtils.cpp                      \
    Globals.cpp                           \
    $(NULL)

if CHIP_ENABLE_OPENTHREAD
libDeviceLayer_a_SOURCES               += \
    OpenThread/OpenThreadUtils.cpp        \
    $(NULL)
endif

if CHIP_DEVICE_LAYER_TARGET_LINUX

SUBDIRS                                += tests

libDeviceLayer_a_CPPFLAGS              += \
    $(INIPP_CPPFLAGS)                     \
    $(NULL)

libDeviceLayer_a_SOURCES               += \
    Linux/BLEManagerImpl.cpp              \
    Linux/ConfigurationManagerImpl.cpp    \
    Linux/ConnectivityManagerImpl.cpp     \
    Linux/Logging.cpp                     \
    Linux/PosixConfig.cpp                 \
    Linux/CHIPLinuxStorage.cpp            \
    Linux/CHIPLinuxStorageIni.cpp         \
    Linux/PlatformManagerImpl.cpp         \
    Linux/SystemTimeSupport.cpp           \
    $(NULL)

endif # CHIP_DEVICE_LAYER_TARGET_LINUX

if CHIP_DEVICE_LAYER_TARGET_NRF5

libDeviceLayer_a_SOURCES               +=       \
    nRF5/BLEManagerImpl.cpp                     \
    nRF5/PlatformManagerImpl.cpp                \
    nRF5/ConfigurationManagerImpl.cpp           \
    nRF5/ConnectivityManagerImpl.cpp            \
    nRF5/nRF5Config.cpp                         \
    nRF5/nRF5Utils.cpp                          \
    nRF5/Logging.cpp                            \
    FreeRTOS/SystemTimeSupport.cpp              \
    $(NULL)

if CHIP_ENABLE_OPENTHREAD
libDeviceLayer_a_SOURCES               +=       \
    nRF5/ThreadStackManagerImpl.cpp             \
    $(NULL)
endif

endif # CHIP_DEVICE_LAYER_TARGET_NRF5

if CHIP_DEVICE_LAYER_TARGET_EFR32

libDeviceLayer_a_SOURCES               +=       \
    EFR32/BLEManagerImpl.cpp                    \
    EFR32/freertos_bluetooth.c                  \
    EFR32/gatt_db.c                             \
    EFR32/PlatformManagerImpl.cpp               \
    EFR32/ConnectivityManagerImpl.cpp           \
    EFR32/EFR32Config.cpp                       \
    EFR32/Logging.cpp                           \
    FreeRTOS/SystemTimeSupport.cpp              \
    $(NULL)

endif # CHIP_DEVICE_LAYER_TARGET_EFR32

if CHIP_DEVICE_LAYER_TARGET_ESP32

libDeviceLayer_a_SOURCES               +=       \
    ESP32/BLEManagerImpl.cpp                    \
    ESP32/ConfigurationManagerImpl.cpp          \
    ESP32/PlatformManagerImpl.cpp               \
    ESP32/ConnectivityManagerImpl.cpp           \
    ESP32/ESP32Config.cpp                       \
    ESP32/ESP32Utils.cpp                        \
    ESP32/Logging.cpp                           \
    ESP32/SystemTimeSupport.cpp                 \
    ESP32/LwIPCoreLock.cpp                      \
    FreeRTOS/SystemTimeSupport.cpp              \
    $(NULL)

endif # CHIP_DEVICE_LAYER_TARGET_ESP32

endif # CONFIG_DEVICE_LAYER

include $(abs_top_nlbuild_autotools_dir)/automake/post.am
