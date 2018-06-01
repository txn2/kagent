FROM txn2/txagent:1.0.4
RUN mkdir /configs
COPY configs/amd64/ /configs
ENV AGENT_CFG_URL=file://configs/defs.json
ENV AGENT_AUTH_URL=file://configs/auth.json