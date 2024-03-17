+++
title = 'Associate .dig files with Digital on macOS'
date = 2024-03-16T12:41:56+01:00
draft = false
thumbnail.src = 'images/tn/digital.png'
+++
Here are the steps I take to associate **.dig** files to autostart the [Digital](https://github.com/hneemann/Digital) application on double-click.

Normally a script/shell file can't be associated to an extension in macOS. To solve this I make a small "app" using the built-in Automator application and have that run a script that runs Digital.


> Please note that these intructions assume that you have installed the Digital "jar" file in /Applications/Digital If you're having it somewhere else you need to adjust the Automator code. ==

**1 Run Automator (cmd-space and type automator)**

**2 Click on “New Document” and choose “Application”**
{{< figure src="/images/automator-app-type.png" width="600">}}

**3 Drag “Run Shell Script” into the grey area** 
{{< figure src="/images/automator-drag-to-grey.png" width="600">}}

**4 Change “Pass input” to “as arguments” and replace the example script with the text**

```java -jar /Applications/Digital/Digital.jar $1 >/dev/null 2>&1 &```
{{< figure src="/images/automator-script.png" width="600">}}

**6 Save it as Digital.app in /Applications/Digital (or wherever you have Digital saved)**

**7 Right click on any .dig-file and select “Get Info”. Change the “Open with:” to “Other” and navigate to /Applications/Digital/ and select the newly created Digital.app there.**
{{< figure src="/images/automator-finder-open-with.png" width="600">}}

**8 Finally click on the “Change All”-button**

