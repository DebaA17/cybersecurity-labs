FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
  && apt-get install -y --no-install-recommends sudo python3 ca-certificates \
  && rm -rf /var/lib/apt/lists/*

# Low-privilege user
RUN useradd -m -s /bin/bash student

# Root-only flag
COPY root-flag.txt /root/flag.txt
RUN chmod 600 /root/flag.txt

USER student
WORKDIR /home/student

CMD ["/bin/bash", "-l"]
