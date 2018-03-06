FROM microsoft/aspnetcore:2.0 AS base
WORKDIR /app
EXPOSE 80

COPY *.csproj ./
RUN dotnet restore
COPY . .
RUN dotnet build -c Release -o /app
RUN dotnet publish -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "HelloWorld.dll"]
