#!/usr/bin/env bash
set -ue

DRONEIP=${1:-"192.168.1.1"}

echo "Removing binaries..."
{( sleep 1; echo "
  rm /bin/wpa_*
";) | telnet $DRONEIP > /dev/null; } | sleep 1 && echo "wpa_supplicant uninstalled."