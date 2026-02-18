+++
title = "Privacy Information"
path = "privacy"
updated = 2026-02-18T17:15:00+00:00

[extra]
meta = [
    {property = "og:title", content = "Privacy Information & Advice"},
    {property = "og:description", content = "This page describes how and when personal data is collected from your visit to this site."},
    {property = "og:url", content = "https://blog.jglass.me/privacy/"},
    {property = "og:type", content = "website"},
    {property = "og:image", content = "cover.png"},
]

tldr = "I do not collect any information from your visit to this site. Your preference between light and dark themes is saved locally in your browser. GitHub may retain your IP address for 'security purposes'."
+++

# Data I Collect

I do not collect any information, personally identifiable or otherwise, from your visit to this site.

I have no idea how many people have visited this site, nor that you specifically have done so.

External analytics code has been [removed](https://github.com/Jordan-Glass/shuttle/commit/e92ffc9c6390b923b2575208a244ecb394da4b16) from the site's theme so that it cannot be inadvertently included.

# Data Third Parties Collect

## GitHub

GitHub (GitHub, Inc. or GitHub B.V.) logs and stores your IP address when you visit this site. An IP address identifies your device or network on the Internet so that content can be sent back to you. Using your IP address is essential to serve you this website and privacy notice.

GitHub also stores and uses your IP address for "security purposes". This may involve analysis for "abuse detection, prevention, and violations of terms of service". It is unclear how long they retain it for, or if and how you can request its deletion.

Whether your IP address identifies you depends in part on whether your Internet Service Provider shares it with other customers. In any case, it may reveal your approximate location.

For more information, see [About GitHub Pages: Data collection](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages#data-collection) and the [GitHub General Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement), limited in scope to your IP address as used for security purposes.

**How to exercise data rights**: if you have legal rights regarding personal data, contact [privacy@github.com](mailto:privacy@github.com).

**General queries**: if you have queries regarding GitHub's use of data or compliance with relevant laws and regulations, contact [dpo@github.com](mailto:dpo@github.com).

## Next Visited Websites

Websites may log the address of the site that you visited immediately prior using the [HTTP referer header](https://en.wikipedia.org/wiki/HTTP_referer). Therefore, by clicking a link on this site, that site may record that this site sent you there.

Such use is governed by that site's privacy policy. No information is returned to me and I have no knowledge of which links you click, nor how you found this site.

**How to check what data is being collected**: if the website in question has a privacy policy, check it to see if you can exercise your right to access (if applicable). Alternatively, use a tool such as [this one](https://alexloth.com/referrer-checker/) to see what is contained in your referer header.

**How to prevent future data collection**: in Firefox, go to `about:config` and set `network.http.sendRefererHeader` to `0`. For Chrome, [launch it with the `--no-referrers` flag](https://superuser.com/a/1497461). Some websites may not work with this change in effect.

## Social Platforms and Apps

Social media services may track which links you click and how you interact with those websites, [particularly if you use their mobile apps](https://krausefx.com/blog/ios-privacy-instagram-and-facebook-can-track-anything-you-do-on-any-website-in-their-in-app-browser). Such use is governed by their privacy policy.

**How to check what data is being collected**: if the social media service has a privacy policy, check it to see if you can exercise your right to access (if applicable).

**How to prevent future data collection**: open links, or the social media service itself, in your browser of choice, not their app. This may prevent interaction data being collected, but they could still see that you clicked the link.

## External Resource Providers

No external resources are loaded. Therefore, no third-party servers are contacted during the loading of this site. All references to them [have been removed](https://github.com/Jordan-Glass/shuttle/commit/9408931e2ccedf5036d31405e362b08b1de7ef81) from the theme template to ensure they are never included in this site.

# Interactivity

## Theme Preference Storage

This site allows you to toggle between light and dark themes, and to save your preference in your browser's local storage with the key `theme-storage` and a value of `light` or `dark`. It is managed by [`themetoggle.js`](/js/themetoggle.js).

This preference exists solely in your browser and is never sent elsewhere. Your browser may retain, synchronise or backup this preference according to its privacy policy.

On each page load, the theme is set to the preference in your browser's local storage. If it doesn't exist (such as on your first visit), it will be set to `dark` if your browser indicates you have dark mode enabled, or `light` in all other cases. Upon clicking the theme toggle button, the preference is set to the opposite of the current value.

**How to erase stored data**: use your browser's utility to clear cookies and site data (this is usually in or near the URL bar) or use developer tools to clear local storage.

**How to prevent future data collection**: disable JavaScript for this site.

## Scripts

This site contains a number of other scripts for enhanced functionality. None of them send data to me or anyone else.

- [`codeblock.js`](/js/codeblock.js) shows code I include in my posts in distinct boxes, and allows you to copy it. It defines, adds and positions the copy buttons, writes to your clipboard when you click one, and adds the code language label.
- [`note.js`](/js/note.js) shows and hides an expandable note's contents when clicked.
- [`toc.js`](/js/toc.js) determines the headings on each page, and which heading each paragraph belongs to, to show you a table of contents that highlights where you are (this is not visible on mobile).