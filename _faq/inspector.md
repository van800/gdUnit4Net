---
layout: default
title: Inspector
nav_order: 1
---

# The GdUnit Test Inspector/Explorer

## Definition
The GdUnit inspector provides an overview of the currently executed tests and allows you to navigate them. It allows you to select individual tests and view possible test failures. The integrated status and info bar gives you a quick overview of the last test run.

![]({{ site.baseimg }}/gdUnit4/assets/images/inspector/inspector.png){:.centered}
- [(1) Button Bar](#button-bar)
- [(2) Status Bar](#status-bar)
- [(3) Test Run Overview](#test-run-overview-tree)
- [(4) Failure Report](#failure-report)
- [(5) Info Bar](#info-bar)

---

## Button Bar
The button bar contains several buttons that allow you to perform different actions in GdUnit:
![]({{ site.baseimg }}/gdUnit4/assets/images/inspector/button-bar.png){:.centered}

|Button|Description|
|--- | --- |
|(1)| Opens the GdUnit documentation page in your browser |
|(2)| Opens the GdUnit settings window |
|(3)| (Re)Run the tests in runtime mode |
|(4)| (Re)Run the tests in debug mode |
|(5)| Stops the current test run |
|(6)| Displays the version of GdUnit |

Note that the keyboard shortcuts for these buttons may vary depending on your specific GdUnit configuration.

{% include advice.html 
content="When running tests in GdUnit, it is recommended to first run them in debug mode (4) in order to get the line number where the failure occurred in the test report. This is because Godot does not provide stack trace information when running in runtime mode (3), which can result in the failure line not being displayed in the report."
%}


### The Run Overall Button
The **Run Overall** button provides a convenient way to execute all the tests in your project at once, instead of running them one by one or selecting a custom set of tests. By clicking the "Run Overall" button, you can initiate the execution of all the tests in your project, saving you time and effort.
![](/gdUnit4/assets/images/inspector/overall-button.png){:.centered}
To enable the **Run Overall** button in GdUnit4, you need to adjust the [UI settings](/gdUnit4/first_steps/settings/#ui-settings).<br>
Once you have enabled the **Run Overall** button, it should be visible in the inspector.

---

## Status Bar
This area gives you information about the current/last test execution, such as the progress and errors/failures found.<br>
With the arrow buttons, you can navigate back and forth over found failures.<br>
![](/gdUnit4/assets/images/inspector/status-bar.png){:.centered}

|Marker|Description|
|--- | --- |
|(1)| Test execution progress (indicator of test run)|
|(2)| Number of errors found (parse/runtime errors)|
|(3)| Number of test case failures found|
|(4)| Navigate to previous failure |
|(5)| Navigate to next failure |

{% include advice.html 
content="Whats the difference between errors and failures?<br>
GdUnit distinguishes between errors and failures. An error is a hard failure such as a test abort or timeout, while a failure is a test error caused by a failed assertion."
%}

---

## Test Run Overview Tree
This area provides an overview of all executed/executing tests and their execution status in real-time. Here, you can navigate through the tests and view the report for each individual test by selecting it. You can also run the currently selected test or test suite again by right-clicking to open a context menu.
![](/gdUnit4/assets/images/inspector/test-overview.png){:.centered}

{% include advice.html
content="Double-clicking on a test in the test run overview allows you to jump directly to the test or test error if a failure line was reported in Debug Mode (4)."
%}

---

## Failure Report
This area displays the failure report of the currently selected failed test.<br>
GdUnit generates the failure report based on the used assert, according to the scheme **expected** vs **current** value.
![](/gdUnit4/assets/images/inspector/report.png){:.centered}

---

## Info Bar
This section provides you with information about the total duration of the test execution and any orphaned nodes found.<br>
![](/gdUnit4/assets/images/inspector/info-bar.png){:.centered}

* **Time**<br>
    The time taken to execute all tests.
* **Orphans**<br>
     The number of nodes that were not cleaned up after the execution of the tests. Orphaned nodes can cause memory leaks, and it's essential to clean them up after the execution of the tests.
{% include advice.html
content="It's recommended to always check for orphaned nodes after the execution of tests to ensure there are no memory leaks in your game/application." 
%}



---
<h4> document version v4.1.0 </h4>