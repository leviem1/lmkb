# Creating a Fat JAR Using Gradle

There are a few ways to build a self-contained JAR file using gradle.

## Method 1: Shadow

The [Gradle Shadow Plugin](https://imperceptiblethoughts.com/shadow/) makes creating
self-contained JARs a bit easier with a few additional convenience features.
The Shadow plugin will not only create a self-contained JARs, but will also allow you to shade
your dependencies so that you can avoid classpath collisions. Here's a basic skeleton
of a typical Shadow Gradle file.

```groovy
plugins {
    id 'java'
    id 'com.github.johnrengelman.shadow' version '6.1.0'
}

group = "com.example.project"

java {
    sourceCompatibility = JavaVersion.VERSION_11
    targetCompatibility = JavaVersion.VERSION_11
}

repositories {
    mavenCentral()
}

shadowJar {
    archiveClassifier.set('SNAPSHOT')
    relocate 'com.example.project2', 'shadow.com.example.project2'
    minimize()
}

jar.enabled = false
build.dependsOn(shadowJar)
```

## Method 2: Java Plugin Jar Task

While Shadow can often simplify packaging, it can sometimes cause issues with clobbering
files and causing classloader issues, for example, with **log4j**. There may be a
transformer available to resolve that issue, but I was not able to find it myself.
Below is an approach pulled from a few sources on StackOverflow that leverages the
Java plugin `jar` task.

```groovy
plugins {
    id 'java'
}

// Configure jar file
jar {
    // Exclude duplicated resources from bundle (suppresses Gradle warnings)
    duplicatesStrategy = DuplicatesStrategy.EXCLUDE

    // Bundle runtime and compile time dependencies, not certain if this is 100% correct
    from {
        configurations.runtimeClasspath.collect {
            it.isDirectory() ? it : zipTree(it)
        }

        configurations.compileClasspath.collect {
            it.isDirectory() ? it : zipTree(it)
        }
    }

    // Declare main class for jar
    manifest {
        attributes(
                'Main-Class': 'com.quantum.jsu.Jsu'
        )
    }

    // Prevent security exceptions by excluding sensitive files
    exclude 'META-INF/*.RSA', 'META-INF/*.SF','META-INF/*.DSA'
}
```