Creating a Plugin Project﻿

The IntelliJ Platform SDK - the primary source of documentation for extending the IntelliJ Platform by creating plugins, custom language support, or building a custom IDE.

But the IntelliJ Platform's real power comes from the Program Structure Interface (PSI). It is a set of functionalities used to parse files, build rich syntactic and semantic models of the code, and build indexes from this data. PSI powers a lot of functionality, from quick navigating to files, types, and symbols, to the contents of code completion windows and find usages, code inspections, and code rewriting, for quick fixes or refactorings, as well as many other features.
The IntelliJ Platform includes parsers and a PSI model for many languages, and its extensible nature means that it is possible to add support for other languages.



Creation of agile development environment. 

    • CRUD .
    • Standardized code. 
    • Reusable code.


Tasks
Plugin introduces the following tasks
Task
Description
buildPlugin
Assembles plugin and prepares zip archive for deployment.
patchPluginXml
Collects all plugin.xml files in sources and fill since/until build and version attributes.
downloadRobotServerPlugin
Downloads robot-server plugin which is needed for ui tests running.
prepareSandbox
Creates proper structure of plugin, copies patched plugin xml files and fills sandbox directory with all of it.
prepareTestingSandbox
Prepares sandbox that will be used while running tests.
prepareUiTestingSandbox
Prepares sandbox that will be used while running ui tests.
buildSearchableOptions
Builds an index of UI components (a.k.a. searchable options) for the plugin by running a headless IDE instance.
Note, that this is a runIde task with predefined arguments and all properties of runIde task are also applied to buildSearchableOptions tasks.
jarSearchableOptions
Creates a jar file with searchable options to be distributed with the plugin.
runIde
Executes an IntelliJ IDEA instance with the plugin you are developing.
runIdeForUiTests
Executes an IntelliJ IDEA instance ready for ui tests run with the plugin you are developing. See intellij-ui-test-robot project to know more
publishPlugin
Uploads plugin distribution archive to https://plugins.jetbrains.com.
runPluginVerifier
Runs the IntelliJ Plugin Verifier tool to check the binary compatibility with specified IntelliJ IDE builds.
verifyPlugin
Validates completeness and contents of plugin.xml descriptors as well as plugin’s archive structure.


Documentation:


https://plugins.jetbrains.com/docs/intellij/intellij-platform.html#plugins



To Create an IntelliJ Platform Plugin Project:
﻿
       1. On the main menu, choose File | New | Project. ...
       2. Set IntelliJ Platform Plugin project type.
       3. Click Next.
       4. Set the desired project name.
       5. Click Finish to generate project structure files.
       6. Go to File | Project Structure to customize project settings if required.
       


Running and Debugging a Plugin﻿

It's possible to run and debug a plugin directly from the IntelliJ IDEA. You need a configured special profile (a Plugin Run/Debug configuration) that specifies the plugin module, VM parameters, and other specific options. When you run such a profile, it launches the IDE with your plugin installed.

Using IntelliJ IDEA's debugger, you can find out the origin of the run-time errors and exceptions.

To debug a plugin
    • Select Run | Debug in the main menu, or press Shift + F9.
To run a plugin
    • Select Run | Run in the main menu, or press Shift + F10.


