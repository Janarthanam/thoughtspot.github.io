---
title: ["5.0 Release Notes"]
toc: false
keywords: "release notes"
last_updated: 04/09/2020
sidebar: mydoc_sidebar
permalink: /:collection/:path.html
---
ThoughtSpot version 5.0.x is now available.

These are the new and enhanced features in this release. For a complete list of issues that we fixed in this release, see [Fixed issues]({{ site.baseurl }}/release/fixed.html).

<ul>
   <li><a href="notes.html#supported-upgrade-paths">Supported upgrade paths</a></li>
   <li><a href="notes.html#5-0-new-features-and-functionality">5.0 New Features and Functionality</a></li>
</ul>


<h2>Supported upgrade paths</h2>

<p>If you are running one of the following releases, you can upgrade to this release directly.</p>
<ul>
<li>4.4.1.x to 5.0</li>
<li>4.5. to 5.0</li>
<li>4.5.1.x to 5.0</li>
</ul>
<p>(This includes any hotfixes or customer patches on these branches.)</p>
<p>If you are running a different version, you need to do a multiple pass upgrade. First, upgrade to one of the above versions, and then to this release.</p>

<p><a name="5-0-new-features-and-functionality"></a></p>
<h2>5.0 New Features and Functionality</h2>
<h4><a name="Searchiq"></a>SearchIQ</h4>
<p>SearchIQ is a different search experience that understands more natural, speech-like search language than the current search function. For example, a user could search for “What was my top selling product last month?”, instead of having to type “top 1 product by sales last month”. You can also speak your search using the voice-to-text capability of your operating system.</p>

<p>You can easily teach SearchIQ your language as you use it. Over time, it gets smarter about how to interpret terms that don’t come directly from column names or values. In order to give it time to learn, the best practice recommendation is to enable SearchIQ for a small group of users. Over time you can roll it out to larger groups as SearchIQ learns what your users search for the most.</p>

<p>SearchIQ is turned off by default, but you can enable it by asking ThoughtSpot Support to turn it on for your cluster. For each group that should have access to the SearchIQ experience,
you’ll need to grant them the “Can use experimental features” permission.</p>
<h4><a name="Worksheetfilters"></a>Worksheet filters</h4>
<p>You can now add filters to a worksheet to limit the set of data it contains.
This is useful when you have underlying tables that store more data than necessary
for the types of analyses the worksheet is intended for.
You can also use worksheet filters to provide data security when you have different groups
of users that are trying to access different types of data without relying on row level security.</p>
<h4><a name="SearchresponsetoEnterkey"></a>Search response to Enter key</h4>
<p>The way the system responds to the user typing the Enter key has changed. The system can now resolve an exact match even if there are other partial matches or the suggestions have not returned from the server yet. These changes result in a more natural search experience that allows advanced users to get search results quicker.</p>
<h4><a name="Improvementsinthevisualizationconfigurationworkflowandydesign"></a>Improvements in the visualization configuration workflow and design</h4>
<p>Switching from table to chart is now a toggle button rather than two separate icons. To change the chart type, you now use a separate button. This makes changing the chart type more intuitive.</p>
<img style="border: 0px solid black;" src="{{ "/images/notes/chart_table_toggle.png"| prepend: site.baseurl }}"/>

<p>The chart configuration icons now appear in a vertical panel, to the right of the visualization.
This provides a cleaner look, and more real estate to display the visualization. The more information icon has also been moved to this panel.
The style icon has been added for easy access to setting display properties, including colors.</p>
<img style="border: 0px solid black;" src="{{ "/images/notes/chart_configuration_icons.png"| prepend: site.baseurl }}"/>
<h4><a name="Excludefilters"></a>Exclude filters</h4>
<p>When defining a filter for a column or worksheet, you can now choose values to
exclude as well as to include. In past releases, it was difficult to create a "not equals" filter. Now you can define an exclude filter in any of these ways:</p>
<ul>
<li>by choosing from a list of values</li>
<li>by adding a bulk exclude filter</li>
<li>by using != operator in the search bar</li>
</ul>
<h4><a name="Searchranking"></a>Search ranking</h4>
<p>The rules that determine the ranking of search suggestions have been adjusted to more closely
match what most users expect.
For example, suggestions that match what you've
typed so far can move up in the suggestion ranking, but not down.
Suggestions that match the beginning of what you're typing appear
higher than ones that have a match in the middle of a phrase.
These changes make suggestions more useful and the search experience more intuitive.</p>
<h4><a name="Flexibleaggregations"></a>Flexible aggregations</h4>
<p>The 5.0 release introduces flexible aggregations to enable you to aggregate measures
  using filters and aggregation dimensions that might be different from the ones that
  are used in the search. For example, you might need to compare yearly sales against
  the monthly sales for each product category or you might need to compare against
  the total sales of only active products.
