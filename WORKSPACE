load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_apple",
    sha256 = "b770067261140c0a3c5f84f900e3d6059d7036d7954da243016acfdb17216799",
    url = "https://github.com/bazelbuild/rules_apple/releases/download/3.11.2/rules_apple.3.11.2.tar.gz",
)

http_archive(
    name = "build_bazel_rules_swift",
    sha256 = "5563621eb523f35373eb06a744f00a4c1d631e9b9af256754cd3ff152f888940",
    url = "https://github.com/bazelbuild/rules_swift/releases/download/2.2.2/rules_swift.2.2.2.tar.gz",
)

load(
    "@build_bazel_rules_apple//apple:repositories.bzl",
    "apple_rules_dependencies",
)

apple_rules_dependencies()

load(
    "@build_bazel_rules_swift//swift:repositories.bzl",
    "swift_rules_dependencies",
)

swift_rules_dependencies()

load(
    "@build_bazel_rules_swift//swift:extras.bzl",
    "swift_rules_extra_dependencies",
)

swift_rules_extra_dependencies()

load(
    "@build_bazel_apple_support//lib:repositories.bzl",
    "apple_support_dependencies",
)

apple_support_dependencies()