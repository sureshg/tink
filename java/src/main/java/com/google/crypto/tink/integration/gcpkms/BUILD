licenses(["notice"])  # Apache 2.0

package(default_visibility = ["//tools/build_defs:internal_pkg"])

load("//tools/build_defs:javac.bzl", "JAVACOPTS")

# public interfaces

java_library(
    name = "gcpkms",
    srcs = [
        "GcpKmsAead.java",
        "GcpKmsClient.java",
    ],
    javacopts = JAVACOPTS,
    plugins = [
        ":auto_service_plugin",
    ],
    deps = [
        "//java/src/main/java/com/google/crypto/tink",
        "//java/src/main/java/com/google/crypto/tink/subtle",
        "@com_google_api_client",
        "@com_google_apis_google_api_services_cloudkms",
        "@com_google_auto_service",
        "@com_google_http_client",
        "@com_google_http_client_jackson2",
        "@com_google_oauth_client",
    ],
)

java_plugin(
    name = "auto_service_plugin",
    processor_class = "com.google.auto.service.processor.AutoServiceProcessor",
    deps = [
        "@com_google_auto_common",
        "@com_google_auto_service",
        "@com_google_guava",
    ],
)
