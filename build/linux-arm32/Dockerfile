ARG tag=3.1
FROM mcr.microsoft.com/dotnet/core/runtime:${tag} AS base
WORKDIR /app
EXPOSE 8080
EXPOSE 8443
COPY qemu-arm-static /usr/bin/
COPY Template/ .
RUN ln -s  /var/run/secrets/kubernetes.io/serviceaccount/ca.crt /etc/ssl/certs/kubernetes.pem \
    && useradd -m house -u 1200 \
    && chown -R house /app \
    && rm -f /usr/bin/qemu-arm-static
USER 1200
ENTRYPOINT ["dotnet", "Template.dll"]