</p>

<h4><a name="FlexibleJoinsinWorksheets"></a>Flexible Joins in Worksheets</h4>
<p>This version of ThoughtSpot introduces flexible join types to give you more options and an easier workflow to model joins between tables, views, and worksheets and within worksheets.</p>
<p>You can now specify the join type separately for each join between tables in a worksheet. You can also create generic relationships between tables without leaving the worksheet creation workflow within the ThoughtSpot application.</p>
<p>In past versions, there were several limitations on joins:</p>
<ol>
<li>It was hard to see the effective schema when creating or editing a worksheet.</li>
<li>You could only specify one type of join (inner, outer, etc.) per worksheet, and that join type would be applied to all table joins in the worksheet.</li>
</ol>
<p>This limited the use of worksheets such that they couldn&rsquo;t be applied to some use cases. For example, sometimes two tables in a worksheet required a full outer join between them, while two others required an inner join. Now you can create this type of worksheet, and all the joins to support it, in a single workflow.</p>
<p>Now you can specify join type for each relationship in a worksheet, using one of these types:</p>
<ul>
<li>Full outer join</li>
<li>Left outer join</li>
<li>Right outer join</li>
<li>Inner join</li>
</ul>
<p>In ThoughtSpot, the fact or source table is the &ldquo;left&rdquo; table, and the dimension (target or destination) table is the &ldquo;right&rdquo; table. You can now easily see which is the left table and which is the right table when you&rsquo;re setting up the join types.</p>

<h4><a name="AddedtheabilitytoaddcustomHelplinks"></a>Added the ability to add custom Help links</h4>
<p>When users click the help icon, they see a list of links. You can now add your own links to this list. This allows you to include documentation specific to your company, such as information about the data available in ThoughtSpot, where to get support internally, or company-specific training.</p>
<img style="border: 0px solid black;" src="{{ "/images/notes/custom_help_item.png"| prepend: site.baseurl }}"/>
<p>You can also edit existing links, change icons, or remove items from the help listing altogether.</p>

<h4><a name="Stylecustomizationoptionsareenabledbydefault"></a>Style customization options are enabled by default</h4>
<p>In the past, to enable style customization&mdash;colors, fonts, and custom logo&mdash;you had to contact ThoughtSpot Support. With this release, style customization features are enabled by default for users with the Administrator privilege. If you want to disable these settings, contact ThoughtSpot Support.</p>
<img style="border: 0px solid black;" src="{{ "/images/notes/style-customizations.png"| prepend: site.baseurl }}"/>


<h4><a name="Supportforipsecbetweenclusternodes"></a>Support for IPSec between cluster nodes</h4>
<p>With 5.0, you can encrypt traffic between various ThoughtSpot cluster nodes. However, by default the encryption of traffic between ThoughtSpot nodes is disabled. When required to enable on a specific cluster, contact ThoughtSpot Support. ThoughtSpot can enable encryption of traffic between ThoughtSpot nodes to allow this feature to automatically work on Amazon Web Services (AWS), Google Cloud Platform (GCP), OnPrem, or Microsoft Azure.</p>

<h4><a name="Embeddedsearchapi"></a>Embedded Search API</h4>
<p>The Embedded Search API enables searching directly from an external application or web page to pull data from ThoughtSpot. When using this API, you can access data stored in ThoughtSpot directly. You do not need to save a search result to a pinboard and then reference it using the visualization’s URL.
This embedded search is useful when you want to allow an application to pull data directly from ThoughtSpot in an ad hoc fashion.
To have the Embedded Search API functionality turned on, contact ThoughtSpot Support.
</p>

