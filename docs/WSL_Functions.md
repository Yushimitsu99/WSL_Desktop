### WSL COMMANDS

------------

#### 1. Start a WSL instance:
- `wsl --distribution <DistributionName>`
- `wsl -d <DistributionName>`

#### 2. Stop a WSL instance:
- `wsl --terminate <DistributionName>`
- `wsl -t <DistributionName>`

#### 3. Delete a WSL instance:
- `wsl --unregister <DistributionName>`

#### 4. List WSL instances:
- `wsl --list --verbose`
- `wsl -l -v`

#### 5. Install applications on a WSL instance:
- `wsl -d <DistributionName> -- sudo apt update && sudo apt install -y <AppName>`

#### 6. Get RAM and CPU Usage:
- `wsl -d <DistributionName> -- top -b -n 1 | head -n 10`
- `wsl -d <DistributionName> -- free -m`
- `wsl -d <DistributionName> -- mpstat`

#### 7. Open File Explorer in the directory of a WSL instance:
- `wsl -e bash -c "cd /home; explorer.exe ."`

#### 8. Transfer files to a WSL instance:
- `wsl cp /mnt/c/Users/YourUserName/PathToYourFile /home/YourWSLUser/PathInWSL`
