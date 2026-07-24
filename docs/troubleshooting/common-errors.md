# Troubleshooting

## Overview

This document records common issues encountered during the setup of the SIEM Detection Lab and their solutions.

---

## Issues Encountered

### Wazuh Installer Stuck

**Problem**

The installation appeared to stop while installing the Wazuh Indexer.

**Cause**

The package download required additional time because the Wazuh Indexer package is large.

**Status**

Resolved.

---

### SSH Service Inactive

**Problem**

The SSH service was inactive after installation.

**Solution**

Enabled and started the SSH service using systemctl.

---

### Guest Additions

**Problem**

Clipboard sharing was unavailable.

**Solution**

Installed VirtualBox Guest Additions and enabled bidirectional clipboard.
