# docker-arch-yaourt

This is a simple docker image based on l3iggs/archlinux that provides aur access via yaourt.

## Usage

Here's a simple example how to use this baseimage:

```Dockerfile
FROM chrert/arch-yaourt
MAINTAINER Your name

USER yaourt
RUN yaourt --noconfirm -Sa SOME_AUR_PACKAGE

# remove user yaourt (for security reasons)
USER root
RUN userdel -r yaourt && rm /etc/sudoers.d/yaourt
```
