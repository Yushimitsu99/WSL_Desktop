# Use Case Diagram

This diagram illustrates the interactions between a user and the WSL interface to manage instances and install applications.

```mermaid
%%{
init: {
  'theme': 'base',
  'themeVariables': {
    'primaryColor': '#858E90',    
    'primaryTextColor': '#ffffff', 
    'primaryBorderColor': '#2a3137',
    'secondaryBorderColor': '#485663', 
    'lineColor': '#485663', 
    'secondaryColor': '#86a3b4',   
    'tertiaryColor': '#99b4b7', 
    'tertiaryTextColor': '#ffffff', 
    'tertiaryBorderColor': '#becbce' 
  }
}
}%%
graph TD
    User -- Start/Stop/Delete WSL Instances --> UICase
    User -- Install Applications on WSL --> InstallCase
    User -- Monitor RAM & CPU Usage --> MonitorCase
    User -- Transfer Files to WSL --> TransferCase
    subgraph "WSL Interface"
        UICase(Start/Stop/Delete WSL Instances)
        InstallCase(Install Applications on WSL)
        MonitorCase(Monitor RAM & CPU Usage)
        TransferCase(Transfer Files to WSL)
    end
