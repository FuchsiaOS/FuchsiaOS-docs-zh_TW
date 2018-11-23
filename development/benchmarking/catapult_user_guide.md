# Catapult User Guide (Version 1)

* Updated: 2018 July 27

[TOC]

## Overview

The Catapult dashboard is the UI we send benchmark results to for monitoring and
visualization.  The dashboard is maintained by the Chrome team.  This a short guide on how
to find and use the results of your benchmarks in the dashboard.


## Accessing the Dashboard

*** promo
**Be sure to sign into your google.com account or else Fuchsia data will be hidden.**

The login button is in the top right corner of the screen.
***

The dashboard can be found at https://chromeperf.appspot.com/report.

## Searching and Adding Graphs

The dashboard displays a list of search boxes.  The placeholder names are relics from the
days when Chrome infrastructure was still using BuildBot.  Since they are not relevant to
Fuchsia infrastructure, we map our own data into these fields with the following scheme:

* `Test suite` == the name of the benchmark suite.
* `Bot` == A Fuchsia LUCI builder that has run the benchmark at least once.
* `Subtest` == The name of the test case in your benchmark suite.

Type the name of your benchmark suite in the first box to begin searching.   As an
example, we can see the zircon_benchmarks suite if we type "zircon"

![test_suite_example](/images/benchmarking/test_suite_example.png "test_suite_example")

Select a builder and a subtest.  Note that if your subtest is named "foo", there will be
multiple "foo_<metric_name>" subtests to choose from.  Each of these represents a metric
computed from the sample(s) of that subtest.   For example: if "foo" generates N sample
points each time the benchmark is run, then the subtest "foo_avg" is a plot of the
averages of these N samples.

When you're finished filling out each field, click "Add" to add your graph to the UI.
You should see something like this:

![graph_example](/images/benchmarking/graph_example.png "graph_exmaple")


## Viewing sample metadata

If you hover over a point in a graph, you can see some extra information such as the
point's value, the date it was recorded, and a link to the log page of the build that
generated it.

![tooltip_example](/images/benchmarking/tooltip_example.png "tooltip_example")


## Saving the View

v1 of the Catapult dashboard UI does not have a built in mechanism for saving a collection
of Graphs.  If you want to save a list of graphs so that you can share with others or
re-open the list later, you can copy the URL from the Chrome Address Bar.

Beware, you will have to re-copy the URL each time you add, modify or remove a graph. This
includes moving the green slider beneath a graph or making any selections in the box to
the right of the graph.


## Enabling Regression Detection

To enable regression detection, you must enable "monitoring" for a test by clicking the
"Request Monitoring for Tests" button under the "Report issue" dropdown at the top of the
page.

![monitoring_button_example](/images/benchmarking/monitoring_button_example.png "monitoring_button_example")

This will open a bug form you can fill out to enable monitoring for a benchmark.  The
Chrome team has a Sheriff rotation (oncall rotation) to triage regression alerts.  The
dashboard only allows triaging bugs in monorail, so we'll have to make due without JIRA
support.

See this link for more information about the [Sheriff rotation]

[Sheriff rotation]: https://chromium.googlesource.com/chromium/src/+/master/docs/speed/perf_regression_sheriffing.md
