FROM boinc/client:arm64v8

RUN apt-get update \
 && apt-get install -y --no-install-recommends libgomp1

CMD ["start-boinc.sh"]
