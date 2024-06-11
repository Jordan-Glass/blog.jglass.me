+++
title = "Privacy Info & Advice"
path = "privacy"
updated = 2024-06-11T10:50:00Z

[extra]
meta = [
    {property = "og:title", content = "Privacy Information & Advice"},
    {property = "og:description", content = "This page describes how and when personal data is collected from your visit to this site."},
    {property = "og:url", content = "https://blog.jglass.me/privacy/"},
    {property = "og:type", content = "website"},
    {property = "og:image", content = "cover.png"},
]

tldr = "I do not collect any information from your visit to this site. Your preference between light and dark themes is saved locally in your browser. GitHub may collect and retain your IP address for 'security purposes'."
+++

# Data I Collect

I do not collect any information, personally identifiable or otherwise, from your visit to this site.

I have no idea how many (or few) people have visited this site, nor that you specifically have done so.

To further guarantee that this remains the case, external analytics code has been [removed](https://github.com/Jordan-Glass/blog.jglass.me/commit/105377ae7a9aa6e3da8e36e83c8c1ab55d9c7acb) from the site's theme so that it cannot be inadvertently included and published.

# Data Third Parties Collect

## GitHub

GitHub (GitHub, Inc. or GitHub B.V.) logs and stores your IP address when you visit this site. An IP address identifies your device or network on the Internet, so that requested content (such as text and images) can be sent to the correct destination. The server you're requesting this content from needs to know about this IP address to send the content back to you.

Therefore, collecting your IP address is necessary to provide you with the service (enabling the site and, therefore, this privacy policy to be sent to your device as requested - it would be impossible to load this privacy policy without knowledge of your IP address). GitHub also stores and uses your IP address for "security purposes". This may involve automated and manual analysis for "abuse detection, prevention, and violations of terms of service". It is unclear how long they retain this information for, or if and how you can request its deletion.

Whether your IP address identifies you depends on how you are accessing the Internet. If your Internet Service Provider uses [Carrier-Grade Network Address Translation](https://en.wikipedia.org/wiki/Carrier-grade_NAT) (CG-NAT), your address may be shared with other users, and therefore may not identify you specifically. In other cases, such as but not limited to connections with a static and/or IPv6 address, and connections not using CG-NAT, it may be unique to you, your device, or your household. In any case, depending on your Internet Service Provider's configuration, it may reveal your approximate location.

For more information, see [About GitHub Pages: Data collection](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages#data-collection) and the [GitHub General Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement), limited in scope to your IP address as used for security purposes.

**How to exercise data rights**: if you have legal rights regarding personal data, contact [privacy@github.com](mailto:privacy@github.com).

**General queries**: if you have queries regarding GitHub's use of data or compliance with relevant laws and regulations, contact [dpo@github.com](mailto:dpo@github.com).

**How to prevent future data collection**: to protect your IP address, you can access this site using a VPN, using a proxy such as [StartPage Anonymous View](https://www.startpage.com/en/anonymous-view), or simply by avoiding visiting the site entirely. If using a VPN or proxy, remember to check their privacy policy to see what information is retained. *This is not an endorsement of Anonymous View, nor a guarantee that it is safe or effective*. Alternatively, access this site using an IP address shared with others.

## Referrer Information

Websites may log the address of the site that you visited immediately prior. Often, this is the site on which you clicked the link that sent you there. This is achieved by the [HTTP referer header](https://en.wikipedia.org/wiki/HTTP_referer).

Therefore, by clicking a link on this site, the site that you visit may record that this site sent you there. Such use is governed by that site's privacy policy.

No information is returned to me and I have no knowledge of which links you click.

**How to check what data is being collected**: if the website in question has a privacy policy, check it to see if you can exercise your right to access (if applicable). Alternatively, use a tool such as [this one](https://alexloth.com/referrer-checker/) to see what is contained in your referer header.

**How to prevent future data collection**: in Firefox, go to `about:config` and set `network.http.sendRefererHeader` to `0`. In Chrome, use [this extension](https://chrome.google.com/webstore/detail/referer-control/hnkcfpcejkafcihlgbojoidoihckciin/) or [launch Chrome with the `--no-referrers` flag](https://superuser.com/a/1497461). This change will apply to all websites, not just this one, and may break some. *This is not an endorsement of Referer Control, nor a guarantee that it is safe or effective*.

## Social Media Information

Social media sites may track which links you click and how you interact with the websites after you click them. For example, on mobile devices, it [is technically possible](https://krausefx.com/blog/ios-privacy-instagram-and-facebook-can-track-anything-you-do-on-any-website-in-their-in-app-browser) to track interactions in webpages when viewed from within the social media app where you found the link (although it is unclear to what extent, if any, this capability is utilised). In any case, they may log which links you click, for example to determine which types of content interest you the most.

Such use is governed by the social media service's privacy policy.

**How to check what data is being collected**: if the social media service in question has a privacy policy, check it to see if you can exercise your right to access (if applicable).

**How to prevent future data collection**: copy links and open them manually in your chosen browser.

## External Resources

No external resources are loaded. Therefore, no third-party servers are contacted during the loading of this site. All references to them (specifically, [mathematical notation rendering](https://github.com/Jordan-Glass/blog.jglass.me/commit/fb93fbecd0b62071a8a0569634f8e9ce48d6c072) and [external fonts](https://github.com/Jordan-Glass/blog.jglass.me/commit/074a4591c89661eb2804476d29a43c3ba3fc9de6)) have been removed from the theme template to ensure they are never included in this site.

# Data Stored in Your Browser

This site contains the ability to toggle between light and dark themes, and to save this preference between visits. This is achieved using an entry in your browser's local storage with the key `theme-storage` and a value of `light` or `dark`, depending on your preference. It is managed by [`themetoggle.js`](/js/themetoggle.js).

This preference exists solely in your browser and is never sent elsewhere. Your browser may save this information or send it elsewhere, such as for synchronisation or backups. Such use is governed by your browser's documentation, support pages and/or privacy policy.

If you have JavaScript enabled, this preference is set automatically the first time you load the site in a given browser, even if you don't interact with the theme toggle button.

On each site load, the theme is set to the preference saved in your browser's local storage. If that preference doesn't exist (such as on the first site load), if your system or browser indicates that you have its dark mode enabled, the value `dark` will be set. Otherwise, the default value is `light`.

Upon clicking the theme toggle button, the preference is set to the opposite of the current value.

**How to erase stored data**: use your browser's utility to clear cookies and site data (this is usually in or near the URL bar) or use developer tools to clear local storage.

**How to prevent future data collection**: to prevent the storage value being set, use a browser extension such as [NoScript](https://noscript.net/), or some functionality built-in to your browser if present, to disable JavaScript for this site. If using NoScript, set the site's permission level to DEFAULT or use CUSTOM to ensure that `script` is disabled and, optionally, `font` is enabled (to enable the loading of custom fonts). You have been successful if the theme switch icon does not appear in the header. Remember to clear your browser's local storage for this site (see above).
