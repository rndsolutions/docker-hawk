FROM hawk-base:0.0.2
MAINTAINER Radoslav Minchev <rminchev@rnd-solutions.net>

#setup file structure
RUN mkdir -p /usr/src/app/source /usr/src/app/build
WORKDIR /usr/src/app/source
COPY . /usr/src/app/source

#compile server
RUN nuget restore -NonInteractive
RUN xbuild /property:Configuration=Release /property:OutDir=/usr/src/app/build/
WORKDIR /usr/src/app/build
RUN mkdir www

#change working dir
WORKDIR /usr/src/app/source/ui

#install nodejs packages
RUN npm install    

#install bower packages
RUN bower install --allow-root

#build the app
RUN npm install --global gulp-cli \
    && gulp build

#copy the minified and combined app assets to www
RUN cp -r dist/* /usr/src/app/build/www/  

WORKDIR /usr/src/app/build

#run when the container is started
CMD ["mono", "./HawkEngine.Server.exe"] 


