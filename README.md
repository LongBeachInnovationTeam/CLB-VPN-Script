# CLB VPN Script

Use this handy script to login to City VPN with OpenConnect in case you are using a Debian-derived Linux distribution and don't want to use Cisco's VPN client software.

## Installation

1. Install necessary packages: `$ sudo apt-get install openconnect lib32ncurses5 lib32tinfo5 lib32z1 libc6-i386 libpkcs11-helper1 openvpn vpnc-scripts`
2. Edit the `VPNUSER` variable in the script with your City Employee ID/login name
3. Save the script somewhere in your system where it can be picked up by your `$PATH`, e.g. `/usr/local/bin/clbvpn`
4. Make the script executable `$ chmod +x /usr/local/bin/clbvpn`
5. Verify that your script is in your `$PATH` with `$ which clbvpn`

## Usage

`$ clbvpn`

You should see the following output:

    Sun Mar 19 22:09:41 2017 TUN/TAP device tun1 opened
    Sun Mar 19 22:09:41 2017 Persist state set to: ON
    POST https://clbvpn1.ci.long-beach.ca.us/
    Attempting to connect to server 204.108.18.93:443
    SSL negotiation with clbvpn1.ci.long-beach.ca.us
    Connected to HTTPS on clbvpn1.ci.long-beach.ca.us
    XML POST enabled
    Please enter your username and password.
    Password:

Enter the passcode given by your cryptocard into the password prompt to login.

You're connected to the VPN if you see something like this:

    POST https://clbvpn1.ci.long-beach.ca.us/
    Got CONNECT response: HTTP/1.1 200 OK
    CSTP connected. DPD 30, Keepalive 20

Keep the shell session open to keep the connection alive. When you're done, you can terminate the VPN session with `CTRL+C`.

## Future Work
It will be great to get proxy settings working well and/or figure out how to tunnel split.
