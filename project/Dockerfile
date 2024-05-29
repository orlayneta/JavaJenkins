#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.
FROM microsoft-sdk-dotnet-6-0-juan AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443
FROM microsoft-sdk-dotnet-6-0-juan AS build

FROM base AS final
WORKDIR /app

RUN apt-get update
RUN apt-get install net-tools

RUN rm -rf /app
ADD ./ /app/
RUN dotnet build "HolaMundo.csproj" -c Release
ENTRYPOINT ["dotnet", "/app/bin/Release/net6.0/HolaMundo.dll"]