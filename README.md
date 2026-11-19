# Broadlink Lifaair for Home Assistant

This repository overrides Home Assistant’s built-in **Broadlink** integration with a version that adds support for **LIFAair** air purifiers, specifically the [LIFAair LA330](https://lifa-air.com/products/lifa-air-la330-air-purifier).

## Installation

In HACS, open **Integrations** → **⋮** → **Custom repositories**, add
`https://github.com/pit3k/broadlink-lifaair` with category **Integration**, then
install **Broadlink LIFAair** and restart Home Assistant.

To test unpushed local changes, HACS cannot fetch the working tree. Copy this
repository's `custom_components/broadlink` directory into your Home Assistant
configuration's `custom_components` directory, replacing the existing
`broadlink` custom component, then restart Home Assistant. Keep the existing
config entry; the integration domain remains `broadlink`.

Test the purifier's on/off controls, **Auto**, **Night**, **Turbo**, and
**Anti-Allergy** presets, manual speed changes, and speed **0** (which should
turn it off). Also check that the fan reports off when its mode is off even if
the device reports a nonzero speed, the diagnostic purifier-online entity
tracks connectivity, and temperature and humidity become unavailable when the
purifier is offline. Verify available PM2.5, CO₂, TVOC, and formaldehyde sensor
entities update.