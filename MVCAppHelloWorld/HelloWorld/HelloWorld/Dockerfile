FROM microsoft/aspnetcore-build:2.0
WORKDIR /app
EXPOSE 80
COPY *.csproj ./
RUN dotnet restore
COPY . .
RUN dotnet publish -c Release -o /out
COPY /app/out .
ENTRYPOINT ["dotnet", "HelloWorld.dll"]
