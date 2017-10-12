FROM codeurs/mod-neko
RUN apt-get update
RUN apt-get -y install curl imagemagick
RUN haxelib setup /usr/share/haxelib
RUN haxelib install templo
RUN cd /usr/bin && haxelib run templo
