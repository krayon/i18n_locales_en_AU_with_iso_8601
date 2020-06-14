# Internationalisation locales - en_AU + ISO 8601 dates #

This locale file can be included in your system locales. It merges Australian
English locale with some more sane date formats.

The time and dates displayed for various commands will then be in new formats.

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
## Installation - System ##

Install the file to `/usr/share/i18n/locales/en_KRAYON`

```bash
sudo install -m0644 -oroot -groot usr-share-i18n-locales-en_KRAYON /usr/share/i18n/locales/en_KRAYON
```

Add it to your `/etc/locale.gen`

```bash
cat <<EOF |sudo tee -a /etc/locale.gen
en_KRAYON ISO-8859-1
en_KRAYON.UTF-8 UTF-8
EOF
```

Regenerate your locales

```bash
sudo locale-gen
```



----
## Installation - Local user ##

Can instead store it for local user, and set `PATH_LOCALE`, see:

  * http://lists.freebsd.org/pipermail/freebsd-questions/2015-June/266181.html



----
## Enable ##

Set your environment variable `LC_TIME` to `en_KRAYON`. You can also add this
to your `.bashrc`, `bash_profile`, `/etc/bash.bashrc`, `/etc/profile` etc

```bash
export LC_TIME=en_KRAYON
```



----
## Other settings of use ##

These are other things to add to your `.bashrc` etc to keep you sane:

```bash
# libc's date format seems to default to "Mth DD  YYYY" / "Mth DD HH:MM"
# ... this ensures ls -la shows the LOGICAL "YYYY-MM-DD HH:MM"
export TIME_STYLE='long-iso'

# libc's collating (ls sort order) is mixed, we want all dot files together etc
export LC_COLLATE='C'
```



----
[//]: # ( vim: set ts=4 sw=4 et ai si ft=markdown: )
