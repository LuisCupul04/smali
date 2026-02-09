# smali

Google Smali 3.0.9 configured for ExtenRe ecosystem.

## Published Artifacts

```groovy
// Maven coordinates
implementation('com.extenre:smali:3.0.9.RE')
implementation('com.extenre:smali-baksmali:3.0.9.RE')
implementation('com.extenre:smali-dexlib2:3.0.9.RE')
implementation('com.extenre:smali-util:3.0.9.RE')
```

##### About

This is **Google Smali 3.0.9** repackaged for the ExtenRe ecosystem.

**Key changes from the original:**
- **Group ID:** `com.extenre` (was `com.android.tools.smali`)
- **Version:** `3.0.9.RE` 
- **Published on:** GitHub Packages (not Google Maven)

**Original project:** smali/baksmali is an assembler/disassembler for the dex format used by dalvik, Android's Java VM implementation. The syntax is loosely based on Jasmin's/dedexer's syntax, and supports the full functionality of the dex format.

**Note:** This repository contains the **exact same code** as Google Smali 3.0.9, with only build configuration changes for ExtenRe compatibility.

#### Support
- [github Issue tracker](https://github.com/google/smali/issues) - For any bugs/issues/feature requests

#### Some useful links for getting started with smali

- [Official dex bytecode reference](https://source.android.com/devices/tech/dalvik/dalvik-bytecode.html)
- [Registers wiki page](https://github.com/JesusFreke/smali/wiki/Registers)
- [Types, Methods and Fields wiki page](https://github.com/JesusFreke/smali/wiki/TypesMethodsAndFields)
- [Official dex format reference](https://source.android.com/devices/tech/dalvik/dex-format.html)

### Building and testing

All building and testing should be done using a version of OpenJDK 11. Newer OpenJDK versions are currently not supported due to issues with some of the tools used in the build process.

#### Building
```
./gradlew assemble
```
#### Command Line Version

To run the `smali` and `baksmali` tools from the command line build the fat
jars. The fat jars will be named with the current version followed by the first
8 characters of the current git hash followed by an optional `-dirty` if the
repository was dirty when building and ending in  -fat . The fat jar can be
invoked with `java -jar`.
```
./gradlew smali:fatJar
java -jar smali/build/libs/smali-x.y.z-aaaaaaaa-dirty-fat.jar
```

#### Testing

To execute all tests run
```
./gradlew test
```

#### Testing Maven Release
Push a release version to your local maven repository (add
`-Dmaven.repo.local=<dir>` to override the default local maven repository
location)
```
./gradlew release publishToMavenLocal
```

### Publishing to GitHub Packages

```bash
# Configure credentials in ~/.gradle/gradle.properties:
# gpr.user=LuisCupul04
# gpr.key=ghp_your_token

./gradlew clean build publish
```

### About ExtenRe Ecosystem

This artifact is part of the ExtenRe ecosystem, which includes:
- `com.extenre:apktool-lib`
- `com.extenre:multidexlib2`
- `com.extenre:smali`

All published on GitHub Packages for use in ExtenRe projects.
