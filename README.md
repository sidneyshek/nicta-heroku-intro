A brief intro to Heroku
=======================

Presso for NICTA Hackathon Sept 2013.

Steps for creating a Heroku instance
===
heroku apps

heroku create regorous-editor-hackathon --buildpack https://github.com/sidneyshek/heroku-buildpack-grails-nodejs

-- add collaborator


heroku addons:add heroku-postgresql:dev --app regorous-editor-hackathon

heroku config --app regorous-editor-hackathon


heroku pg:promote HEROKU_POSTGRESQL_BLUE_URL --app regorous-editor-hackathon

heroku config:add CDN_DOMAIN_NAME=d3tlsisc93i3a0.cloudfront.net --app regorous-editor-hackathon

DATABASE_URL="postgres://yexugsaoypmmug:TSdaTBg8JwO2xcEBvg8QZ-YTAe@ec2-23-21-196-147.compute-1.amazonaws.com:5432/d2n865f46d3g4r?ssl=true&sslfactory=org.postgresql.ssl.NonValidatingFactory" grails -Dgrails.env=prod dbm-update

git remote add hackathon git@heroku.com:regorous-editor-hackathon.git

git push hackathon master

heroku pg:psql --app regorous-editor-hackathon

heroku logs --tail --app regorous-editor-hackathon

heroku run bash

-- Heroku plugins

