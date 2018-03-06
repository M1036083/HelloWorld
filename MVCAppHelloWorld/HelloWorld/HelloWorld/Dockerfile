FROM microsoft/aspnetcore:2.0 AS build-env
WORKDIR /app
EXPOSE 80
COPY *.csproj ./
RUN dotnet restore
COPY . .
RUN dotnet publish -c Release -o /out
COPY /app/out .
ENTRYPOINT ["dotnet", "HelloWorld.dll"]
