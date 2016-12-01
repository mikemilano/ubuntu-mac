# Ubuntu on Macbook Pro

## General Config

```
sudo apt-get install gnome-tweak-tool
```

Open tweak tool and go to `Typing -> Alt/Win key behavior`.
Set this to: Ctrl is mapped to Win keys (and usual Ctrl keys)


## PhpStorm

### Keymaps

Set the Keymap to `Default for GNOME` in `File -> Settings -> Keymap`

Search for 'Generate' (Code -> Generate) and add `Ctrl+Enter` as a shortcut. (Remove existing bindings of Ctrl+Enter when submitting.

Search for `New` (Other -> New...) and add `Ctrl+N` as a shortcut. (Remove existing bindings of Ctrl+N when submitting.

Search for `line end` (Editor Actions -> Move Caret to Line End) and add `Ctrl+Right`.

Search for `line start` (Editor Actions -> Move Caret to Line Start) and add `Ctrl+Left`.

### Plugins

Add plugins:
- Symfony Plugin
- PHP Annotations
- SensioLabsInsight


## Webex

Once configured, the 'Meet Now' link won't work. If hosting a meeting, you need to schedule it, then join.

Install 32 bit version of Firefox.
```
sudo apt-get install firefox:i386 libcanberra-gtk-module:i386 gtk2-engines-murrine:i386 libxtst6:i386
```

Download Linux X86 JRE: http://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html

Extract it somewhere like: `/opt/jre`

`mkdir ~/.mozilla/plugins`

`ln -s /opt/jre/lib/i386/libnpjp2.so ~/.mozilla/plugins/`

Make sure the java plugin is active on: `about:addons`

Run `/opt/jre/bin/jcontrol` and add the following to the site exceptions in the security tab.

- https://example.webex.com (where example is your account)
- https://akamaicdn.webex.com

