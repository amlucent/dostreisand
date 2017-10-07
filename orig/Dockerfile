FROM        hwdm/apbase
# hwdm/apbase contains some useful shell utils. You may replace it with alpine:3.5 instead.
MAINTAINER      Howard Mei      <howardleomei@gmail.com>

ENV         REPO_URL="https://github.com/StreisandEffect/streisand"
ENV         DEBUG_MODE=no
ENV         PLAYBOOK_PORT=22
# You may use the official repo: https://github.com/jlund/streisand
# I changed the ssh default port and plan to do more in the future.

RUN         apk-install bash curl curl-dev build-base libffi-dev linux-headers openssh-client libressl-dev git py-pip python python-dev && \
            pip install --upgrade pip && sleep 1 && sync && \
            pip install --upgrade ansible markupsafe pycurl paramiko boto "dopy>=0.3.5" "apache-libcloud>=1.5.0" && \
            pip install --upgrade msrest msrestazure "azure>=2.0.0rc5" packaging linode-python pyrax PyCrypto

# Clone the latest streisand code from the master branch
RUN         git clone -b master ${REPO_URL} /streisand

WORKDIR     /streisand

VOLUME      /root/.ssh
VOLUME      /streisand

CMD         ["/streisand/streisand"]
