FROM scratch
ENTRYPOINT ["/helloworld"]
EXPOSE 80
ARG VCS_REF
LABEL org.label-schema.vcs-ref=$VCS_REF \
      org.label-schema.vcs-url="https://github.com/weaveworks/flux-example"
COPY ./helloworld-linux-amd64 /helloworld
