FROM michzimny/learninglocker2-app:afb2858ab47bb76a1153ae2dd8a3bdf79d10b863

# make a copy of the origin storage directory that will be used in entrypoint-common.sh
# to fill up a volume mounted here, if it's empty
RUN cp -r storage storage.template

# service api exposes port 8080
# service ui exposes port 3000
# see env.template
EXPOSE 3000 8080

COPY env.template .env.template
COPY entrypoint-common.sh entrypoint-common.sh
COPY entrypoint-ui.sh entrypoint-ui.sh

ENTRYPOINT ["./entrypoint-common.sh"]

