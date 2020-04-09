---
title: ["5.1 Release Notes"]
toc: false
keywords: "release notes"
last_updated: 04/09/2020
sidebar: mydoc_sidebar
permalink: /:collection/:path.html
---

ThoughtSpot version 5.1.4 is now available. These release notes include information about new and enhanced features.

For a complete list of issues that we fixed in this release, see [Fixed issues]({{ site.baseurl }}/release/fixed.html).

* [Supported Upgrade Paths](#supported-upgrade-paths)
* [Mobile App](#mobile-app)
* [5.1.1 New Features](#511-new)
* [5.1 New Features](#51-new)

## Supported Upgrade Paths

If you are running one of the following versions, you can upgrade to the 5.1.4 release
directly:

* 4.5.1.x to 5.1.4
* 5.1.x to 5.1.4

(This includes any hotfixes or customer patches on these branches.)

If you are running a different version, you must do a multiple pass upgrade.
First, upgrade to one of the above versions, and then to the 5.1.4 release.

## Mobile App

ThoughtSpot mobile app version 1.1 is now available! For more information, see [ThoughtSpot mobile overview]({{ site.baseurl}}/admin/mobile/use-mobile.html)

Version 1.1.2 now supports auto-redirect Single Sign-On (SSO) for clusters with SSO enabled.

For more information, see [Mobile]({{ site.baseurl }}/admin/mobile/use-mobile.html#).

{: id="511-new"}
## 5.1.1 New Features and Functionality

For a complete list of issues that we fixed in this release, see [5.1.1 Fixed issues]({{ site.baseurl }}/release/fixed.html#5-1-1).

### Data visualization color refinements

Visualization colors have been refined to match ThoughtSpot's fresh, new look. You can still customize colors, and reset them to the default color palette later, if needed.

{: id="51-new"}
## 5.1 New Features and Functionality

For a complete list of issues that we fixed in this release, see [5.1 Fixed issues]({{ site.baseurl }}/release/fixed.html#5-1).

### Quick Select

When you type a phrase or a letter in the search bar, the first suggestion is
automatically highlighted and you can press Enter to select it ([Quick Select]({{ site.baseurl }}/end-user/search/about-the-search-bar.html)). Suggestions can be an attribute, measures, value, keyword, historical queries,
or exactly what you typed as the search phrase. Historic suggestions always
display on top with the first suggestion highlighted as default.  If there are
no suggestions, the suggestion list is not be displayed.

### Improvements in the presentation mode experience of pinboards

When you display pinboards charts on projectors in conference rooms and on a
laptop that has a widescreen display, the display automatically adjusts itself
depending on the size of the display screen. For example, if you are using a
widescreen display, pinboard font size increases for a more definitive and
high-quality experience.

1. Choose a pinboard that you want to display and click the **present** icon ![present icon]({{ site.baseurl }}/images/icon-present.png){: .inline} (top-right).

   Alternatively, you can click the ellipses ![more options menu icon]({{ site.baseurl }}/images/icon-ellipses.png){: .inline} and select **Present**.

2. Use the **Up** and **Down** arrow keys to navigate.

### Stable search suggestions

Search suggestions are now more stable. When you start to type a search phrase and
the full matching phrase appears in the results list, the order in which it
appears does not change as you finish typing it.

### Show rounded or non-rounded numbers on charts

You can set labels on charts to [show rounded or non-rounded numbers]({{ site.baseurl}}/end-user/search/show-data-labels.html#show-rounded-or-non-rounded-numbers).

### Pie charts now support color customization

You can now [customize the colors of each slice on pie charts]({{ site.based}}/end-user/search/change-chart-colors.html#set-pie-chart-slice-colors) from the chart Styles panel. Click the Styles button next to any pie chart to get started (![paintbrush icon]({{ site.baseurl }}/images/icon-paintbrush.png){: .inline}).

### Longer pinboard descriptions

Table or chart descriptions in a pinboard can now be up to two lines long.
Descriptions that exceed a second line are truncated with three periods (...) at
the end. Headline tiles (which don’t have a table or chart) are limited to a
one-line description.

### New typography in the desktop app

With the 5.1 release, the fonts used are Optimo Plain and BB Roller Mono. This
provides a modern, more readable look for the ThoughtSpot application user
interface and data visualizations.

### Table aggregate headline

The Table Aggregate headline option is available when an aggregate function is
used in a table either through a formula or a search bar query, like the average
of a measure. It recalculates the function for the entire table. In such cases,
the Table Aggregate is shown by default below the table, instead of the “Avg”
option, which does a second level of aggregation on top of the existing
aggregation.

### Period to date

Before 5.1, Period to Date didn't work in conjunction with other date filters.
With this release, you can compare data spread across the same period and drill
down to a specific period of a year, month, week, and date.

For example, you can compare:

* `quarter to date vs last year quarter to date`
* `month to date vs last month to date`
* `year to date vs last year month to date`
* `week to date vs last quarter week to date`

To review date keywords, see [Date in keywords reference]({{ site.baseurl }}/reference/keywords.html#date).

For more about `vs` keyword, see [Comparative in keywords reference]({{ site.baseurl }}/reference/keywords.html#comparative)

### Case sensitivity on formulas is supported

You can now enable case sensitivity when defining formulas, and the final
formula output retains the case sensitive state. Quoted text in a formula can
now be case-sensitive. For example, "`if revenue > 1000 then 'Good' else 'Bad'`".
The output of this formula retains the case.

### SpotIQ personalization

Users can specify "Insight Threshold Settings" as part of their individual
profile [SpotIQ preferences]({{ site.baseurl}}/end-user/introduction/about-user.html#spotiq-preferences-and-email-notifications) to further refine the parameters SpotIQ uses.
SpotIQ profile preferences are a subset of those available on the SpotIQ "Customize
analysis dialog", and persist for all SpotIQ analyses, unless you explicitly
reset options for custom analyze.

### Improved search editing

You can edit a search without affecting existing search results. You can insert a new phrase or edit an existing one in the middle of a search without causing any errors. You can even merge words or phrases without breaking the search. As you edit your search, ThoughtSpot continuously generates new results.

### Copy and edit

The previous feature called "Make a Copy" is now called "Copy and Edit" and it brings a major workflow improvement. Instead of simply saving a copy in the background, "Copy and Edit" allows you to make a copy of an answer, pinboard visualization, insight, SpotIQ pinboard or view and immediately start editing it.

### SpotIQ insight feedback

Administrators can save user feedback and use it to suppress down-voted insights
from auto or custom SpotIQ analyses.

### SpotIQ column level data modeling

Data modelers and administrators can [exclude columns from SpotIQ analyses]({{ site.baseurl }}/admin/data-modeling/spotiq-data-model-preferences.html) via a
new `SPOTIQ PREFERENCE` option on the Data tabs for worksheets, tables or views.
By default, all columns are included in SpotIQ analyses.

### Schema Viewer available to non-admin users

Starting in the 5.1 release, you can grant non-admin users with
[Can manage data]({{ site.baseurl}}/admin/users-groups/about-users-groups.html)
privilege access to [Schema Viewer]({{ site.baseurl}}/admin/loading/schema-viewer.html).
This enables non-admin users to view data in a schema they have access to.

### Active Directory (AD) management for ThoughtSpot nodes

ThoughtSpot supports enabling [Active Directory (AD) based access]({{ site.baseurl}}/admin/setup/active-directory-based-access.html) individually on
each node where the commands are run. To enable AD access on a cluster, the
administrator must run the same commands on each individual node and on any
additional nodes added to the cluster.

### Keyword support for eight new languages / locales (Beta)

Beta mode [internationalization (I18N) keywords support]({{ site.baseurl}}/reference/keywords.html) for the following additional locales is available in version 5.1:

* Español (España)
* Português (Portugal)
* Italiano
* Dansk
* Suomi
* Svenska
* Norsk
* Nederland
