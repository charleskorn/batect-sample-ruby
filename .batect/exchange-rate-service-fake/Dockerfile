FROM andyrbell/mountebank:2.4.0

RUN apk add --no-cache curl
RUN mkdir -p /tools
COPY health-check.sh /tools/
HEALTHCHECK --interval=0.2s --retries=10 CMD /tools/health-check.sh

ADD imposters /imposters

CMD ["mb", "--configfile", "/imposters/config.ejs"]
EXPOSE 6000
