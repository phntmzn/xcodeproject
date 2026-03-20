```python
from __future__ import annotations

import shutil
import subprocess
from pathlib import Path


ROOT = Path("/Users/macbookair/Desktop/mapgraph/Sources/SoundCloudGeoSeedApp")
OUT = Path("/Users/macbookair/Desktop/SoundCloudGeoSeed-macOS")

APP_DIR = OUT / "App"
SHARED_DIR = OUT / "Shared"
RES_DIR = OUT / "Resources"
PROJ_DIR = OUT / "SoundCloudGeoSeedMacOS.xcodeproj"
WORKSPACE_DIR = PROJ_DIR / "project.xcworkspace"

APP_SWIFT = """import SwiftUI

@main
struct SoundCloudGeoSeedMacOSApp: App {
    @State private var sharedViewModel = SoundCloudGeoSeedViewModel()

    var body: some Scene {
        WindowGroup("SoundCloud Geo Seed") {
            NativeMacAppView()
                .environment(sharedViewModel)
        }
        .defaultSize(width: 1360, height: 860)
        .windowResizability(.contentMinSize)
    }
}
"""

README_MD = """# SoundCloudGeoSeed macOS

This folder is a standalone macOS Xcode project export of the SoundCloud Geo Seed app.

Structure:
- `App/` contains the macOS app entry point.
- `Shared/` contains the app's shared Swift source files.
- `Resources/` contains bundled sample JSON files.
- `SoundCloudGeoSeedMacOS.xcodeproj/` is the Xcode project bundle.

Open `SoundCloudGeoSeedMacOS.xcodeproj` in Xcode.
"""

WORKSPACE_XML = """<?xml version="1.0" encoding="UTF-8"?>
<Workspace
   version = "1.0">
   <FileRef
      location = "self:">
   </FileRef>
</Workspace>
"""

PBXPROJ = r"""// !$*UTF8*$!
{
	archiveVersion = 1;
	classes = {
	};
	objectVersion = 77;
	objects = {

/* Begin PBXFileReference section */
		AB0000000000000000000001 /* SoundCloudGeoSeedMacOS.app */ = {isa = PBXFileReference; explicitFileType = wrapper.application; includeInIndex = 0; path = SoundCloudGeoSeedMacOS.app; sourceTree = BUILT_PRODUCTS_DIR; };
/* End PBXFileReference section */

/* Begin PBXFileSystemSynchronizedRootGroup section */
		AB0000000000000000000011 /* App */ = {
			isa = PBXFileSystemSynchronizedRootGroup;
			path = App;
			sourceTree = "<group>";
		};
		AB0000000000000000000012 /* Shared */ = {
			isa = PBXFileSystemSynchronizedRootGroup;
			path = Shared;
			sourceTree = "<group>";
		};
		AB0000000000000000000013 /* Resources */ = {
			isa = PBXFileSystemSynchronizedRootGroup;
			path = Resources;
			sourceTree = "<group>";
		};
/* End PBXFileSystemSynchronizedRootGroup section */

/* Begin PBXFrameworksBuildPhase section */
		AB0000000000000000000021 /* Frameworks */ = {
			isa = PBXFrameworksBuildPhase;
			buildActionMask = 2147483647;
			files = (
			);
			runOnlyForDeploymentPostprocessing = 0;
		};
/* End PBXFrameworksBuildPhase section */

/* Begin PBXGroup section */
		AB0000000000000000000031 = {
			isa = PBXGroup;
			children = (
				AB0000000000000000000011 /* App */,
				AB0000000000000000000012 /* Shared */,
				AB0000000000000000000013 /* Resources */,
				AB0000000000000000000032 /* Products */,
			);
			sourceTree = "<group>";
		};
		AB0000000000000000000032 /* Products */ = {
			isa = PBXGroup;
			children = (
				AB0000000000000000000001 /* SoundCloudGeoSeedMacOS.app */,
			);
			name = Products;
			sourceTree = "<group>";
		};
/* End PBXGroup section */

/* Begin PBXNativeTarget section */
		AB0000000000000000000041 /* SoundCloudGeoSeedMacOS */ = {
			isa = PBXNativeTarget;
			buildConfigurationList = AB0000000000000000000062 /* Build configuration list for PBXNativeTarget "SoundCloudGeoSeedMacOS" */;
			buildPhases = (
				AB0000000000000000000022 /* Sources */,
				AB0000000000000000000021 /* Frameworks */,
				AB0000000000000000000023 /* Resources */,
			);
			buildRules = (
			);
			dependencies = (
			);
			fileSystemSynchronizedGroups = (
				AB0000000000000000000011 /* App */,
				AB0000000000000000000012 /* Shared */,
				AB0000000000000000000013 /* Resources */,
			);
			name = SoundCloudGeoSeedMacOS;
			packageProductDependencies = (
			);
			productName = SoundCloudGeoSeedMacOS;
			productReference = AB0000000000000000000001 /* SoundCloudGeoSeedMacOS.app */;
			productType = "com.apple.product-type.application";
		};
/* End PBXNativeTarget section */

/* Begin PBXProject section */
		AB0000000000000000000051 /* Project object */ = {
			isa = PBXProject;
			attributes = {
				BuildIndependentTargetsInParallel = 1;
				LastSwiftUpdateCheck = 1620;
				LastUpgradeCheck = 1620;
				TargetAttributes = {
					AB0000000000000000000041 = {
						CreatedOnToolsVersion = 16.2;
						LastSwiftMigration = 1620;
					};
				};
			};
			buildConfigurationList = AB0000000000000000000061 /* Build configuration list for PBXProject "SoundCloudGeoSeedMacOS" */;
			developmentRegion = en;
			hasScannedForEncodings = 0;
			knownRegions = (
				en,
				Base,
			);
			mainGroup = AB0000000000000000000031;
			minimizedProjectReferenceProxies = 1;
			preferredProjectObjectVersion = 77;
			productRefGroup = AB0000000000000000000032 /* Products */;
			projectDirPath = "";
			projectRoot = "";
			targets = (
				AB0000000000000000000041 /* SoundCloudGeoSeedMacOS */,
			);
		};
/* End PBXProject section */

/* Begin PBXResourcesBuildPhase section */
		AB0000000000000000000023 /* Resources */ = {
			isa = PBXResourcesBuildPhase;
			buildActionMask = 2147483647;
			files = (
			);
			runOnlyForDeploymentPostprocessing = 0;
		};
/* End PBXResourcesBuildPhase section */

/* Begin PBXSourcesBuildPhase section */
		AB0000000000000000000022 /* Sources */ = {
			isa = PBXSourcesBuildPhase;
			buildActionMask = 2147483647;
			files = (
			);
			runOnlyForDeploymentPostprocessing = 0;
		};
/* End PBXSourcesBuildPhase section */

/* Begin XCBuildConfiguration section */
		AB0000000000000000000071 /* Debug */ = {
			isa = XCBuildConfiguration;
			buildSettings = {
				ALWAYS_SEARCH_USER_PATHS = NO;
				CLANG_ANALYZER_NONNULL = YES;
				CLANG_ANALYZER_NUMBER_OBJECT_CONVERSION = YES_AGGRESSIVE;
				CLANG_CXX_LANGUAGE_STANDARD = "gnu++20";
				CLANG_ENABLE_MODULES = YES;
				CLANG_ENABLE_OBJC_ARC = YES;
				CLANG_ENABLE_OBJC_WEAK = YES;
				CLANG_WARN_BLOCK_CAPTURE_AUTORELEASING = YES;
				CLANG_WARN_BOOL_CONVERSION = YES;
				CLANG_WARN_COMMA = YES;
				CLANG_WARN_CONSTANT_CONVERSION = YES;
				CLANG_WARN_DEPRECATED_OBJC_IMPLEMENTATIONS = YES;
				CLANG_WARN_DIRECT_OBJC_ISA_USAGE = YES_ERROR;
				CLANG_WARN_DOCUMENTATION_COMMENTS = YES;
				CLANG_WARN_EMPTY_BODY = YES;
				CLANG_WARN_ENUM_CONVERSION = YES;
				CLANG_WARN_INFINITE_RECURSION = YES;
				CLANG_WARN_INT_CONVERSION = YES;
				CLANG_WARN_NON_LITERAL_NULL_CONVERSION = YES;
				CLANG_WARN_OBJC_IMPLICIT_RETAIN_SELF = YES;
				CLANG_WARN_OBJC_LITERAL_CONVERSION = YES;
				CLANG_WARN_OBJC_ROOT_CLASS = YES_ERROR;
				CLANG_WARN_QUOTED_INCLUDE_IN_FRAMEWORK_HEADER = YES;
				CLANG_WARN_RANGE_LOOP_ANALYSIS = YES;
				CLANG_WARN_STRICT_PROTOTYPES = YES;
				CLANG_WARN_SUSPICIOUS_MOVE = YES;
				CLANG_WARN_UNGUARDED_AVAILABILITY = YES_AGGRESSIVE;
				CLANG_WARN_UNREACHABLE_CODE = YES;
				CLANG_WARN__DUPLICATE_METHOD_MATCH = YES;
				COPY_PHASE_STRIP = NO;
				DEBUG_INFORMATION_FORMAT = dwarf;
				ENABLE_STRICT_OBJC_MSGSEND = YES;
				ENABLE_TESTABILITY = YES;
				ENABLE_USER_SCRIPT_SANDBOXING = YES;
				GCC_C_LANGUAGE_STANDARD = gnu17;
				GCC_DYNAMIC_NO_PIC = NO;
				GCC_NO_COMMON_BLOCKS = YES;
				GCC_OPTIMIZATION_LEVEL = 0;
				GCC_PREPROCESSOR_DEFINITIONS = (
					"DEBUG=1",
					"$(inherited)",
				);
				GCC_WARN_64_TO_32_BIT_CONVERSION = YES;
				GCC_WARN_ABOUT_RETURN_TYPE = YES_ERROR;
				GCC_WARN_UNDECLARED_SELECTOR = YES;
				GCC_WARN_UNINITIALIZED_AUTOS = YES_AGGRESSIVE;
				GCC_WARN_UNUSED_FUNCTION = YES;
				GCC_WARN_UNUSED_VARIABLE = YES;
				LOCALIZATION_PREFERS_STRING_CATALOGS = YES;
				MTL_ENABLE_DEBUG_INFO = INCLUDE_SOURCE;
				MTL_FAST_MATH = YES;
				ONLY_ACTIVE_ARCH = YES;
				SDKROOT = macosx;
				SWIFT_ACTIVE_COMPILATION_CONDITIONS = "DEBUG $(inherited)";
				SWIFT_OPTIMIZATION_LEVEL = "-Onone";
			};
			name = Debug;
		};
		AB0000000000000000000072 /* Release */ = {
			isa = XCBuildConfiguration;
			buildSettings = {
				ALWAYS_SEARCH_USER_PATHS = NO;
				CLANG_ANALYZER_NONNULL = YES;
				CLANG_ANALYZER_NUMBER_OBJECT_CONVERSION = YES_AGGRESSIVE;
				CLANG_CXX_LANGUAGE_STANDARD = "gnu++20";
				CLANG_ENABLE_MODULES = YES;
				CLANG_ENABLE_OBJC_ARC = YES;
				CLANG_ENABLE_OBJC_WEAK = YES;
				CLANG_WARN_BLOCK_CAPTURE_AUTORELEASING = YES;
				CLANG_WARN_BOOL_CONVERSION = YES;
				CLANG_WARN_COMMA = YES;
				CLANG_WARN_CONSTANT_CONVERSION = YES;
				CLANG_WARN_DEPRECATED_OBJC_IMPLEMENTATIONS = YES;
				CLANG_WARN_DIRECT_OBJC_ISA_USAGE = YES_ERROR;
				CLANG_WARN_DOCUMENTATION_COMMENTS = YES;
				CLANG_WARN_EMPTY_BODY = YES;
				CLANG_WARN_ENUM_CONVERSION = YES;
				CLANG_WARN_INFINITE_RECURSION = YES;
				CLANG_WARN_INT_CONVERSION = YES;
				CLANG_WARN_NON_LITERAL_NULL_CONVERSION = YES;
				CLANG_WARN_OBJC_IMPLICIT_RETAIN_SELF = YES;
				CLANG_WARN_OBJC_LITERAL_CONVERSION = YES;
				CLANG_WARN_OBJC_ROOT_CLASS = YES_ERROR;
				CLANG_WARN_QUOTED_INCLUDE_IN_FRAMEWORK_HEADER = YES;
				CLANG_WARN_RANGE_LOOP_ANALYSIS = YES;
				CLANG_WARN_STRICT_PROTOTYPES = YES;
				CLANG_WARN_SUSPICIOUS_MOVE = YES;
				CLANG_WARN_UNGUARDED_AVAILABILITY = YES_AGGRESSIVE;
				CLANG_WARN_UNREACHABLE_CODE = YES;
				CLANG_WARN__DUPLICATE_METHOD_MATCH = YES;
				COPY_PHASE_STRIP = NO;
				DEBUG_INFORMATION_FORMAT = "dwarf-with-dsym";
				ENABLE_NS_ASSERTIONS = NO;
				ENABLE_STRICT_OBJC_MSGSEND = YES;
				ENABLE_USER_SCRIPT_SANDBOXING = YES;
				GCC_C_LANGUAGE_STANDARD = gnu17;
				GCC_NO_COMMON_BLOCKS = YES;
				GCC_WARN_64_TO_32_BIT_CONVERSION = YES;
				GCC_WARN_ABOUT_RETURN_TYPE = YES_ERROR;
				GCC_WARN_UNDECLARED_SELECTOR = YES;
				GCC_WARN_UNINITIALIZED_AUTOS = YES_AGGRESSIVE;
				GCC_WARN_UNUSED_FUNCTION = YES;
				GCC_WARN_UNUSED_VARIABLE = YES;
				LOCALIZATION_PREFERS_STRING_CATALOGS = YES;
				MTL_ENABLE_DEBUG_INFO = NO;
				MTL_FAST_MATH = YES;
				SDKROOT = macosx;
				SWIFT_COMPILATION_MODE = wholemodule;
			};
			name = Release;
		};
		AB0000000000000000000081 /* Debug */ = {
			isa = XCBuildConfiguration;
			buildSettings = {
				CLANG_ENABLE_MODULES = YES;
				CODE_SIGN_STYLE = Automatic;
				CURRENT_PROJECT_VERSION = 1;
				ENABLE_PREVIEWS = YES;
				GENERATE_INFOPLIST_FILE = YES;
				INFOPLIST_KEY_LSApplicationCategoryType = "public.app-category.music";
				INFOPLIST_KEY_NSHighResolutionCapable = YES;
				INFOPLIST_KEY_NSPrincipalClass = NSApplication;
				LD_RUNPATH_SEARCH_PATHS = "@executable_path/../Frameworks";
				MACOSX_DEPLOYMENT_TARGET = 15.0;
				MARKETING_VERSION = 1.0;
				PRODUCT_BUNDLE_IDENTIFIER = com.codex.SoundCloudGeoSeedMacOS;
				PRODUCT_NAME = "$(TARGET_NAME)";
				SDKROOT = macosx;
				SUPPORTED_PLATFORMS = macosx;
				SWIFT_EMIT_LOC_STRINGS = NO;
				SWIFT_OPTIMIZATION_LEVEL = "-Onone";
				SWIFT_VERSION = 5.0;
			};
			name = Debug;
		};
		AB0000000000000000000082 /* Release */ = {
			isa = XCBuildConfiguration;
			buildSettings = {
				CLANG_ENABLE_MODULES = YES;
				CODE_SIGN_STYLE = Automatic;
				CURRENT_PROJECT_VERSION = 1;
				ENABLE_PREVIEWS = YES;
				GENERATE_INFOPLIST_FILE = YES;
				INFOPLIST_KEY_LSApplicationCategoryType = "public.app-category.music";
				INFOPLIST_KEY_NSHighResolutionCapable = YES;
				INFOPLIST_KEY_NSPrincipalClass = NSApplication;
				LD_RUNPATH_SEARCH_PATHS = "@executable_path/../Frameworks";
				MACOSX_DEPLOYMENT_TARGET = 15.0;
				MARKETING_VERSION = 1.0;
				PRODUCT_BUNDLE_IDENTIFIER = com.codex.SoundCloudGeoSeedMacOS;
				PRODUCT_NAME = "$(TARGET_NAME)";
				SDKROOT = macosx;
				SUPPORTED_PLATFORMS = macosx;
				SWIFT_EMIT_LOC_STRINGS = NO;
				SWIFT_VERSION = 5.0;
			};
			name = Release;
		};
/* End XCBuildConfiguration section */

/* Begin XCConfigurationList section */
		AB0000000000000000000061 /* Build configuration list for PBXProject "SoundCloudGeoSeedMacOS" */ = {
			isa = XCConfigurationList;
			buildConfigurations = (
				AB0000000000000000000071 /* Debug */,
				AB0000000000000000000072 /* Release */,
			);
			defaultConfigurationIsVisible = 0;
			defaultConfigurationName = Release;
		};
		AB0000000000000000000062 /* Build configuration list for PBXNativeTarget "SoundCloudGeoSeedMacOS" */ = {
			isa = XCConfigurationList;
			buildConfigurations = (
				AB0000000000000000000081 /* Debug */,
				AB0000000000000000000082 /* Release */,
			);
			defaultConfigurationIsVisible = 0;
			defaultConfigurationName = Release;
		};
/* End XCConfigurationList section */
	};
	rootObject = AB0000000000000000000051 /* Project object */;
}
"""


def reset_output() -> None:
    if OUT.exists():
        shutil.rmtree(OUT)
    APP_DIR.mkdir(parents=True, exist_ok=True)
    SHARED_DIR.mkdir(parents=True, exist_ok=True)
    RES_DIR.mkdir(parents=True, exist_ok=True)
    WORKSPACE_DIR.mkdir(parents=True, exist_ok=True)


def copy_sources() -> None:
    for src in ROOT.glob("*.swift"):
        if src.name == "MapGraphApp.swift":
            continue
        shutil.copy2(src, SHARED_DIR / src.name)


def copy_resources() -> None:
    src_res = ROOT / "Resources"
    if not src_res.exists():
        return
    for src in src_res.glob("*.json"):
        shutil.copy2(src, RES_DIR / src.name)


def write_files() -> None:
    (APP_DIR / "SoundCloudGeoSeedMacOSApp.swift").write_text(APP_SWIFT, encoding="utf-8")
    (OUT / "README.md").write_text(README_MD, encoding="utf-8")
    (PROJ_DIR / "project.pbxproj").write_text(PBXPROJ, encoding="utf-8")
    (WORKSPACE_DIR / "contents.xcworkspacedata").write_text(WORKSPACE_XML, encoding="utf-8")


def verify_project() -> None:
    cmd = [
        "xcodebuild",
        "-list",
        "-project",
        str(PROJ_DIR),
    ]
    result = subprocess.run(cmd, capture_output=True, text=True)

    print("\n=== xcodebuild -list ===")
    if result.stdout.strip():
        print(result.stdout.strip())
    if result.stderr.strip():
        print(result.stderr.strip())

    if result.returncode != 0:
        raise SystemExit(result.returncode)


def print_summary() -> None:
    print("\nCreated:")
    print(f"- Export folder: {OUT}")
    print(f"- App entry file: {APP_DIR / 'SoundCloudGeoSeedMacOSApp.swift'}")
    print(f"- Shared sources: {SHARED_DIR}")
    print(f"- Resources: {RES_DIR}")
    print(f"- Project bundle: {PROJ_DIR}")
    print(f"- Key file: {PROJ_DIR / 'project.pbxproj'}")
    print(f"- Workspace metadata: {WORKSPACE_DIR / 'contents.xcworkspacedata'}")


def main() -> None:
    if not ROOT.exists():
        raise FileNotFoundError(f"Source folder not found: {ROOT}")

    reset_output()
    copy_sources()
    copy_resources()
    write_files()
    print_summary()
    verify_project()


if __name__ == "__main__":
    main()
```

Save it as `make_xcodeproj.py`, then run:

```bash
python3 make_xcodeproj.py
```

This script:
- creates `SoundCloudGeoSeed-macOS`
- writes `SoundCloudGeoSeedMacOSApp.swift`
- copies Swift files into `Shared`
- copies JSON files into `Resources`
- creates `SoundCloudGeoSeedMacOS.xcodeproj`
- writes `project.pbxproj`
- writes `project.xcworkspace/contents.xcworkspacedata`
- runs `xcodebuild -list` to verify the target and scheme exist

One detail to watch: `.environment(sharedViewModel)` is correct only if your app uses the newer Observation-style environment injection. If your view model is `ObservableObject`, change that line to `.environmentObject(sharedViewModel)`.
