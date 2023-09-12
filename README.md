# docker-soapysdr

This container image runs SoapySDRServer from [SoapyRemote](https://github.com/pothosware/SoapyRemote), and, because it’s (currently, see SoapyRemote/issues#96) a dependency, avahi and dbus-daemon.

## Permissions

udev device permissions for the SDRs must be set _on the host_ to allow access to the soapysdr user in the container (e.g. 0666).

## Host networking

SoapySDRServer apparently creates a new listener for each stream and the ports are not predictable. Because of that the container needs host networking. (Also for avahi, though avahi is not at all neccessary for using SoapyRemote.)

Forked from [hbaier/docker-soapysdr](https://github.com/hbaier/docker-soapysdr)
