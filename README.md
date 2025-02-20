# ClockSystem

This is a gradle-based Java project for a Clock with Swing GUI and JUnit5 unit
tests. It has been created and used by Tom Mens for educational purposes at the
University of Mons.

The application includes a watch, with timer, stopwatch and alarm functionality.
Its implementation is based on a statechart, using the state and singleton
design patterns.

## Development Environments

There are multiple ways to set up your development environment: you can use
**DevContainer**, **Nix**, or configure it manually.

Due to the graphical nature of the application (Java GUI), running the interface
may not be possible within **DevContainer**. However, you can still use
**DevContainer** to run tests or generate the JAR file. If you need to interact
with the GUI, consider using **Nix** or a manual setup.

### Using DevContainer (Container based)

[DevContainer](https://containers.dev/) is a feature available for
[VSCode](https://code.visualstudio.com/) and
[Jetbrains](https://www.jetbrains.com/) IDEs that allows you to develop
seamlessly in a containerised environment. This approach will setup your
development environment using containers.

1. Ensure you have Docker installed on your machine. It might work with Podman
   too, but it is not tested yet.
2. Install the DevContainer extension
   1. For VSCode:
      [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
      ([documentation](https://code.visualstudio.com/docs/devcontainers/containers))
   2. For Jetbrains: nothing to do, it is supported by default
      ([documentation](https://www.jetbrains.com/help/idea/connect-to-devcontainer.html))
3. Open the project in your IDE, and you should see a notification to reopen the
   project in a container, click on it.
4. Once the project is reopened in the container, you need to wait a bit for the
   container to build and start, and then you can start developing, all the
   tools and dependencies are already installed in the container.

### Using Nix

This approach will setup a development environment using the
[Nix](https://nixos.org) package manager. Unlike DevContainer, no
containerisation is used, and the development environment will be installed on
your local machine, in total isolation from your current system packages.

1. Install Nix package manager: `curl -L https://nixos.org/nix/install | sh`
2. Go to the project root folder
3. Run `nix develop` to enter the development environment
4. Once you are done, you can exit the environment by running `exit`

## Instructions

The application has been tested locally with Java 21 and Gradle 8.5 (on MacOS).
To run it locally, download the latest release and run the following
command-line instructions, assuming you have already gradle installed on your
machine:

"gradle wrapper" (creates the necessary gradle wrapper files to be able to build
the app with gradle).

"./gradlew build" (executes the generated wrapper to build and test the
application; build should be successful, but will fail if some of the unit tests
fail)

"./gradlew run" (executes the Java application by opening a graphical user
interface you can interact with)
