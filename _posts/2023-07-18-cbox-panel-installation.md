---
title: Connectivity Box Panel Installation
date: 2023-07-18 15:20:00 +0530
categories: [Connectivity Box panel, Panel-Installation]
tags:
  [
    cbox,
    services,
    cbox usage,
    aggregator,
    crawler,
    scrapper,
    control panel,
    admin panel,
    monitoring,
  ]
author: ayush
---

If your connectivity box is not registered with zMed, the Installation Script will give you a unique cBox id. You must email the cBox ID to zMed to register and Authorize the cBox. Once the cBox is authorized by zMed, run the installation script again.

## Connectivity Box Panel Installation

- Step 1: Download the connectivity box panel installation zip file

```bash
sudo wget https://openbuckets.zmed.tech/zexe/cbox/install/cbox-install.zip --no-check-certificate
```

- Step 2: Install unzip utility:

```bash
sudo apt-get install unzip
```

- Step 3:  Unzip the downloaded zip file and run the installation script

```bash
sudo unzip cbox-install.zip
cd cboxPanel
sudo chmod +x install
sudo ./install
```

**- Verify the installation using the instructions provided at the end of the installation script**
