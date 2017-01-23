# AuRevoir

AuRevoir does zeroconf service discovery on behalf
of clients who do not support zeroconf, and exposes
discovered services on a web page.


## Examples of use

### Browsing *.local services from smartphones/tablets

Multiple services on my network announce themselves
with mDNS, making them discoverable from my laptop
with a convenient name under the `.local` hierarchy.

For instance, from my Linux machine named `glamdring`,
I can connect to my Mac machine named `moonshine` with
the following command:

```bash
ssh moonshine.local
```

And I can look up existing services (for instance,
my printer) with `avahi-browse`.

However, this doesn't work out of the box on phones
and tablets. So instead, I run AuRevoir on a local
web server (e.g. 192.168.1.1) and from my phone or
tablet, I can open http://192.168.1.1/ to see a list
of existing services (and their IP addresses).

Note: for this specific use-case, it is usually easier
to run a Bonjour browser on your phone directly!


### Generating a dynamic menu of local services

I have a multi-room audio system using multiple
Raspberry Pis and other network-connected speakers
that announce themselves using PulseAudio's zeroconf
module. From my phone, I want to see a list of the
available speakers (those which are currently powered on).

To do this, I run AuRevoir on a central Raspberry Pi,
and I configure it to generate a nice HTML page showing
only the audio resources. I can now see these resources
(and access them) from my phone, even if my phone doesn't
support mDNS (i.e. `.local` resolution).


### Listing existing mDNS services with a REST API

I need to list existing mDNS services and resolve them,
but I don't want to implement mDNS discovery. Instead,
I can run AuRevoir and let it maintain the list of mDNS
services, and query AuRevoir with a REST API.




