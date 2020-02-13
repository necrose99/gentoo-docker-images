FROM alpine:latest
RUN apk add squashfs-tools 	p7zip xz tar bzip2

{ARG BOOTSTRAP
FROM ${BOOTSTRAP:-alpine:3.7} as builder

WORKDIR /gentoo  } https://raw.githubusercontent.com/gentoo/gentoo-docker-images/master/stage3.Dockerfile 
i'm just swaping alpine to this so builder has the few required build toys. 

I needed a multistage builder with just a few extra tools ie unzip /unsquash craps. 

Like Live Cd iso's etc.. 

in my use case Gentoo Varriants.. for now i've stuck here. 

WORKDIR /gentoo
ie needing the epherial chroot of docker and or means of tweaking iso more to my liking woithout a hudge mess.  on system or lots of leftovers to clean out
IE https://www.pentoo.ch/isos/latest-iso-symlinks/ 

add ios /sometemp 

7z x /sometemp/my.iso /
rm *.trashes... 

unsquashfs -f -d /mydistro  /sometemp/file.squashfs

next from push /mydistro / wala 

FROM scratch

WORKDIR /
COPY --from=builder /gentoo/ /
CMD ["/bin/bash"]
