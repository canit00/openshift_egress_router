# This is the egress router for OpenShift Origin
# The standard name for this image is openshift/origin-egress-router
#
# Usage:
# sudo docker build --rm -t <registry>:5000/openshift/origin-egress-router-lb .
# sudo docker push <registry>:5000/openshift/origin-egress-router-lb
# oc create -f egress-rr.yaml
#
FROM registry.access.redhat.com/rhel7

LABEL maintainer "First Last <first.last@server.com>"

RUN yum makecache && \
yum install iputils iproute -y && \
yum clean all && \
rm -rf /var/cache/yum/*

ADD egress-router-lb.sh /bin/egress-router-lb.sh

ENTRYPOINT /bin/egress-router-lb.sh
