# Old ICOM IC-F310 Programming 


## HARDWARE

To program the ICOM IC-F310 you first need the correct cable and serial IC module.

I had to use an old PL232 USB module and the old driver from 2008.

The radio uses an RJ45 port for programming and only 2 wires are needed.

Once you have the correct cable continue to the software setup.

## SOFTWARE

Install the latest DOSBox on windows 11.

once installed open the config file at `C:\Users\UserName\AppData\Local\DOSBox\dosbox-0.74-3.conf`.

In the config file change the settings for `cpu` and `serial` to mach those below:

```conf
[cpu]
#      core: CPU Core used in emulation. auto will switch to dynamic if available and
#            appropriate.
#            Possible values: auto, dynamic, normal, simple.
#   cputype: CPU Type used in emulation. auto is the fastest choice.
#            Possible values: auto, 386, 386_slow, 486_slow, pentium_slow, 386_prefetch.
#    cycles: Amount of instructions DOSBox tries to emulate each millisecond.
#            Setting this value too high results in sound dropouts and lags.
#            Cycles can be set in 3 ways:
#              'auto'          tries to guess what a game needs.
#                              It usually works, but can fail for certain games.
#              'fixed #number' will set a fixed amount of cycles. This is what you usually
#                              need if 'auto' fails. (Example: fixed 4000).
#              'max'           will allocate as much cycles as your computer is able to
#                              handle.
#            Possible values: auto, fixed, max.
#   cycleup: Amount of cycles to decrease/increase with keycombos.(CTRL-F11/CTRL-F12)
# cycledown: Setting it lower than 100 will be a percentage.

# Original values 
#core=auto
#cputype=auto
#cycles=auto
#cycleup=10
#cycledown=20

# Changed values
core=auto
cputype=auto
cycles=3000
cycleup=10
cycledown=20

[serial]
# serial1: set type of device connected to com port.
#          Can be disabled, dummy, modem, nullmodem, directserial.
#          Additional parameters must be in the same line in the form of
#          parameter:value. Parameter for all types is irq (optional).
#          for directserial: realport (required), rxdelay (optional).
#                           (realport:COM1 realport:ttyS0).
#          for modem: listenport (optional).
#          for nullmodem: server, rxdelay, txdelay, telnet, usedtr,
#                         transparent, port, inhsocket (all optional).
#          Example: serial1=modem listenport:5000
#          Possible values: dummy, disabled, modem, nullmodem, directserial.
# serial2: see serial1
#          Possible values: dummy, disabled, modem, nullmodem, directserial.
# serial3: see serial1
#          Possible values: dummy, disabled, modem, nullmodem, directserial.
# serial4: see serial1
#          Possible values: dummy, disabled, modem, nullmodem, directserial.

serial1=dummy
serial2=directserial realport:COM7 # or your COM Port
serial3=disabled
serial4=disabled
```

Install the `9/24/2008` prolific driver version `3.3.2.102` for your PL232 IC module.

Once installed check that the usb to serial shows up in the COM ports section.

Now start DOSBox.

You will be in the Z directory.

Next type the mount path to ICOM files directory.

```
mount C C:\Software\DOSBox-0.74-3\v1_2
```

Browse to the newly mounted C: drive.

```
C:
```

Start the IC-F310 DOS application.

```
CSF300.EXE
```

You will now see the App interface in the DOS console window.

Press esc and move to the `Setup` menu item select `RS-232C`.

Now choose the `Port #2` option and press enter.

Now move to the `Model` menu item and choose the `PMR` option and press enter.

Move to the `Clone` menu option and select `Read <- TR` make sure the radio is powered on!










