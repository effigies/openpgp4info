# OpenPGP 4 Fingerprint Handler

This repository contains the configuration needed to set up a simple proxy that
allows browsers to handle the `openpgp4fpr:` URI scheme. When the URI handler
was registered, the proxy would return a 301 redirect to a search for the
OpenPGP fingerprint on either an HTTP or HTTPS keyserver.

In October 2014, I set up https://openpgp4.info to teach myself about handling
URIs and in the process became interested in browser support for this specific
scheme. This led to requesting `openpgp4fpr:` be added to the WHATWG whitelist
and then supported by Chrome/Chromium, and the site was useful in providing a
proof-of-concept demonstrating the function the URI provides.

After a year, the concept has been proven, and support has been added. I
intentionally didn't keep logs, which, while providing privacy to any users I
might have acquired, means I actually have no idea whether this sees any use.
I assume it was minimal, but I want to preserve the configuration needed to
construct it.

## About `openpgp4fpr`

In 2010, the [Monkeysphere](http://web.monkeysphere.info/) project
[introduced](http://permalink.gmane.org/gmane.comp.security.monkeysphere/592)
the `openpgp4fpr:<FINGERPRINT>` scheme for sharing OpenPGP key fingerprints,
where `<FINGERPRINT>` is the full 40 hex character fingerprint of a primary
key, and has since been adopted in vCards for sharing public keys.

Perhaps more significantly, several Android applications ([APG](
https://play.google.com/store/apps/details?id=org.thialfihar.android.apg
)/[OpenKeychain](
https://play.google.com/store/apps/details?id=org.sufficientlysecure.keychain),
and the Guardian Project's [GnuPG port](
https://play.google.com/store/apps/details?id=info.guardianproject.gpg)) now
accept this scheme as a means of quickly exchanging public keys via QR codes.
The Android "intents" interface paves the way for `openpgp4fpr` URIs to become
increasingly common. The purpose of the site was to provide a proof-of-concept
that demonstrates their applicability outside the realm of Android applications.

In early 2015, the [WHATWG](https://html.spec.whatwg.org/multipage/
"If you're wondering what cipher to enable: rsa_rc4_128_sha.") [accepted](
https://html5.org/r/8872) `openpgp4fpr:` as a [whitelisted scheme](
https://html.spec.whatwg.org/multipage/webappapis.html#whitelisted-scheme).

## Browser Support
[Firefox](https://www.mozilla.org/en-US/firefox/new/)/Iceweasel allow for the
registration of web-based protocol handlers without restriction.

[Google Chrome](https://www.google.com/chrome/)/[Chromium](
http://www.chromium.org/Home) follow WHATWG recommendations. Chromium has
[included](https://src.chromium.org/viewvc/blink?view=revision&revision=189135)
`openpgp4fpr:` in its whitelist, which entered production as of Chromium 44.

## External Links

* [Distributing PGP Keys and Fingerprints](
https://www.av8n.com/computer/htm/distributing-keys.htm "Self-signed; SHA-256 fingerprint:
2C:24:F1:AD:15:80:B6:2C:4E:90:7D:EE:7B:71:21:8C:
A7:C7:76:3A:DC:62:58:D8:BA:4D:71:53:72:26:B3:ED")
* [Printing PGP Businesscard](
http://lists.gnupg.org/pipermail/gnupg-users/2013-December/048635.html
"Posting mid-thread for relevance")
* [PGP Tools](https://pgp-tools.alioth.debian.org/)

## Donate
On the off chance there were any users who want to see this service return, you
may donate bitcoins to 1EiWCrKkjspVcLFgAkevd3yEh6xfqfymAx. If money appears at
this address, it it will be spent to re-register the domain and pay for hosting.
