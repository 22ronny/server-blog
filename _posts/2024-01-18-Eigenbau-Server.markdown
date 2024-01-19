---
layout: post
title: "Eigenbau Server"
---


## Vorbereitung
**Problem 1:**  
Private Kunden bekommen von Internetbetreibern oft nur Private IP Adressen.  
Hier ist es nicht möglich von Außerhalb über die Ports ins eigene Netz zuzugreifen.  
Deshalb musste ich hier erst eine Öffentliche IP Beantragen (Unterschiedlich je nach Betreiber).

**Problem 2:**  
Öffentliche IP´s sind nicht Statisch, was heist sie ändern sich ca. alle 24h.  
Für dieses Problem gibt es verschiedene Betreiber wie NO-IP oder Duck DNS.  
Dorthin wird die gerade aktuelle IP bei änderung übermittelt.



## Verwendete Hardware
* **CPU:** AMD Athlon 200GE, 2 Cores / 4 Threads
* **RAM:** Corsair 32Gb DDR4 2100Mhz@2667Mhz
* **HDD** 3 x 3.000GB Seagate RAID-Z1
* **SSD** SanDisk 512GB  für OS. LXC und VM
  

## Verwendete Serversoftware
Proxmox Virtual Environment ist eine komplette Open Source-Virtualisierungsplattform für Server.  
Es kombiniert KVM- und Container-basierte Virtualisierung und verwaltet virtuelle Maschinen, Container, Storage, virtuelle Netzwerke und Hochverfügbarkeits-Cluster übersichtlich über die zentrale Managementoberfläche.

[![Bildvorschau](\server-blog\image\serverBig.jpg)](\server-blog\image\serverBig.jpg){:target="_blank"}

## Verwendete LXC (Linux Container)

![alternativtext](\server-blog\image\lxc.jpg)

### 200 Datenserver
 SMB - Protokoll 
 ZFS Raid-Z1 an Container durchgereicht

 ![alternativtext](\server-blog\image\200.jpg)


### 202 WireGuard
Ein VPN bietet eine verschlüsselte Verbindung für den externen Zugriff auf das Intranet.

### 203 influxDB
InfluxDB ist spezialisiert auf die effiziente Speicherung und Abfrage von Zeitreihendaten, was es im Vergleich zu anderen Datenbanken besonders gut für Anwendungen wie Monitoring, IoT und Analysen von zeitbasierten Ereignissen macht.  
In meinem Fall für die Wetteraufzeichnung. Aktuell aber läuft meine Wetteraufzeichnung auf einem Raspberry.

### 204 Grafana
Grafana ist eine Open-Source-Plattform für die Visualisierung und Überwachung von Daten, die es ermöglicht, Daten aus verschiedenen Quellen in ansprechenden Dashboards darzustellen.

 ![alternativtext](\server-blog\image\Grafana.jpg)

