# Social Engineering Toolkit

This Docker image contains the following social engineering tools. 

##  Tools
- SET - setoolkit
- Maltego 
- Metasploit
- Wifiphisher

## Docker Image
- https://hub.docker.com/r/habbdt/socialengineering


# Docker X11 Forwarding (Running GUI Application with Docker on Mac OS X)

The following instructions are tested for MacOS.  

## Installation

```
# brew install socat
# brew install xquartz
# socat TCP-LISTEN:6000,reuseaddr,fork UNIX-CLIENT:\"$DISPLAY\"
```

## How to 

Launch Xquartz application. 

```
# open -A Xquartz
```

Get the IP address of the MacOS. 

```
# ifconfig -a
```

Run the following command to launch the `habbdt/socialengineering` Docker container in Xquartz shell. Note. replace `$mac_ip` with the IP address of the MacOS. The `maltego &` command will launch Maltego application via X11 window. 

```
$ docker run --rm -it -e DISPLAY=$mac_ip:0 socialengineering bash
$ maltego &

```

## References
[1] https://unix.stackexchange.com/questions/403424/x11-forwarding-from-a-docker-container-in-remote-server#
[2] https://cntnr.io/running-guis-with-docker-on-mac-os-x-a14df6a76efc