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
  implementation "dkurt:openvino_java:2022.1:linux-x86_64@jar"  // Choose "macosx-x86_64" for Mac or "windows-x86_64" for Windows
}
```


Or download from [releases](https://github.com/dkurt/openvino_java/releases) page.
