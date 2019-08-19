# Packet Rig Startup
> v1.0 - Aug 10, 2018

## AX.25 Setup

> *Note:* AX.25 ports will need to be configured first. The ports are defined in `/etc/ax25/axports`

Ports are currently configured as:

- [ ] Include contents of axports file
- [ ] Rename AX.25 ports
	- The first item in a port description can be a name instead of a number.  Currently using numbers, should rename this to something like w100, aprs, etc.


Assuming ports have been configured, attach the serial port to the AX.25 system using:

```
sudo kissattach /dev/ttyAMA0 3 10.1.1.1
```

The number `3` above matches the port number from the axports file above. There is also an IP address. It’s required here even though you aren’t using the IP protocol on it.

To detach ports in the event a port needs to be re-configured:

```
sudo killall kissattach
```

## Packet Monitoring

Packets can be monitored using `axlisten`. This can be done in a separate terminal window.

```
sudo axlisten –a
```


## Connecting to Other Stations

Connecting to other stations is done via `axcall`. The general format is:

```
axcall 1 otherCall
```

…where `otherCall` is the callsign of the station to which you want to connect. 

There seems to be a bug in `axcall`. The first time you use it after calling `kissattach`, it will take significantly longer for the Raspberry Pi to send a valid connect string to the TNC than it does in subsequent attempts. You may have to wait 10–15 seconds. Further attempts occur instantaneously. You can abort this first try by issuing a `Ctrl-C` and then issuing the `axcall` command again. It will then connect immediately.

```
axcall -s <your_call> <port> <other_call>
```

### Command Details

`axcall`
: Invokes the `axcall` app.

`-s`
: Sets the AX.25 mode to `s` for normal (modulus 8) AX.25 operation.

`your_call`
: Your callsign.

`port`
: The port to use when connecting. This will be the same port that `kissattach` is bound to. In our case, `3`, as that's where we bound `/dev/ttyAMA0` up above.

`other_call`
: The callsign to attempt connecting to.


So, in our case, our final command will look like this:

```
axcall -s kc6bsa 3 ke7bme
```

## Logging Traffic

As mentioned earlier, `axlisten` can be used to monitor the raw packets. To log the data of `axcall`, once it's running and connected, commands can be issued to `axcall` using `~`.

`~o [filename]`
: Open a logfile (default 'logfile.txt')

`~c`
: Close the logfile

Note: The logfile will be written the the user directory (`~/logfile.txt`). It doesn't seem to like supplying a path like `~/Desktop/logfile.txt`, but a path like `myLogFile.txt` seems to be reliable to get the log writted to the user directory.


## Connecting to W100 System

*NOTE* This info is for the test system. Need to add race day details.

First, connect to a node. We'll be connecting to PEAK, which is run by `K0DJ-4` on 145.050.

```
axcall -s kc6bsa 3 ac7br-4
```

Run the `nodes` command to verify that `RACE` is connected. Connect to RACE:

```
connect RACE
```