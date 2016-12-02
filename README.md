# Ubuntu on Macbook Pro

## General Config

```
sudo apt-get install gnome-tweak-tool
```

Open tweak tool and go to `Typing -> Alt/Win key behavior`.
Set this to: Ctrl is mapped to Win keys (and usual Ctrl keys)

### Mouse fix

My Logitec mouse is too fast, even at the slowest speed. This script slows it down.
```
#!/bin/sh
for id in `xinput --list|grep 'Logitech Gaming Mouse G303'|perl -ne 'while (m/id=(\d+)/g){print "$1\n";}'`; do
    # echo "setting device ID $id"
    notify-send -t 50000  'Mouse fixed'
    xinput set-prop $id "Device Accel Velocity Scaling" 202020 
    xinput set-prop $id "Device Accel Constant Deceleration" 3 
done
```
Add that script to /etc/rc.local to have it automatically run on startup.

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


## PHP

Install/setup xdebug.

```
sudo apt-get install php-xdebug
```

Set the configuration: `/etc/php/7.0/mods-available/xdebug.ini`
```
zend_extension=xdebug.so
xdebug.remote_enable=1
xdebug.remote_port=9000
xdebug.profiler_enable=0
xdebug.profiler_output_dir=/home/xdebug
```

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

