# monitoring-supervision
Configuration de Zabbix, Grafana et scripts de surveillance système.
#!/bin/bash
echo "Installation de l’agent Zabbix..."
apt update && apt install -y zabbix-agent

echo "Configuration de l’agent pour communiquer avec le serveur Zabbix..."
echo "Server=192.168.1.100" >> /etc/zabbix/zabbix_agentd.conf
echo "ServerActive=192.168.1.100" >> /etc/zabbix/zabbix_agentd.conf

echo "Redémarrage du service Zabbix..."
systemctl restart zabbix-agent
systemctl enable zabbix-agent
echo "Agent Zabbix installé et configuré !"
