# Updating Homeassistant Tuya Local device IP references

## When to use this:
When changing routers or updating the firmware, the DHCP leases or static IPs of devices may change.
Read this and follow the steps *before* updating the firmware or changing the router.

## Steps:

1. Download a backup of the router configuration file.
2. Download the DHCP leases from Mac address to IP address. Sometimes, you can fetch it from the Developer tools by inspecting the network traffic.
    It looks like this:
    ```json
      "D8:D6:68:59:84:04": {
          "ip": "192.168.132.123",
          "ipType": "automatic",
          "leaseExpirationTime": 1765496280,
          "name": "Tuya Ceiling Light Bathroom",
          "originalName": "lwip0",
          "ts": null,
          "tunnel": 0
      },
    ```

    On OpenWrt, it looks like this:
    ```json
    "D8:D6:68:59:84:04": {
      "ipaddrs": [
        "192.168.1.123"
      ],
      "ip6addrs": []
    },
    ```
3. After updating the firmware or changing the router, update the IP references in the Tuya Local configuration in Home Assistant. For each device in the Home Assistant Tuya Local configration:
    1. Open the device configuration to see the old IP address (when on the previous router).
    2. Finding the MAC address in the above saved mapping.
    3. Open the new router dashboard page, and search for the MAC address in the new router dashboard page, to find the new IP address.
    4. Enter that new IP address in the Tuya local configuration and press Submit.
