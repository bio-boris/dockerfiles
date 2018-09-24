FROM centos:7
ENV container docker

RUN yum -y update && yum -y install wget && yum -y install git && cd /etc/yum.repos.d && wget http://research.cs.wisc.edu/htcondor/yum/repo.d/htcondor-development-rhel7.repo && wget http://research.cs.wisc.edu/htcondor/yum/repo.d/htcondor-stable-rhel6.repo && wget http://research.cs.wisc.edu/htcondor/yum/RPM-GPG-KEY-HTCondor && rpm --import RPM-GPG-KEY-HTCondor && yum -y install condor.x86_64

RUN useradd kbase
COPY start-condor.sh /usr/bin/
COPY sleep /home/kbase/

CMD ["/usr/bin/start-condor.sh"]


