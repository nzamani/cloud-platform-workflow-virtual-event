FROM centos:7

RUN yum -y install which unzip wget net-tools less

COPY sapdownloads /tmp/sapdownloads/
WORKDIR /tmp/sapdownloads/

RUN unzip sapcc*.zip && \
	rpm -i sapjvm*.rpm && \
	rpm -i com.sap.scc*.rpm

RUN chsh -s /bin/bash sccadmin

EXPOSE 8443
USER sccadmin
WORKDIR /opt/sap/scc

ENV JAVA_HOME=/opt/sapjvm_8/
CMD ./go.sh
