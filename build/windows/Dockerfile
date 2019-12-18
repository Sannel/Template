ARG tag=3.1
FROM mcr.microsoft.com/dotnet/core/runtime:${tag} AS base
WORKDIR /app
EXPOSE 8080
EXPOSE 8443

COPY Template/ .
USER ContainerUser
ENTRYPOINT ["dotnet", "Template.dll"]