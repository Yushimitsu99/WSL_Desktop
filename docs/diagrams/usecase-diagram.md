# Use Case Diagram

This diagram illustrates the interactions between a user and the WSL interface to manage instances and install applications.

```mermaid
%%{
init: {
  'theme': 'base',
  'themeVariables': {
    'primaryColor': '#ffcc00',
    'edgeLabelBackground':'#ffffff',
    'actorBorder': '#000000',
    'actorBkg': '#ffcc00',
    'actorTextColor': '#000000'
  }
}
}%%
%% A Mermaid Use Case Diagram %%
graph TD
    actor User as User
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
