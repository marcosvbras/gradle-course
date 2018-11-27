# Gradle Course

This repository has everything I learned on Udacity course *Gradle for Android and Java*. There are all exercises that I did during the course and a small summary with some theoretical information about Gradle.

## Why does Android use Gradle?

The Java source created on Android Studio is not compiled as standard Java byte code, it is compiled to a custom byte code for the Android run time instead. There are three types of Android resources that are packed differently and all these things are not too simple to do by hand.

## How to install Gradle?

Gradle knows how to install itself through a shell script and a tiny jar that knows how to download and install it. So, to do this job, everything you need is a gradle script and a Gradle Wrapper jar in the same directory level.

If you use Mac or Linux, just type:
```bash
$ ./gradlew
```

Or, if you use Windows, just type:
```bash
gradlew
```

The approach above will work just with an existing Gradle project. That way we can ensure that everyone working on the project is using the same version of Gradle. However, if you want to create a new Gradle project, you will need a local installation of Gradle.

### Mac/Linux Install

- Download the [latest version of Gradle](https://gradle.org/gradle-download/)
- Run the following code

```bash
$ unzip ~/Downloads/gradle-2.11-all.zip -d /usr/local/gradle/ && export GRADLE_HOME=/usr/local/gradle/gradle-2.11
$ PATH=$GRADLE_HOME/bin:$PATH
$ export PATH
# Turning on the Gradle daemon by default
$ export GRADLE_OPTS="-Dorg.gradle.daemon=true" >> ~/.bash_profile && source ~/.bash_profile
```

> **NOTE**: Don't forget changing the commands Gradle version to which one you downloaded.

### Windows Install

First, head over to https://gradle.org/gradle-download/, and download the latest version of Gradle. Note that we want the complete distribution. Next, we'll unzip Gradle and move it to where we want it to live. Our recommendation is in `C:\gradle-2.11`.

To tell Windows where to find Gradle, we need to add an environment variable. Navigate to the Control Panel > System > Advanced system settings > Advanced > Environment Variables... > System variables > New...

Set the variable name to: GRADLE_HOME Set the variable value to the location you unzipped Gradle if you followed our suggestion it should be: C:\gradle-2.11

Then edit the PATH user variable by appending: ;%GRADLE_HOME%\bin\

Your path will then look something like:

    <a bunch of directories>;%GRADLE_HOME%\bin\

When you're done, run `gradle --version` to ensure the installation is complete.

Finally, let's add a properties file to tell Gradle to use the daemon by default. All we need to do is put a file named `gradle.properties` in

C:\Users\<your username>\.gradle, and add the line `org.gradle.daemon=true`.

> **NOTE**: Don't forget changing the commands Gradle version to which one you downloaded.

## How does Gradle work?

Gradle has to do a significant amount of work to start up, mainly because it is required to use an instance of the JVM to run. This startup time can be mitigated by using the Gradle Demon. When Gradle's instructed to use a demon, a demon process has started, and continuously runs in the background, keeping the JVM instance alive. So that subsequent Gradle runs can use the same instance. By default, Android Studio always uses this as Gradle demon, when running Gradle from the command line however you'll have to explicitly enable it. Simply put you should always use a demon when it is possible.

The build scripts are written in Groovy. Groovy interoperates extremely well with Java and has some special features that make it ideally suited for creating domain specific languages (DSLs). Gradle provides its own Groovy distribution, so we don't even need to install Groovy to get started.

Gradle works with a concept called Tasks. A task is a self-contained unit of work that Gradle can reason about. A task has an action that do something, e.g. copy some files from one directory to another.

## Command Summary

- `gradle <task>`: Run a task
- `gradle tasks`: See a list of available tasks
- `gradle --status`: See all Daemons status
- `gradle --stop`: Stop running all Daemons
