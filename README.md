# Bromite - Take back your browser

<img src="https://www.bromite.org/release.svg" alt="current Bromite release" title="current Bromite release" /> <img src="https://www.bromite.org/license.svg" alt="GNU GPL v3" title="GNU VPL v3" />

<img title="Bromite - take back your browser!" src="https://www.bromite.org/android-icon-192x192.png" width="96" alt="Bromite" />

Bromite is [Chromium](https://www.chromium.org/Home) plus some patches for ad blocking and enhanced privacy.

Bromite is only available for Android v4.4 and above.

<img src="https://www.bromite.org/bromite_bromite_gh_downloads.svg" alt="downloads on Github" title="downloads on Github" />

# Goals

Bromite aims at providing a no-clutter browsing experience without privacy-invasive features and with the addition of a fast ad-blocking engine.
Minimal UI changes are applied to help curbing the idea of "browser as an advertisement platform".

# Donate

Please donate to support development of Bromite and the costs for the build system.

[&rarr; Support development with a donation](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=JP3XTQPVRNET2): [![paypal](https://www.bromite.org/assets/img/btn_donate_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=JP3XTQPVRNET2)

<a href="bitcoin:3MkC3idL61npQSCxL1gceksmRTkNkiCPcG">BTC donations address</a>: `3MkC3idL61npQSCxL1gceksmRTkNkiCPcG`

ETH donations address: `0xf47ff39223d828f99fec5ab53bd068c5c0522042`

# F.A.Q.

## Does Google Sync/Translate/Data saver work?
No.
This is not a limitation of Bromite but of all Chromium-based projects in general, as general public is not allowed to use Google's APIs for free unless when using Chrome.

Additionally, these features would not be privacy-friendly.

## Does Bromite require root?
No.

## Is Bromite de-googled?

Yes, although this has not been verified (and hardly can be) under all situations; if you were to find connections to cloud-based services please report them via the issue tracker.
Projects which follow a strict approach on this are [Iridium](https://iridiumbrowser.de/) and [Inox patchset](https://github.com/gcarq/inox-patchset).

## What is the SystemWebView?
It is the core component of Android for all web page visualizations. For example when you access a new wifi network and need to activate it, that is using the SystemWebView. If you do not know what it is then you do not need to install it.

See also [the wiki page](https://github.com/bromite/bromite/wiki/Installing-SystemWebView) for community-contributed installation instructions.

## How to enable DNS-over-HTTPS?

See [this wiki page](https://github.com/bromite/bromite/wiki/Enabling-DNS-over-HTTPS).

## Can you add HTTPS everywhere?
No.
We cannot add add-ons to Bromite (merely some features).

## Is Bromite on Play Store?
No, and this is unlikely to change. Many limitations apply for submissions there, including which ads are allowed to be blocked.

Bromite favors user freedom in software choice: the device is yours so you get to choose which software to run on it, end of the story.

## Is Bromite on F-Droid?
It is not on the official F-Droid repository and there are no (more) plans to submit it.

You can use F-Droid client to install and receive updates via [the official Bromite F-Droid repository](https://www.bromite.org/fdroid).

## Does Bromite support WebRTC?
Yes, since version 69. While the desktop version of Chromium has an option to disable it (video/audio site settings), the Android version cannot.

# Features

* native adblock engine
* remove click-tracking and AMP from search results
* DNS-over-HTTPS support via Google, Cloudflare, Quad9 and AdGuard servers
* [proxy configuration page](https://github.com/bromite/bromite/wiki/ProxyConfiguration) with PAC and custom proxy lists support
* [StartPage](https://startpage.com/), [DuckDuckGo](https://duckduckgo.com/) and [Qwant](https://www.qwant.com/) search engines
* chrome flags to disable custom intents and clear session on exit
* always-incognito mode
* completely removed safe browsing and other privacy-unfriendly features
* anti-fingerprinting mitigations for canvas, audio, client rects, webGL and sensor APIs
* use fixed User-Agent to conceal real model and browser version
* privacy enhancement patches from [Iridium](https://iridiumbrowser.de/), [Inox patchset](https://github.com/gcarq/inox-patchset), [Brave](https://brave.com/) and [ungoogled-chromium](https://github.com/Eloston/ungoogled-chromium) projects
* security enhancement patches from [GrapheneOS](https://github.com/GrapheneOS) project

## Features not related to privacy
* import/export bookmarks
* allow playing videos in background tabs and disable pause on switching tabs
* all codecs included (proprietary, open H.264 etc.)
* [AV1 codec support](https://github.com/bromite/bromite/wiki/AV1-support)
* built with official speed optimizations

You can inspect all functionality/privacy changes by reading the patches: https://github.com/bromite/bromite/tree/master/build/patches

# Privacy limitations

Bromite's privacy features, including anti-fingerprinting mitigations (which can be easily circumvented), **are not to be considered useful for journalists and people living in countries with freedom limitations**, please look at [Tor Browser](https://2019.www.torproject.org/projects/torbrowser.html.en) in such cases.

# Releases

All built versions are available as [releases](https://github.com/bromite/bromite/releases); the [official website](https://www.bromite.org/) points to those releases and - when browsing via Android - it will automatically select the one apt for your device (or none otherwise).

Each tag corresponds to a Chromium Stable release tag.

Bromite is currently built for ARM, ARM64 and x86 and for the Android SDK versions 19 and 21; [Bromite SystemWebView](https://www.bromite.org/system_web_view) is provided as well (SDK21+).
For every Bromite build you can always find a matching [vanilla Chromium](https://www.bromite.org/chromium) build which is used for example to verify which issues are specific to Bromite or not.

All official releases are also available through the [official third-party F-Droid repository](https://www.bromite.org/fdroid).

## Integrity and authenticity

You can verify the integrity of a downloaded APK file from this project with any `sha256sum`-compatible tool by downloading the corresponding `brm_X.Y.Z.sha256.txt` or `chr_X.Y.Z.sha256.txt` file, where X.Y.Z is the release version number. Example:
```
$ sha256sum --check brm_68.0.3440.54.sha256.txt
arm64_SystemWebView.apk: OK
arm64_ChromePublic.apk: OK
arm64_ChromeModernPublic.apk: OK
```

If you prefer an UI-based tool, you might want to look into [GtkHash](https://github.com/tristanheaven/gtkhash).

You can verify authenticity, e.g. that the author ([csagan5](https://github.com/csagan5)) released the file, by using gpg2:
```
$ gpg2 --quiet --verify brm_68.0.3440.54.sha256.txt.asc
gpg: assuming signed data in 'brm_68.0.3440.54.sha256.txt'
gpg: Signature made Sun 08 Jul 2018 04:22:52 PM CEST using RSA key ID D85DC0C5
gpg: Good signature from "csagan5 <32685696+csagan5@users.noreply.github.com>"
```

You can download csagan5's public GnuPG key from here: [csagan5.asc](./csagan5.asc).

**NOTE:** releases before v68 did not have published signed hashes files.

# How to build

The [Bromite main repository](https://github.com/bromite/bromite) contains tags for each corresponding Chromium release (see https://chromium.googlesource.com/chromium/src.git).

Please refer to [official Chromium build documentation](https://www.chromium.org/developers/how-tos/get-the-code) to get started on how to build Chromium; if you can build Chromium for Android, you can build Bromite.

The GN args used to build Bromite are available here: [GN_ARGS](./build/GN_ARGS).
The patches are to be applied second the order specified in the `bromite_patches_list.txt` file (you can use `git am`).

## How to build the filters

See upstream documentation: https://github.com/chromium/chromium/blob/master/components/subresource_filter/FILTER_LIST_GENERATION.md

Bromite uses an unindexed filter file, which is periodically published at https://github.com/bromite/filters

# Credits

* [Chromium project](https://www.chromium.org/Home) and developers
* [Iridium project](https://github.com/iridium-browser) for some patches
* [ungoogled-chromium](https://github.com/Eloston/ungoogled-chromium) for some patches
* [ungoogled-chromium-android](https://github.com/ungoogled-software/ungoogled-chromium-android) for some patches
* [GrapheneOS](https://github.com/GrapheneOS) for some security patches
* [Inox patchset](https://github.com/gcarq/inox-patchset) for some patches (via ungoogled-chromium)
* [Brave Browser](https://github.com/brave/browser-android-tabs) for some patches
* nochromo for the original adblock patch, currently used only in the SystemWebView
* [Vadim Pleshkov](http://vadimpleshkov.me/) for Bromite's logo

# Filters credits
* [EasyList](https://easylist.to/#easylist)
* [EasyPrivacy](https://easylist.to/#easyprivacy)
* [uBlock Origin](https://github.com/uBlockOrigin)

# License

The patches published as part of the Bromite project are released under [GNU GPL v3](./LICENSE).

[version-image]: https://img.shields.io/github/release/bromite/bromite.svg?style=flat-square
[version-url]: https://github.com/bromite/bromite/releases/latest
[license-image]: https://img.shields.io/github/license/bromite/bromite.svg
[license-url]: https://github.com/bromite/bromite/blob/master/LICENSE
