# invesdwin-instrument

This is an instrumentation java agent that is able to load itself into the running JVM. It is able to dynamically setup springs `InstrumentationLoadTimeWeaver` to enable support for aspects without having to start the JVM with an explicit java agent.

## Maven

Releases and snapshots are deployed to this maven repository:
```
http://invesdwin.de:8081/artifactory/invesdwin-oss
```

Dependency declaration:
```xml
<dependency>
	<groupId>de.invesdwin</groupId>
	<artifactId>invesdwin-instrument</artifactId>
	<version>1.0.0-SNAPSHOT</version>
</dependency>
```

## Usage

Simply define a static initializer like this:
```xml
static {
  DynamicInstrumentationLoader.waitForInitialized();
}
```

Please note that you need to have a JDK installed with tools.jar available in it for this to work properly.
Alternatively just load the jar via the `-javaagent <path>` JVM parameter if you only have a JRE installed.
The dynamic loading will be skipped then.
