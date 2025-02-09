FROM mcr.microsoft.com/dotnet/aspnet:5.0 AS base
WORKDIR /app
EXPOSE 80

FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /src
COPY ["Services/UserService/API/UserService.API.csproj", "Services/UserService/API/"]
COPY ["Services/UserService/Application/UserService.Application.csproj", "Services/UserService/Application/"]
COPY ["Services/UserService/Domain/UserService.Domain.csproj", "Services/UserService/Domain/"]
COPY ["Services/UserService/Infrastructure/UserService.Infrastructure.csproj", "Services/UserService/Infrastructure/"]
RUN dotnet restore "Services/UserService/API/UserService.API.csproj"
COPY . .
WORKDIR "/src/Services/UserService/API"
RUN dotnet build "UserService.API.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "UserService.API.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "UserService.API.dll"]
