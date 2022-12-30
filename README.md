# Java bindings for Intel OpenVINO

[![GitHub all releases](https://img.shields.io/github/downloads/dkurt/openvino_java/total?color=blue)](https://github.com/dkurt/openvino_java/releases)

**NOTE**: This is an unofficial build farm for OpenVINO in Java for Linux, Windows and Mac (x86) and Android (x86 and ARM64)

## How to use

Setup OpenVINO with Gradle:

```gradle
repositories {
  mavenCentral()

  def github = ivy {
    url "https://github.com/"

    patternLayout {
        artifact '/[organisation]/[module]/releases/download/[revision]/openvino-[revision]-[classifier].[ext]'
    }

    metadataSources { artifact() }
  }

  exclusiveContent {
      forRepositories(github)
      filter { includeGroup("dkurt") }
  }
}

dependencies {
  implementation "dkurt:openvino_java:2022.3:linux-x86_64@jar"  // Choose "macosx-x86_64" for Mac or "windows-x86_64" for Windows
}
```


Or download from [releases](https://github.com/dkurt/openvino_java/releases) page.

## Tutorials
* [Audio Recognition in Android with OpenVINO](https://medium.com/@dmitry.kurtaev/audio-recognition-in-android-with-openvino-5d51e71f1426)
* [Sign language recognition on Android with Intel OpenVINO](https://medium.com/@anna.likholat/sign-language-recognition-on-android-with-intel-openvino-1296d76bfa5e)
