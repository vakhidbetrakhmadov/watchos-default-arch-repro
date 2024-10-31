load("@build_bazel_rules_swift//swift:swift.bzl", "swift_library")
load("@build_bazel_rules_apple//apple:ios.bzl", "ios_application")
load("@build_bazel_rules_apple//apple:watchos.bzl", "watchos_application", "watchos_extension")
load("@build_bazel_rules_apple//apple:versioning.bzl", "apple_bundle_version")

swift_library(
    name = "Sources",
    module_name = "Sources",
    srcs = [
        "Sources/BazelApp.swift",
    ],
)

filegroup(
    name = "PhoneAppIcon.xcassets",
    srcs = glob(["Resources/PhoneAppIcon.xcassets/**"]),
)

ios_application(
    name = "HelloWorld",
    app_icons = [":PhoneAppIcon.xcassets"],
    bundle_id = "com.example.hello-world",
    families = [
        "iphone",
        "ipad",
    ],
    infoplists = ["Resources/Info.plist"],
    minimum_os_version = "14.0",
    deps = [":Sources"],
    version = ":HelloWorldVersion",
    watch_application = ":HelloWorld-WatchApplication",
)

apple_bundle_version(
    name = "HelloWorldVersion",
    build_version = "1.0",
)

filegroup(
    name = "WatchAppIcon.xcassets",
    srcs = glob(["WatchResources/WatchAppIcon.xcassets/**"]),
)

watchos_application(
    name = "HelloWorld-WatchApplication",
    app_icons = [":WatchAppIcon.xcassets"],
    bundle_id = "com.example.hello-world.watch",
    extensions = [":HelloWorld-WatchExtension"],
    infoplists = ["WatchResources/WatchApp-Info.plist"],
    minimum_os_version = "6.0",
    storyboards = ["WatchResources/Interface.storyboard"],
    version = ":HelloWorldVersion",
)

watchos_extension(
    name = "HelloWorld-WatchExtension",
    bundle_id = "com.example.hello-world.watch.extension",
    infoplists = ["WatchResources/WatchExt-Info.plist"],
    minimum_os_version = "6.0",
    deps = [":WatchSources"],
    version = ":HelloWorldVersion",
)

objc_library(
    name = "WatchSources",
    srcs = [
        "WatchSources/ExtensionDelegate.h",
        "WatchSources/ExtensionDelegate.m",
    ],
    deps = [":WatchSharedSources"],
)

objc_library(
    name = "WatchSharedSources",
    srcs = [
        "WatchSharedSources/InterfaceController.h",
        "WatchSharedSources/InterfaceController.m",
    ],
    sdk_frameworks = [
        "WatchConnectivity",
        "WatchKit",
    ],
)