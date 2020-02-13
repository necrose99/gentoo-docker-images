FROM alpine:latest
RUN apk add squashfs-tools 	p7zip xz tar bzip2

I needed a multistage builder with just a few extra tools ie unzip /unsquash craps. 

Like Live Cd iso's etc.. 

in my use case Gentoo Varriants.. for now i've stuck here. 
WORKDIR /gentoo
ie needing the epherial chroot of docker and or means of tweaking iso more to my liking woithout a hudge mess. 
add ios /sometemp 

7z x /sometemp/my.iso /
rm *.trashes... 

unsquashfs -f -d /mydistro  /sometemp/file.squashfs

next from push /mydistro / wala 

FROM scratch

WORKDIR /
COPY --from=builder /gentoo/ /
CMD ["/bin/bash"]
