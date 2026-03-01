## Umbrel Community App Store - JAYDEVSTACK

This repository contains the JAYDEVSTACK Community App Store for Umbrel, featuring the Miner Radar application.

## Apps in this store:

### Miner Radar
Monitor your Bitcoin miners in real-time. Track hashrate, temperature, and performance metrics across all your mining hardware from a single dashboard.

## Installation

Add this Community App Store to your Umbrel:

1. Open your Umbrel dashboard
2. Go to App Store settings
3. Add Community App Store with this URL:
   ```
   https://github.com/jaydevstack/jaydevstack-umbrel-community-app-store
   ```

## Deployment Instructions

After making changes to the app configuration:

1. Commit and push changes to GitHub
2. On your Umbrel server, clear the cached docker-compose.yml:
   ```bash
   sudo rm -rf /home/umbrel/umbrel/app-data/jaydevstack-store-miner-radar/
   ```
3. Restart the Umbrel daemon:
   ```bash
   sudo systemctl restart umbreld
   ```
4. Uninstall and reinstall the app from the Umbrel UI

## Network Configuration

The Miner Radar app uses `network_mode: host` for the server container to access miners on your local network (192.168.x.x addresses). The app_proxy uses `extra_hosts` with `host-gateway` to communicate with the server running in host mode.

## App Details

- Store ID: `jaydevstack-store`
- App ID: `jaydevstack-store-miner-radar`
- External Port: 3021
- Internal Port: 3000
- Docker Image: `jaydevstack/miner-radar:v0.1.0`