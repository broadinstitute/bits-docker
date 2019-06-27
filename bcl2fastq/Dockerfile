FROM centos:7.6.1810 as builder

WORKDIR /tmp

ADD https://support.illumina.com/content/dam/illumina-support/documents/downloads/software/bcl2fastq/bcl2fastq2-v2-20-0-linux-x86-64.zip .

RUN yum -y update && \
    yum -y install unzip && \
    unzip bcl2fastq2-v2-20-0-linux-x86-64.zip && \
    yum -y install bcl2fastq2-v2.20.0.422-Linux-x86_64.rpm

FROM centos:7.6.1810

WORKDIR /usr/local/bin

COPY --from=builder /usr/local/bin/bcl2fastq .

ENTRYPOINT ["/usr/local/bin/bcl2fastq"]

CMD ["--help"]
