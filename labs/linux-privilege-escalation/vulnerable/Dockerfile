FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
  && apt-get install -y --no-install-recommends sudo python3 ca-certificates \
  && rm -rf /var/lib/apt/lists/*

# Low-privilege user
RUN useradd -m -s /bin/bash student

# Vulnerability: student can run python3 as root without a password
RUN echo "student ALL=(root) NOPASSWD: /usr/bin/python3" > /etc/sudoers.d/student \
  && chmod 440 /etc/sudoers.d/student

# Root-only flag
COPY root-flag.txt /root/flag.txt
RUN chmod 600 /root/flag.txt

# Optional
COPY exploit.sh /home/student/exploit.sh
RUN chown student:student /home/student/exploit.sh \
  && chmod 750 /home/student/exploit.sh

USER student
WORKDIR /home/student

CMD ["/bin/bash", "-l"]
