#!/usr/bin/env bash
set -ue

DRONEIP=${1:-"192.168.1.1"}

echo "Rebooting drone..."
{( sleep 1; echo "
  reboot
";) | telnet $DRONEIP > /dev/null; } | sleep 1 && echo "Done."
