---
uid: Executing_actions_via_URL
---

# Executing actions via the app URL

From DataMiner 10.3.6/10.4.0 onwards<!-- RN 35979 -->, you can make an app execute one or more actions by adding the action configuration to the app URL. This can for instance be used to make an app embedded in Visual Overview execute actions.

## Configuration

1. Configure the actions in the action editor.

1. Click the *Copy actions* button to copy the action configuration to the clipboard as a JSON object.

1. Add `#{"actions": }` to the URL, and paste the copied JSON object between the colon (`:`) and the closing bracket (`}`).

The actions you have added will immediately be executed when the URL is loaded.

As soon as the actions have been executed, the action configuration will be removed from the URL, so that they do not get executed multiple times.

> [!NOTE]
>
> - Making an app execute actions by adding a configuration to its URL does not work while that app is in edit mode.
> - Currently, the following actions cannot be executed this way for security reasons:
>
>   - *Launch a script*
>   - *Execute component action: delete current instance/save current changes*
>   - *Navigate to a URL*

> [!IMPORTANT]
> To guarantee support across all browsers and prevent possible issues, the URL value should be encoded. If, for example, the JSON structure contains any ampersands ("&"), this will not work unencoded.

## Example

In this example, an *Open a panel* action is added to an app URL:

```txt
https://myDMA/APP_ID/PAGE_NAME#{"actions":[{"Type":6,"__type":"Skyline.DataMiner.Web.Common.v1.DMAApplicationPagePanelAction","Panel":"4507edc7-fcee-47bd-985c-f40d844e72cb","Position":"Center","Width":30,"AsOverlay":true}]}
```

> [!NOTE]
> For the example above, this is the encoded equivalent: `https://myDMA/APP_ID/PAGE_NAME#%7B%22actions%22%3A%5B%7B%22Type%22%3A6%2C%22__type%22%3A%22Skyline.DataMiner.Web.Common.v1.DMAApplicationPagePanelAction%22%2C%22Panel%22%3A%224507edc7-fcee-47bd-985c-f40d844e72cb%22%2C%22Position%22%3A%22Center%22%2C%22Width%22%3A30%2C%22AsOverlay%22%3Atrue%7D%5D%7D`
