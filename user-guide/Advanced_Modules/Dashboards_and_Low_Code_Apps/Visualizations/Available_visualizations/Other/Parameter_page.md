---
uid: DashboardParameterPage
---

# Parameter page

This component displays a particular data page of an element.

![Parameter page](~/user-guide/images/Parameter_Page.png)<br>*Parameter page component in DataMiner 10.4.5*

To configure the component:

1. Add an element data feed or a data page feed (recommended). For a data page feed, filter the *Parameters* item in the data pane either by element or by protocol.

1. If you used an element data feed: Click the filter button in the quick menu below the component and add a data page filter feed from the *Parameters* category.

   If you used a data page feed based on element, no additional filter is needed.

   If you used a data page feed based on protocol, an additional element filter feed is needed. You can either directly add this feed from the *Elements* section in the data pane, or use a feed component. See [Applying a data feed](xref:Apply_Data_Feed).

1. Optionally, to customize the polling interval for this component, expand the *Settings* \> *WebSocket settings* section, clear the checkbox in this section, and specify the custom polling interval.
