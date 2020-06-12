# Internationalisation locales - en_AU + ISO 8601 dates #

This locale file can be included in your system locales. It merges Australian
English locale with some more sane date formats.

The time and dates displayed for commands (`ls` etc) will then be in new
formats.

Changes date and time formats from:

  * `Tue  1 Dec 23:19:12 AEDT 2015`
  * `Tue 01 Dec 2015 23:19:12 AEDT`
  * `01/12/15`
  * `11:19:12 pm`

to:

  * `Tue 01-Dec-2015 23:19:12 AEDT`
  * `2015-12-01T02:45:31 AEST`
  * `2015-12-01`
  * `23:19:12`

----
## Installation location ##

I install to `/usr/share/i18n/locales/en_KRAYON`, then set the environment
variable `LC_TIME` to `en_KRAYON`, eg:

```bash
sudo install -m0644 -oroot -groot usr-share-i18n-locales-en_KRAYON /usr/share/i18n/locales/en_KRAYON
export LC_TIME=en_KRAYON
```

----
[//]: # ( vim: set ts=4 sw=4 et ai si ft=markdown: )
