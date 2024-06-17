# Diagramme de Séquence

Ce diagramme décrit l'interaction pour démarrer une instance WSL et installer une application.

```mermaid
sequenceDiagram
    participant User
    participant UI as User Interface
    participant VM as WSLViewModel
    participant Manager as WSLManager
    participant WSL as WSLInstance
    participant Installer as ApplicationInstaller

    User ->> UI: Demander à démarrer l'instance WSL
    UI ->> VM: startWSL(distributionName)
    VM ->> Manager: startWSL(distributionName)
    Manager ->> WSL: start()
    WSL -->> Manager: Instance démarrée
    Manager -->> VM: Instance démarrée
    VM -->> UI: Afficher instance démarrée

    User ->> UI: Demander à installer l'application
    UI ->> VM: installApp(distributionName, appName)
    VM ->> Manager: installApp(distributionName, appName)
    Manager ->> Installer: installApp(WSL, appName)
    Installer ->> WSL: sudo apt update && sudo apt install -y appName
    WSL -->> Installer: Application installée
    Installer -->> Manager: Application installée
    Manager -->> VM: Application installée
    VM -->> UI: Afficher application installée
