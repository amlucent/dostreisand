FROM        hwdm/dostreisand:orig
# hwdm/apbase contains some useful shell utils. You may replace it with alpine:3.5 instead.
MAINTAINER      Howard Mei      <howardleomei@gmail.com>

ENV         REPO_URL="https://github.com/entaopy/dostreisand.git"
ENV         REPO_BRN="master"
ENV         DEBUG_MODE=no
ENV         PLAYBOOK_PORT=22
# You may use the official repo: https://github.com/jlund/streisand
# I changed the ssh default port and plan to do more in the future.

# Renew the streisand by cloning the latest streisand code from the master branch
RUN         rm -rf /streisand && git clone -b ${REPO_BRN} ${REPO_URL} /streisand

WORKDIR     /streisand

VOLUME      /root/.ssh
VOLUME      /streisand

CMD         ["/streisand/streisand"]
