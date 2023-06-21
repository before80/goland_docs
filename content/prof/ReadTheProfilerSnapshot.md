+++
title = "Read the profiler snapshot"
weight = 50
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Read the profiler snapshot﻿

https://www.jetbrains.com/help/go/read-the-profiling-report.html

Last modified: 27 March 2023

In the Profiler tool window, the collected data is presented on several tabs: Flame Graph, Call Tree, and Method List.

## Navigate the snapshot﻿

You can jump between the tabs while staying focused on a specific method. Right-click the necessary method and select another view in which you want to open it.

![https://resources.jetbrains.com/help/img/idea/2023.1/go_navigate_profiler.png](ReadTheProfilerSnapshot_img/go_navigate_profiler.animated.gif)

For a method on any tab, you can open the [Merged Callees](https://www.jetbrains.com/help/go/read-the-profiling-report.html#callees) and [Back Traces](https://www.jetbrains.com/help/go/read-the-profiling-report.html#backtraces) trees. Right-click the method and select Method Merged Callees or Method Back Traces respectively.

If you want to review the sources in the editor, right-click it on any tab and select Jump to Source or press F4. This will take you to the place where this method is declared.

## Flame Graph﻿

The flame graph visualizes the application call tree with the rectangles that stand for frames of the call stack, ordered by width. Methods that consume more resources are wider than the others.

![Block details shown in the flame graph](ReadTheProfilerSnapshot_img/go_profiler_flamechart_hover.png)


> Native profiling is turned off by default. To enable it, go to Settings | Build, Execution, Deployment | Java Profiler and check the Collect native calls option.

When you read the flame graph, focus on the widest blocks. These blocks are the methods that are presented in the profile most. You can start from the bottom and move up, following the code flow from parent to child methods. If you prefer to examine the flame graph from top to the bottom, use the ![the Presentation Settings button](ReadTheProfilerSnapshot_img/app.actions.show.svg) |Show Icicle Graph option change the graph view.

### Get call details﻿

- Hover over a block to see a tooltip.

  The tooltips show the fully qualified method name, the percentage of the parent sample time, and the percentage of total sample time.

### Zoom the graph﻿

- Use the ![the Zoom in button](ReadTheProfilerSnapshot_img/artwork.studio.icons.common.zoom-in.svg) and ![the Zoom out button](ReadTheProfilerSnapshot_img/artwork.studio.icons.common.zoom-out.svg) buttons or the scroll wheel to zoom the graph.
- To focus on a specific method, double-click the corresponding block on the graph.
- To restore the original size of the graph, click 1:1.

### Search the graph﻿

- If you want to locate a specific method on the graph, start typing its name or click ![Show Search Toolbar](ReadTheProfilerSnapshot_img/artwork.studio.icons.common.search.svg) and type the name in the search bar.

  The graph highlights all blocks with method names matching your search request.

  Use ![Previous Occurrence](ReadTheProfilerSnapshot_img/app.actions.previousOccurence.svg) and ![Next Occurrence](ReadTheProfilerSnapshot_img/app.actions.nextOccurence.svg) for fast navigation between search results. You can also search eiаther in the whole graph or just in a specific subtree.

![Using the search in the Flame Graph tab](ReadTheProfilerSnapshot_img/go_flame_graph_search.png)

### Capture the graph﻿

You can capture and export the graph separately from other data in the snapshot.

- Click ![Capture Image](ReadTheProfilerSnapshot_img/app.actions.dump.svg) and select Copy to Clipboard or click Save to export the graph as an image in the **.png** format.


> For more information about flame graphs, see [Flame Graphs](http://www.brendangregg.com/flamegraphs.html).

You can visualize the difference between two snapshots on the flame graph.

### Compare with a baseline﻿

1. Open two snapshots. To open snapshots, you can run the profiler twice or go to Run | Open Profiler Snapshot and select snapshots here.

2. Click the Compare With Baseline button and select the snapshot that you want to compare against.

   A separate diff tab will open with the results of the comparison, combining two flame graphs and showing the differences as red and green.

   If you see that some part of the frame is green, it means that the corresponding method became faster during this profiler run. The red color means that the corresponding method became slower.

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_compare_with_a_baseline.png](ReadTheProfilerSnapshot_img/go_compare_with_a_baseline.animated.gif)

## Call Tree﻿

The Call Tree tab organizes the sampled data in a tree-like structure.

![call tree tab in the profiler results](ReadTheProfilerSnapshot_img/go_profiler_calltree_mac.png)

For each method, the tab shows the following information:

- Names of methods
- Percentage of total samples or parent's samples
- The total sample count
- [Recursive calls](https://www.jetbrains.com/help/go/read-the-profiling-report.html#recursive-calls)

By default, the percentage is relative to the total number of samples. You can choose to view the numbers relative to the parent frame.

### Switch the percentage between total and parent﻿

- Click ![the Presentation Settings button](ReadTheProfilerSnapshot_img/app.actions.show.svg) and select Show Percent of Total Time or Show Percent of Parent.

### Collapse recursive calls﻿

A stack that involves recursion may be very difficult to analyze. In a regular Call Tree view, recursive calls are displayed as they are called – one after another, which may lead to almost infinite stack scrolling.

GoLand detects recursion when the same method is called higher up in the call stack. In this case, the subtree is taken out of the call tree and then attached back to the first invocation of that method. This way you can bypass recursion and focus on methods that consume most of the resources and calls that they make.

Collapsing recursive calls allows you to see the total amount of time spent in these calls as if there was no recursion.

![Demonstrating collapsed recursive calls](ReadTheProfilerSnapshot_img/collapse-recursion.png)

Folded recursive calls are marked with the ![the Recursion icon](ReadTheProfilerSnapshot_img/app.gutter.recursiveMethod.svg) icon on the Call Tree tab. Click it to open the recursive call tree in a separate tab. You can preview the number of merged calls in a tooltip.

![Unfolding a collapsed recursion](ReadTheProfilerSnapshot_img/go_profiler_recursion.png)

### What-if: focus on specific methods﻿

GoLand allows you to examine specific methods in the Call Tree: you can exclude particular methods or other way round, focus only on the methods in which you are interested at the moment.

Right-click the necessary method on the Call Tree tab and select one of the following options to open the results in a dedicated tab:

- Focus On Subtree: show only the selected method call. Parent method sample counter shows only the time spent in the selected subtree.
- Focus On Call: show the selected method and the methods that call it. When this option is enabled, every frame shows only the time spent in the selected method.
- Exclude Subtree: ignore the selected method call.
- Exclude Call: ignore all calls to the selected method.

![Using the What-if feature](ReadTheProfilerSnapshot_img/go_profiler_what_if.png)

## Method List﻿

The Method List collects all methods in the profile data and sorts them by cumulative sample time. Every item in this list has several views:

- Back Traces shows the hierarchy of callers. Use this view to trace which methods call the selected method.
- Merged Callees summarizes all methods that are called by the selected one.
- Callee List shows all methods that were called from the selected one.

![method list tab in the profiler results](ReadTheProfilerSnapshot_img/go_profiler_methodlist_mac.png)