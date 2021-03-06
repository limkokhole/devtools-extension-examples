Firefox DevTools Extension Examples
===================================

This repository contains extensions for Firefox native developer tools
showing how to build extensions and use existing platform API.

Use [JPM](https://developer.mozilla.org/en-US/Add-ons/SDK/Tools/jpm)
to run example extensions.

Run with Firefox Nightly on OSX:

`jpm run -b /Applications/FirefoxNightly.app`


See also:
* [Hacking on DevTools](https://wiki.mozilla.org/DevTools/Hacking)
* [Hacking on Firebug](https://github.com/firebug/firebug.next#hacking-on-firebugnext-aka-firebug-3)

HelloWorld
----------
This example shows basic architecture of an extension for Firefox developer
tools. It handles basic toolbox initialization events and registers
a new panel.

Related API:

    Panel
    Tool

Related Events:

    `toolbox-ready`
    `toolbox-destroy`
    `toolbox-destroyed`

CustomTheme
-----------
This extension shows how to implement new theme for developer tools Toolbox.

Related API:

    gDevTools.registerTheme()
    gDevTools.unregisterTheme()

GlobalActor
-----------
This extension shows how to implement tools/features that can be used
to debug/inspect remote devices. Learn how to properly implement both:
the client and sever side of new tool. Remotable feature in this extension
is implemented as a `global actor`.

Related API:

    Actor
    ActorFront
    registerGlobalActor()

TabActor
-----------
This extension shows how to create a tab actor. If multiprocess support
is active tab actors run within the child process (global actors run
within the parent process).

Related API:

    Actor
    ActorFront
    registerTabActor()

ConsoleListener
---------------
This extension shows how to intercept and modify logs in the Console panel.

Related Events:

    `webconsole-ready`
    `new-messages`

HelloReact
----------
An example extension showing how to integrate standard web technologies
with an extension.

Related Libs:
* Bootstrap: http://getbootstrap.com/
* React: http://facebook.github.io/react/
* React Bootstrap: http://react-bootstrap.github.io/components.html

MessageManager
--------------
An example extension showing how to communicate between chrome and
content scopes.

Related API:

    addMessageListener()
    removeMessageListener()
    sendAsyncMessage()

DOM Inspector
-------------
An example extension showing how to send DOM node from the backed to
the client.

Related API:

    Actor
    registerTabActor()
    Actor Events
    NodeFront

Related Events:

    `toolbox-ready`
    `toolbox-destroy`

CustomActor
-----------
This extension shows how to implement backend actor register and
unregister it. Learn how to properly implement both the client and sever
side. This example also shows how to communicate between chrome and content
scope through MessageChannel.

Related API:

    Actor
    ActorFront
    registerTabActor()
    MessageChannel()

TitleManager
------------
An example extension showing how to access 'window' global
in the web page and also register new Console command-line
commands.

Related API:

    Actor
    registerTabActor()
    Toolbox Events
    WebConsoleCommands
    ToolboxOverlay


NetAnalysis
-----------
An example showing how to perform custom analysis of data collected by
the Network panel. Check out how to get all data as HAR object.
See also: http://www.softwareishard.com/blog/har-12-spec/

Related API:

    HAR
    HARBuilder
    HARExporter
    ToolboxOverlay

SimpleMVC
-----------
An example extension showing how to use Model View Controller (MVC) pattern
in context of an extension for Firefox DevTools.
(based on HelloWorld example above)

Related API:

    Panel
    Tool
    MessageManager
    Frame script
    Mode View Controller
    Chrome & Content scope communication

TodoMVC
-------
Basic example extension showing how to use ReactJS+Redux to implement
an extension for Firefox developer tools. The example is taken
and adapted from the official Redux docs. Recommended mainly for
web developers who want to use existing knowledge and build Firefox
developer tools extensions on top of standard web technologies.

Related API:

    Firebug.SDK
    ReactJS
    Redux

Further Resources
=================
* Add-on SDK: https://developer.mozilla.org/en-US/Add-ons/SDK
* Add-on SDK Coding Style: https://github.com/mozilla/addon-sdk/wiki/Coding-style-guide
* DevTools API: https://developer.mozilla.org/en-US/docs/Tools/DevToolsAPI
* DevTools Extension Examples: https://github.com/firebug/devtools-extension-examples
* Hacking on core DevTools: https://wiki.mozilla.org/DevTools/Hacking
