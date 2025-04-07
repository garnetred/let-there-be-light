# Let There Be Light

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/decemberthedeveloper)

## Abstract

This Chrome browser extension attempts to thwart clickjacking attempts by setting the opacity of any iframe to 1.

## Background

[Clickjacking](https://en.wikipedia.org/wiki/Clickjacking) is when an invisible website is laid on top of a decoy website to trick the user into clicking on elements without realizing it. For example, an invisible iframe containing a user's profile page with a delete account button can be hidden on top of a video of cute kittens. When the user clicks to watch the video, they will unintentionally click the "delete account" button. The browser believes the user intends to do this action, so the account is deleted and the attack can go undetected. There are a few ways developers can circumvent this issue, but sometimes these can be easily evaded by an attacker. 

In order for this attack to work, the iframe needs to be invisible to the user. Some browsers will not show any iframes with an opacity of 0 (which would make them completely invisible), so instead attackers will set the opacity as close to 0 as possible (ex. 0.0001). This extension attempts to minimize the effectiveness of this type of clickjacking by setting the opacity of all iframes on every website to 1.  It will not work for clickjacking attacks that are structured differently. It works by overriding the opacity of the given website, revealing the hidden site to the user. Hopefully this would cause users to avoid the clickjacking attack. Notably this will force all iframes on every website a user visits to be opaque. 

## Example

### Before
<img width="707" alt="Screen Shot 2025-04-07 at 2 08 58 AM" src="https://github.com/user-attachments/assets/686edd29-e419-4b78-b996-80c28f5432de" />
A login page on top of a decoy page that says "click me" to trick a user into deleting their account. For the purposes of this exercise the opacity of the iframe (login page) is `0.1`.

<img width="592" alt="Screen Shot 2025-04-07 at 2 09 16 AM" src="https://github.com/user-attachments/assets/3c02806a-25f6-4121-a968-e3d35450d246" />
Here the opacity is `0.0001`, rendering it effectively invisible. Some browsers will protect against iframes with an opacity of 0, so the number is as close as possible to avoid detection.


### After

<img width="502" alt="Screen Shot 2025-04-07 at 2 09 42 AM" src="https://github.com/user-attachments/assets/4de5962b-d802-4cf9-8704-3dc9288b7633" />
Here the extension is running, so the default opacity for all iframes is 1. The iframe is clearly visible to the user and the "click me" div is no longer visible because it's beneath the iframe.

## Tech Stack

This project uses vanilla JS, CSS, and HTML.

## Setup/Installation

You can clone the repo locally using `git clone git@github.com:garnetred/let-there-be-light.git`.

Without using a terminal you can also visit the project homepage, select the green button that says "code" and then click the option to "Download zip." From there you'll need to unzip the folder before following the rest of the instructions.

### Chrome (and other Chromium-based browsers)

[This article](https://developer.chrome.com/docs/extensions/mv3/getstarted/development-basics/#load-unpacked) offers detailed instructions on loading an unpacked chrome extension. You can navigate to the chrome extensions page via the lightbulb icon in the toolbar. Enable "developer mode" on the top-right. From there, you can click "load unpacked extension" and choose the folder via the popup. You should then see the lightbulb icon appear in the toolbar. When you click on it, you can see a popup that reads "Let There Be Light."

You can test the web page using one of Portswigger's Web Security Academy's clickjacking labs such as the [Basic Clickjacking with CSRF Protection lab](https://portswigger.net/web-security/clickjacking/lab-basic-csrf-protected).

## Future Changes
Eventually I plan to port the extension to Firefox.

## Attribution


