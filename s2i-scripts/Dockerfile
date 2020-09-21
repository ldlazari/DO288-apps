#FROM openshift/httpd:2.4
FROM rhscl/httpd-24-rhel7

#LABEL "io.openshift.build.commit.author"="Luciano Dias Lázari <luciano.lazari@gmail.com>" \
#      "io.openshift.build.commit.date"="Sat Sep 19 15:52:09 2020 -0300" \
#      "io.openshift.build.commit.id"="df3b8ad6eefac4bd02a56b3a6d164694e3c8535b" \
#      "io.openshift.build.commit.ref"="master" \
#      "io.openshift.build.commit.message"="Merge pull request #1 from RedHatTraining/master" \
#      "io.openshift.build.source-location"="https://github.com/ldlazari/DO288-apps" \
#      "io.openshift.build.source-context-dir"="s2i-scripts" "io.openshift.build.image"="image-registry.openshift-image-registry.svc:5000/openshift/httpd@sha256:2f8503347c10a6fad0628fbbb5b2cbfc3e7cac521cea8c2def6bf4bfa2e67252"

#ENV OPENSHIFT_BUILD_NAME="bonjour-1" OPENSHIFT_BUILD_NAMESPACE="ldlazari-br-ibm-com-myquotes" OPENSHIFT_BUILD_SOURCE="https://github.com/ldlazari/DO288-apps" OPENSHIFT_BUILD_COMMIT="df3b8ad6eefac4bd02a56b3a6d164694e3c8535b"

USER root
COPY ./.s2i/bin /tmp/scripts
COPY ./ /tmp/src
RUN chgrp -R 0 /tmp/scripts /tmp/src && \
    chown -R 1001:0 /tmp/scripts /tmp/src && \
    chmod -R g=rwx /tmp/scripts
USER 1001
RUN /tmp/scripts/assemble
CMD /tmp/scripts/run
