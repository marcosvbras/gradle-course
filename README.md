# Gradle Course

## Why does Android use Gradle?

The Java source created on Android Studio is not compiled as standard Java byte code, it is compiled to a custom byte code for the Android run time instead. There are three types of Android resources that are packed differently and all these things are not too simple to do by hand.

## How does Gradle work?

Gradle works with a concept called Tasks. A task is a self-contained unit of work that Gradle can reason about. A task has an action that do something, e.g. copy some files from one directory to another.

## Command Summary

- **gradlew**: To download the specified Gradle version
- **gradlew <task>**: To run a task
- **gradlew tasks**: To see a list of available tasks
