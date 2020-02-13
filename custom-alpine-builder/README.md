FROM alpine:latest
RUN apk add squashfs-tools 	p7zip xz tar bzip2

I needed a multistage builder with just a few extra tools ie unzip /unsquash craps. 

Like Live Cd iso's etc.. 

in my use case Gentoo Varriants.. for now i've stuck here. 
