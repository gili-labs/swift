cmake_minimum_required(VERSION 3.4.3)
include("../../../../cmake/modules/StandaloneOverlay.cmake")

add_swift_library(swiftAppKit ${SWIFT_SDK_OVERLAY_LIBRARY_BUILD_TYPES} IS_SDK_OVERLAY
  AppKit.swift
  AppKit_FoundationExtensions.swift
  NSError.swift
  NSGraphics.swift
  NSOpenGL.swift

  SWIFT_COMPILE_FLAGS ${SWIFT_RUNTIME_SWIFT_COMPILE_FLAGS} -swift-version 4 
  LINK_FLAGS "${SWIFT_RUNTIME_SWIFT_LINK_FLAGS}"
  TARGET_SDKS OSX
  SWIFT_MODULE_DEPENDS_OSX Darwin CoreData CoreGraphics CoreImage Dispatch Foundation IOKit ObjectiveC QuartzCore XPC # auto-updated
  FRAMEWORK_DEPENDS AppKit

  DEPLOYMENT_VERSION_OSX ${SWIFTLIB_DEPLOYMENT_VERSION_APPKIT_OSX}
)
