# Darkweb Monitor

Darkweb Monitor is a comprehensive tool designed to help law enforcement and cybersecurity professionals keep tabs on the dark web. In a world where illegal activities hide behind layers of encryption and anonymity, this project provides a much-needed automated solution to scrape, analyze, and classify dark web content. By leveraging secure connection protocols, advanced scraping techniques, and machine learning for threat detection, Darkweb Monitor transforms raw, unstructured data into actionable intelligence.

---

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
  - [1. Clone the Repository](#1-clone-the-repository)
  - [2. Install System Dependencies](#2-install-system-dependencies)
    - [a. Tor & Privoxy](#a-tor--privoxy)
    - [b. MongoDB](#b-mongodb)
    - [c. Kalitorify](#c-kalitorify)
  - [3. Python Environment Setup](#3-python-environment-setup)
  - [4. Configure Tor and Privoxy](#4-configure-tor-and-privoxy)
  - [5. Frontend Setup](#5-frontend-setup)
- [Usage](#usage)

---

## Introduction

The dark web is often portrayed as an elusive, impenetrable maze of encrypted networks and hidden forums. However, beneath this shroud of secrecy lie activities that are not only illegal but also challenging for traditional investigative methods. Darkweb Monitor was born from the necessity to bridge this gap by automating the process of monitoring dark web forums, scanning for vulnerabilities, and classifying potential threats using state-of-the-art machine learning models.

Inspired by recent research and developments in dark web analysis, this project integrates multiple layers of security and intelligence:
- **Anonymity and Secure Browsing:** Using Tor and Privoxy to establish safe, anonymous connections.
- **Traffic Routing:** Employing Kalitorify to force all system traffic through Tor, ensuring complete network anonymity.
- **Data Scraping and Analysis:** Harnessing Selenium, Requests, and Beautiful Soup for robust data extraction, paired with a Large Language Model for classifying content.
- **Vulnerability Scanning:** Integrating tools like Nmap to detect open ports and exposed directories.

This innovative approach not only helps in gathering critical intelligence but also provides a scalable and efficient method to combat cybercrime on the dark web.  
*Based on insights from recent research in dark web analysis :contentReference[oaicite:0]{index=0}.*

---

## Prerequisites

Before getting started, make sure you have the following installed on your system:

- **Git** – for cloning the repository.
- **Python 3** – for the backend services.
- **Node.js & npm** – for the frontend application.
- **MongoDB** – for data storage.
- **Tor** – for secure, anonymous routing.
- **Privoxy** – for proxy configuration.
- **Kalitorify** – for routing all traffic through Tor.

---

## Installation

### 1. Clone the Repository

Open your terminal and run:
```bash
git clone https://github.com/AdilKhan000/DarkwebMonitor.git
cd DarkwebMonitor
```
# Installation Guide

## 1. System Dependencies

### a. Tor & Privoxy
Install Tor and Privoxy using your package manager (for Debian/Ubuntu):
```bash
sudo apt-get update
sudo apt-get install -y tor privoxy
```

### b. MongoDB
Install MongoDB following the official instructions for your operating system. For Ubuntu:
```bash
sudo apt-get install -y mongodb
```

### c. Kalitorify
Clone Kalitorify:
```bash
git clone https://github.com/brainfucksec/kalitorify.git
```

Update System and Install Dependencies:
```bash
sudo apt-get update && sudo apt-get dist-upgrade -y
sudo apt-get install -y tor curl
```

Install Kalitorify:
```bash
cd kalitorify/
sudo make install
```

Activate Kalitorify:
```bash
sudo kalitorify --tor
```

## 2. Python Environment Setup

Create a Virtual Environment:
```bash
python3 -m venv venv
```

Activate the Virtual Environment:
- On Linux/Mac:
```bash
source venv/bin/activate
```
- On Windows:
```bash
venv\Scripts\activate
```

Install Required Python Packages:
```bash
pip install -r requirements.txt
```

## 3. Configure Tor and Privoxy

### Tor Proxy Setup:
Ensure Tor is running and that it is set to activate the SOCKS proxy on port 9050 (default configuration).

### Privoxy Configuration:
Edit the Privoxy configuration file (typically found at `/etc/privoxy/config`) and add the following line at the end:
```
forward-socks5t / 127.0.0.1:9050
```

Then restart Privoxy:
```bash
sudo systemctl restart privoxy
```

## 4. Frontend Setup

Navigate to the Frontend Folder:
```bash
cd public/dwm
```

Install Node.js Dependencies:
```bash
npm install
```

Run the Frontend Development Server:
```bash
npm run dev
```
This will start the React-based frontend (using Vite) typically at http://localhost:3000.

## Usage

Once the installation and configuration steps are completed, you can:

### Run the Backend:
With your virtual environment activated, run the main Python script (refer to your project-specific instructions) to start data scraping and analysis.

### Access the Frontend:
Open your web browser and navigate to the URL provided by the Vite development server. From here, you can initiate scans, monitor progress, and download detailed reports.

Ensure that Kalitorify is running (with `sudo kalitorify --tor`) to guarantee that all traffic is securely routed through the Tor network.
