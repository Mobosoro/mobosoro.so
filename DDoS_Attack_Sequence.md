# DDoS Attack Sequence Diagram

```mermaid
sequenceDiagram
    participant Attacker
    participant BotNet
    participant WebServer
    participant Firewall

    Attacker ->> BotNet: Sends attack Packets
    BotNet ->> WebServer: Floods the webserver with requests
    WebServer ->> Firewall: Detects traffic spike
    Firewall ->> WebServer: Does protective  actions
    Firewall ->> BotNet: Blocks suspicious IP addresses
    BotNet ->> WebServer: Continues sending requests
    WebServer ->> Attacker: Legitimate users Cannot connect
    Firewall ->> Attacker: Notifies about blocked IPs
