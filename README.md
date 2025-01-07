Cambium AP Ethernet Monitor
Monitors Cambium access points' ethernet port speeds via SNMP and alerts on degradation.

Features
Real-time ethernet port speed monitoring
Integration with Cambium cnMaestro API
SNMP-based speed checks
Email alerts for degraded speeds
Web dashboard for status overview
Requirements
CentOS 7 or later
Node.js 14+
Access to cnMaestro API
SNMP access to APs
Installation
Download the package:

wget https://github.com/yourusername/cambium-monitor/releases/latest/download/cambium-monitor.tar.gz
Extract:

tar -xzf cambium-monitor.tar.gz
Install:

cd cambium-monitor
sudo ./install.sh
Configuration
Edit /opt/cambium-ap-monitor/config.js:


{
  api: {
    baseURL: 'https://your-cnmaestro-server/api/v2',
    clientId: 'your-client-id',
    clientSecret: 'your-client-secret'
  },
  snmp: {
    community: 'your-community-string',
    version: 2
  },
  alerts: {
    email: {
      host: 'your-smtp-server',
      auth: {
        user: 'your-email',
        pass: 'your-password'
      }
    }
  }
}
Usage
Service Management
Start:


sudo systemctl start cambium-ap-monitor
Status:


sudo systemctl status cambium-ap-monitor
Stop:


sudo systemctl stop cambium-ap-monitor
Web Dashboard
Access at: http://your-server:3000/ethport

Uninstallation

sudo ./uninstall.sh
Logs
View logs:


journalctl -u cambium-ap-monitor
