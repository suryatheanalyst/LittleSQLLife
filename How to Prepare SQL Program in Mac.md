# How to Prepare SQL Program in Mac using Docker and Azure Data Studio

## Install Docker
You can access the installer of Docker through this website: [Docker Website](https://docs.docker.com/desktop/install/mac-install/)
Please be aware of your Mac chipset whether Intel or Silicon chipset.

## Install Azure Data Studio
You can access the installer of Microsoft Azure Studio through this website: [Azure Data Studio Website](https://learn.microsoft.com/en-us/sql/azure-data-studio/download-azure-data-studio?view=sql-server-ver16&tabs=redhat-install%2Credhat-uninstall)
Please also be aware of the version of Azure Data studio.

## Pull Connection Azure SQL Edge
Run this on your Mac terminal: 
```
docker pull mcr.microsoft.com/azure-sql-edge
```
You can check the updated link through this website: [Azure SQL Edge in Docker Web](https://hub.docker.com/_/microsoft-azure-sql-edge)

## Install Azure SQL Edge
Run this on your terminal, and don't forget to replace password.
```
docker run -e "ACCEPT_EULA=1" -e "MSSQL_SA_PASSWORD={Password}" -e "MSSQL_PID=Developer" -e "MSSQL_USER=SA" -p 1433:1433 -d --name=sql mcr.microsoft.com/azure-sql-edge
```

## Configuring Host and Connection
- Open the Docker Apps. Please make sure both Image and Container are running.
- Open the Azure Data Studio and create a connection.
    - Server: localhost
    - Authentication Type: SQL Login
    - Username: SA
    - Password: {Your Password}
    - Click Log In
