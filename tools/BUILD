load(
    "@bazel_tools//tools/jdk:default_java_toolchain.bzl",
    "default_java_toolchain",
)
load("@rules_java//java:defs.bzl", "java_package_configuration")

default_java_toolchain(
    name = "error_prone_warnings_toolchain_java11",
    package_configuration = [
        ":error_prone",
    ],
    source_version = "11",
    target_version = "11",
    visibility = ["//visibility:public"],
)

default_java_toolchain(
    name = "error_prone_warnings_toolchain_java17",
    configuration = dict(),
    java_runtime = "@bazel_tools//tools/jdk:remotejdk_17",
    package_configuration = [
        ":error_prone",
    ],
    source_version = "17",
    target_version = "17",
    visibility = ["//visibility:public"],
)

# Error Prone errors enabled by default; see ../.bazelrc for how this is
# enabled. This warnings list is originally based on:
# https://github.com/bazelbuild/BUILD_file_generator/blob/master/tools/bazel_defs/java.bzl
# However, feel free to add any additional errors. Thus far they have all been pretty useful.
java_package_configuration(
    name = "error_prone",
    javacopts = [
        "-XepDisableWarningsInGeneratedCode",
        "-Xep:MissingCasesInEnumSwitch:ERROR",
        "-Xep:ReferenceEquality:WARN",
        "-Xep:StringEquality:WARN",
        "-Xep:WildcardImport:ERROR",
        "-Xep:AmbiguousMethodReference:ERROR",
        "-Xep:BadAnnotationImplementation:ERROR",
        "-Xep:BadComparable:WARN",
        "-Xep:BoxedPrimitiveConstructor:ERROR",
        "-Xep:CannotMockFinalClass:ERROR",
        "-Xep:ClassCanBeStatic:ERROR",
        "-Xep:ClassNewInstance:ERROR",
        "-Xep:DefaultCharset:WARN",
        "-Xep:DoubleCheckedLocking:ERROR",
        "-Xep:ElementsCountedInLoop:ERROR",
        "-Xep:EqualsHashCode:ERROR",
        "-Xep:EqualsIncompatibleType:ERROR",
        "-Xep:Finally:WARN",
        "-Xep:FloatingPointLiteralPrecision:ERROR",
        "-Xep:FragmentInjection:ERROR",
        "-Xep:FragmentNotInstantiable:ERROR",
        "-Xep:FunctionalInterfaceClash:ERROR",
        "-Xep:FutureReturnValueIgnored:WARN",
        "-Xep:GetClassOnEnum:ERROR",
        "-Xep:ImmutableAnnotationChecker:ERROR",
        "-Xep:ImmutableEnumChecker:ERROR",
        "-Xep:IncompatibleModifiers:ERROR",
        "-Xep:InjectOnConstructorOfAbstractClass:ERROR",
        "-Xep:InputStreamSlowMultibyteRead:ERROR",
        "-Xep:IterableAndIterator:ERROR",
        "-Xep:JUnit3FloatingPointComparisonWithoutDelta:ERROR",
        "-Xep:JUnitAmbiguousTestClass:ERROR",
        "-Xep:LiteralClassName:ERROR",
        "-Xep:MissingFail:ERROR",
        "-Xep:MissingOverride:ERROR",
        "-Xep:MutableConstantField:ERROR",
        "-Xep:NarrowingCompoundAssignment:ERROR",
        "-Xep:NonAtomicVolatileUpdate:ERROR",
        "-Xep:NonOverridingEquals:ERROR",
        "-Xep:NullableConstructor:ERROR",
        "-Xep:NullablePrimitive:ERROR",
        "-Xep:NullableVoid:ERROR",
        "-Xep:OperatorPrecedence:ERROR",
        "-Xep:OverridesGuiceInjectableMethod:ERROR",
        "-Xep:PreconditionsInvalidPlaceholder:ERROR",
        "-Xep:ProtoFieldPreconditionsCheckNotNull:ERROR",
        "-Xep:ProtocolBufferOrdinal:ERROR",
        "-Xep:RequiredModifiers:ERROR",
        "-Xep:ShortCircuitBoolean:ERROR",
        "-Xep:SimpleDateFormatConstant:ERROR",
        "-Xep:StaticGuardedByInstance:ERROR",
        "-Xep:SynchronizeOnNonFinalField:ERROR",
        "-Xep:TruthConstantAsserts:ERROR",
        "-Xep:TypeParameterShadowing:ERROR",
        "-Xep:TypeParameterUnusedInFormals:WARN",
        "-Xep:URLEqualsHashCode:ERROR",
        "-Xep:UnusedException:WARN",
        "-Xep:UnsynchronizedOverridesSynchronized:ERROR",
        "-Xep:WaitNotInLoop:ERROR",
    ],
    packages = ["error_prone_packages"],
)

package_group(
    name = "error_prone_packages",
    packages = [
        "//org.eclipse.jgit.ant.test/...",
        "//org.eclipse.jgit.ant/...",
        "//org.eclipse.jgit.archive/...",
        "//org.eclipse.jgit.gpg.bc.test/...",
        "//org.eclipse.jgit.gpg.bc/...",
        "//org.eclipse.jgit.http.apache/...",
        "//org.eclipse.jgit.http.server/...",
        "//org.eclipse.jgit.http.test/...",
        "//org.eclipse.jgit.junit.ssh/...",
        "//org.eclipse.jgit.junit/...",
        "//org.eclipse.jgit.junit/http/...",
        "//org.eclipse.jgit.lfs.server.test/...",
        "//org.eclipse.jgit.lfs.server/...",
        "//org.eclipse.jgit.lfs.test/...",
        "//org.eclipse.jgit.lfs/...",
        "//org.eclipse.jgit.pgm.test/...",
        "//org.eclipse.jgit.pgm/...",
        "//org.eclipse.jgit.ssh.apache.agent/...",
        "//org.eclipse.jgit.ssh.apache.test/...",
        "//org.eclipse.jgit.ssh.apache/...",
        "//org.eclipse.jgit.ssh.jsch.test/...",
        "//org.eclipse.jgit.ssh.jsch/...",
        "//org.eclipse.jgit.test/...",
        "//org.eclipse.jgit.ui/...",
        "//org.eclipse.jgit/...",
    ],
)
