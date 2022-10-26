# Java bindings for Intel OpenVINO

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
  implementation "dkurt:openvino_java:2022.2:linux-x86_64@jar"  // Choose "macosx-x86_64" for Mac or "windows-x86_64" for Windows
}
```


Or download from [releases](https://github.com/dkurt/openvino_java/releases) page.

## Tutorials
* [Audio Recognition in Android with OpenVINO](https://medium.com/@dmitry.kurtaev/audio-recognition-in-android-with-openvino-5d51e71f1426)
* [Sign language recognition on Android with Intel OpenVINO](https://medium.com/@anna.likholat/sign-language-recognition-on-android-with-intel-openvino-1296d76bfa5e)
