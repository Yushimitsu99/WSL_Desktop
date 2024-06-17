# Sequence Diagram

This diagram describes the interaction to start a WSL instance and install an application.

```mermaid
sequenceDiagram
    participant User
    participant UI as User Interface
    participant VM as WSLViewModel
    participant Manager as WSLManager
    participant WSL as WSLInstance
    participant Installer as ApplicationInstaller

    User ->> UI: Request to start WSL instance
    UI ->> VM: startWSL(distributionName)
    VM ->> Manager: startWSL(distributionName)
    Manager ->> WSL: start()
    WSL -->> Manager: Instance started
    Manager -->> VM: Instance started
    VM -->> UI: Display instance started

    User ->> UI: Request to install application
    UI ->> VM: installApp(distributionName, appName)
    VM ->> Manager: installApp(distributionName, appName)
    Manager ->> Installer: installApp(WSL, appName)
    Installer ->> WSL: sudo apt update && sudo apt install -y appName
    WSL -->> Installer: Application installed
    Installer -->> Manager: Application installed
    Manager -->> VM: Application installed
    VM -->> UI: Display application installed