<h4><a name="URLlinksindatavaluescannowopeninthesametaboriFrame"></a>URL links in data values can now open in the same tab or iFrame</h4>
<p>In past versions, clicking a URL link in an answer would open the URL in a new tab. Similarly, for an answer embedded in an iFrame, clicking on a URL opened it in a new tab. This is still the default behavior, but you can configure ThoughtSpot to open the link in the same context where it appears.</p>
<p>Now you can change a cluster-wide setting to make links open in the same context (iFrame or tab) in which they appear. With this configuration, if the ThoughtSpot answer is embedded in an iFrame, clicking the URL will open it within the same iFrame. If you are using the ThoughtSpot application the link will open in the same tab.</p>
<p>This setting applies to an entire ThoughtSpot instance. So if it is set to open URLs in the same tab, all URL links whether in the application or in an embedded visualization will open in place. Contact ThoughtSpot Support if you would like them to change this setting for you.</p>

<h4><a name="Patchsupportforupdates"></a>Patch support for updates</h4>
<p>The 5.0 release adds support for applying patches using the <code>tscli</code> command. With this patch support, you do not need to upgrade the entire cluster when there is a bug fix, security fix, or minor feature you want to install. It also provides the ability to apply or rollback a patch and to see any patches that have been applied cluster-wide or listed out by service. To see the list of patches applied currently on a cluster, run the following commands:</p>
<p><code>tscli patch ls</code></p>
<p>To see a list of all patches that have ever been applied, including any that were rolled back, issue the command:</p>
<p><code>tscli patch ls --applied</code></p>
<p>Additional command flags allow you to see the listing by service or to view all patch rollbacks.</p>
<p>To install a patch, contact ThoughtSpot Support.</p>

<h4><a name="PinboardInstantInsights"></a>Pinboard Instant Insights</h4>
<p>With the 5.0 release, you can now automatically view the executive summary of insights for each SpotIQ Pinboard visualizations. Use the magic wand icon (at the top right corner) to see instant insights of your data. The instant insights are generated based on the analysis of visualizations and tables which are pinned on to your pinboard.</p>
<p>Note that the instant insights are cached. It means if you ran SpotIQ analysis on a pinboard to generate insights, you do not need to rerun SpotIQ analysis.</p>

<h4><a name="Abilitytoincludeorexcludevalues"></a>Ability to include or exclude values</h4>
<p>Filters on columns, pinboards, and worksheets now give you the ability to include or exclude values. In past releases, you could only choose values to include. This change makes it easy to see all values except for one or more values. Bulk filters also work with exclude.</p>
<p>When selecting a filter from a list of values, the null value is now available for filtering. You can choose to include or exclude the null value. This allows you to easily see where null (missing) values exist in the data. This can be helpful when looking for dirty or incomplete data.</p>

<h4><a name="colorchart"></a>Change the color on single color charts</h4>
<p>When a chart consists of a single color, you can now change the color. To do this, select the chart style icon to the right of the chart. Under the Color section, use the color picker to choose which color to use for the chart.</p>

<h4><a name="Stackedbarchart"></a>Stacked bar chart</h4>
<p>Stacked bar chart, a new chart type, is the equivalent of stacked column charts,
but with a horizontal orientation. Some types of data are easier to understand
when shown in a stacked bar rather than a stacked column chart.</p>

<h4><a name="Latestupdatestotableformatting"></a>Latest updates to table formatting</h4>
<p>Tables have a new look! The new table formatting makes data more accessible to see because the columns are sized better, text wraps more cleanly, and there is additional white space between rows. To adjust the column width, try clicking and dragging between columns.</p>
<img style="border: 0px solid black;" src="{{ "/images/notes/new_table.png"| prepend: site.baseurl }}"/>

<h4><a name="Datapushapi"></a>Data Push API</h4>
<p>The Data Push API allows you to open a web page in the context of the ThoughtSpot application. This third party web page will then have access to the results of the ThoughtSpot search from which it was invoked. This is useful when you want to initiate an action in another application based on the result of a search in ThoughtSpot.
An example of pushing data to another system to trigger an action would be where you do a search to find customers who are coming due for renewal of their contract in the next month. You could then trigger an action that brings up a web page from an external billing system. The billing system could be set up to read the data (list of names, emails, products, and renewal dates) from ThoughtSpot. The billing system might then add the price, generate an invoice for each customer, and send it out via email.
To have the Data Push API functionality turned on, contact ThoughtSpot Support.
</p>

