FROM        hwdm/dostreisand:base
# hwdm/apbase contains some useful shell utils. You may replace it with alpine:3.5 instead.
MAINTAINER      Howard Mei      <howardleomei@gmail.com>

ENV         REPO_URL="https://github.com/StreisandEffect/streisand"
ENV         DEBUG_MODE=no
ENV         PLAYBOOK_PORT=22
# You may use the official repo: https://github.com/jlund/streisand
# I changed the ssh default port and plan to do more in the future.

# Clone the latest streisand code from the master branch
RUN         git clone -b master ${REPO_URL} /streisand

WORKDIR     /streisand
VOLUME      /streisand
VOLUME      /root/.streisand

CMD         ["/streisand/streisand"]
