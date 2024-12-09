FROM debian:12

RUN apt update && apt install -y net-tools procps most iproute2  iputils-ping whois

RUN apt install -y vsftpd rsyslog

RUN apt clean && rm -rf /var/lib/apt/lists/*

COPY entrypoint.sh /entrypoint.sh

RUN useradd -d /home/jefe -m -s /bin/bash -p $(echo abc123.. | mkpasswd) jefe

RUN mkdir /home/jefe/public_html

RUN chmod -w /home/jefe/

RUN chown jefe:jefe /home/jefe/public_html

RUN useradd -d /home/empleado -m -s /bin/bash -p $(echo abc123.. | mkpasswd) empleado

RUN mkdir /home/empleado/public_html

RUN chmod -w /home/empleado/

RUN chown jefe:jefe /home/empleado/public_html

RUN mkdir /sauron

RUN chmod -w /sauron

RUN mkdir /sauron/public_html

RUN chmod 777 /sauron/public_html

RUN useradd -d /home/saruman -m -s /bin/bash -p $(echo abc123.. | mkpasswd) saruman

RUN chmod +x /entrypoint.sh
ENTRYPOINT ["./entrypoint.sh"]