<h4><a name="CustomRScriptsOnSearchResults"></a>Custom R scripts on search results</h4>
<p>The ability to add custom R scripts is now available as part of the Search page.
In previous releases, custom R scripts were an option only on SpotIQ custom analysis.
Starting in version 5.0, given R privileges, you can create and run R scripts on search
results (answers),leverage ThoughtSpot provided scripts, share scripts as templates, and
share R visualizations as answers and pinboards. End users with privileges can run pre-built R
scripts on top of their search results.</p>
<img style="border: 0px solid black;" src="{{ "/images/notes/r-icon.png"| prepend: site.baseurl }}"/>
<img style="border: 0px solid black;" src="{{ "/images/notes/r-png-result.png"| prepend: site.baseurl }}"/>
<h4><a name="Introducingmaterializedviews"></a>Introducing Materialized Views</h4>
<p>Views are new in version 5.0, and they are similar to aggregated worksheets or search saved as a worksheet. With this release, views can be materialized to provide better performance. After creating a view, you can choose to materialize the view, which helps precompute the view and store it in memory along with the data. You can refresh the view manually or on a set schedule to keep it in synch with the underlying tables as their data is refreshed.
Note: Once materialized, a view does not respect row-level security. So all users of the view will be able to see all the data it contains.</p>
<h4><a name="Newlanguagesupport"></a>New Language support</h4>
<p>Starting in the 5.0 release, the following new locales are supported on the UI including support for
language keywords that can be used in the search bar:</p>

<ul><li>French-France</li>
<li>French-Canada</li>
<li>Spanish-Latin American</li>
<li>Chinese-Simplified</li>
<li>Portuguese-Brazil</li>
</ul>

<h4><a name="SpotIQAutomatedInsightsonthehomepage"></a>SpotIQ Automated Insights on the homepage</h4>
<p>On the homepage, there is now a section called <strong>Did You Know?</strong>, which shows insights found by SpotIQ. To find these insights, SpotIQ runs many analyses of the data used in recent searches. The results which are most likely to contain useful insights are included in this section. This helps users get more value from their data and learn about areas where you may want to do further exploration.</p>
<h4><a name="NewLeaderboardpinboard"></a>New Leaderboard pinboard</h4>
<p>The out-of-the-box pinboard called <code>TS Stats: System Information and Usage</code> now contains leaderboard visualizations. These show which users are most active, and what kinds of things they're doing in ThoughtSpot.</p>
<img style="border: 0px solid black;" src="{{ "/images/notes/leaderboard_pinboard.png"| prepend: site.baseurl }}"/>

<p>Some of the new visualizations show:</p>
<ul>
<li>Which users were most active in the last month</li>
<li>Which pinboards are viewed most often</li>
<li>Which users have initiated the most all-time ad-hoc searches</li>
<li>Which users have been active today</li>
<li>Number of monthly active users (MAU)</li>
</ul>
<p>This leaderboard increases engagement within your user community and helps you identify the people who are the most skilled and frequent ThoughtSpot users.</p>

<h4><a name="Newdefaultsnapshotpolicy"></a>New default snapshot policy</h4>
<p>This release includes a new default snapshot policy. Three snapshots are taken over 4-hour intervals in the course of a day. And 4 daily snapshots are taken. This provides continuity over the long weekends in many countries by ensuring snapshots on Saturday, Sunday, Monday, and Tuesday.</p>

<h4><a name="LearnThoughtSpotinGA"></a>Learn ThoughtSpot in GA</h4>
<p>The Learn option from the main menu has moved from a BETA to a GA feature. Learn uses replay to teach users how to perform search with ThoughtSpot.</p>

<h4><a name="Relatedanswers"></a>Related answers</h4>
<p>Related Answers now appear as cards at the bottom of the search results. This is less distracting when searching and makes these saved searches stand out as distinct from search suggestions.</p>

<h4><a name="Localizeddateformatsupportedinsearchfilters"></a>Localized date format supported in search filters</h4>
<p>The search bar now accepts dates in the format used by the user browser's locale setting. For example, European locales accept dates using formats like DD-MM-YYYY. The US locale accepts dates using formats like MM-DD-YYYY.</p>
<h4><a name="Fiscalcalendarindateformulas"></a>Fiscal calendar in date formulas</h4>
<p>Several date functions now support the ability to indicate either a <code>fiscal</code> or Gregorian calendar (<code>calendar</code>) on which to base date calculations.  If no calendar type is specified, formulas default to standard Gregorian, with the year starting in January.</p>
