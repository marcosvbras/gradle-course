# Gradle Course

This repository has everything I learned on Udacity course *Gradle for Android and Java*. There are all exercises that I did during the course and a small summary with some theoretical information about Gradle.

## Why does Android use Gradle?

The Java source created on Android Studio is not compiled as standard Java byte code, it is compiled to a custom byte code for the Android run time instead. There are three types of Android resources that are packed differently and all these things are not too simple to do by hand.

## How to install Gradle?

Gradle knows how to install itself through a shell script and a tiny jar that knows how to download and install it. So, to do this job, everything you need is a gradle script and a Gradle Wrapper jar in the same directory level.

If you use Mac or Linux, just type:
```shell
./gradlew
```

Or, if you use Windows, just type:
```shell
gradlew
```

## How does Gradle work?

Gradle has to do a significant amount of work to start up, mainly because it is required to use an instance of the JVM to run. This startup time can be mitigated by using the Gradle Demon. When Gradle's instructed to use a demon, a demon process has started, and continuously runs in the background, keeping the JVM instance alive. So that subsequent Gradle runs can use the same instance. By default, Android Studio always uses this as Gradle demon, when running Gradle from the command line however you'll have to explicitly enable it. Simply put you should always use a demon when it is possible.

Gradle works with a concept called Tasks. A task is a self-contained unit of work that Gradle can reason about. A task has an action that do something, e.g. copy some files from one directory to another.

## Command Summary

- **gradlew <task>**: To run a task
- **gradlew tasks**: To see a list of available tasks
