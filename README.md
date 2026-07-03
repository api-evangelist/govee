# Govee (govee)

Govee builds smart lighting and smart-home devices - RGBIC LED strips, light bars, floor and table lamps, string and permanent outdoor lights, plus sensors, humidifiers, heaters, and other connected appliances. The Govee Developer API (v1, hosted at `https://openapi.api.govee.com/router/api/v1`) is a free, cloud REST API authenticated with a `Govee-API-Key` header that lets developers enumerate a user's devices and their capabilities, query live device state, and send control commands - power, brightness, RGB and color-temperature, dynamic light scenes, DIY scenes, and per-segment color and brightness. Device events (for capabilities that support them) are delivered over MQTT, and a separate local LAN API allows direct UDP control on the local network.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/govee/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/govee/refs/heads/main/apis.yml)

## Tags

- Smart Home
- Smart Lighting
- IoT
- LED
- Home Automation
- Device Control

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### Govee Devices API

Enumerate all supported devices in a Govee account and discover each device's capabilities - the sku (product model), device id, user-assigned name, and the typed capability list (on_off, range/brightness, color_setting, segment_color_setting, dynamic scenes, and more) that tells you what commands a device accepts.

- **Human URL:** [https://developer.govee.com/reference/get-you-devices](https://developer.govee.com/reference/get-you-devices)
- **Base URL:** `https://openapi.api.govee.com/router/api/v1`

#### Tags

- Devices
- Discovery
- Capabilities

#### Properties

- [Documentation](https://developer.govee.com/docs/getting-started)
- [API Reference](https://developer.govee.com/reference/get-you-devices)
- [OpenAPI](openapi/govee-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/govee.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/govee.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Govee Device State API

Query the current state and property values of a specific device by sku and device id - power, online status, brightness, color, color temperature, and other capability states. Offline devices return their last known (historical) state; event-only capabilities cannot be queried directly.

- **Human URL:** [https://developer.govee.com/reference/get-devices-status](https://developer.govee.com/reference/get-devices-status)
- **Base URL:** `https://openapi.api.govee.com/router/api/v1`

#### Tags

- Device State
- Query
- Status

#### Properties

- [API Reference](https://developer.govee.com/reference/get-devices-status)
- [OpenAPI](openapi/govee-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/govee.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/govee.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Govee Device Control API

Send control commands to a device by passing a single typed capability - turn power on/off (on_off/powerSwitch), set brightness (range), set an RGB color or Kelvin color temperature (color_setting), toggle features (nightlight, oscillation), select a mode, or drive work_mode and temperature_setting capabilities on appliances.

- **Human URL:** [https://developer.govee.com/reference/control-you-devices](https://developer.govee.com/reference/control-you-devices)
- **Base URL:** `https://openapi.api.govee.com/router/api/v1`

#### Tags

- Device Control
- Commands
- Power
- Color

#### Properties

- [API Reference](https://developer.govee.com/reference/control-you-devices)
- [OpenAPI](openapi/govee-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/govee.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/govee.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Govee Dynamic Scenes API

Retrieve the list of dynamic (light) scenes a device supports - Govee's built-in lighting effects such as Sunrise, Aurora, or Rainbow - each returned as a selectable option that can then be applied through the Device Control API's dynamic_scene capability.

- **Human URL:** [https://developer.govee.com/reference/get-light-scene](https://developer.govee.com/reference/get-light-scene)
- **Base URL:** `https://openapi.api.govee.com/router/api/v1`

#### Tags

- Scenes
- Light Scenes
- Effects

#### Properties

- [API Reference](https://developer.govee.com/reference/get-light-scene)
- [OpenAPI](openapi/govee-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/govee.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/govee.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Govee DIY Scenes API

Retrieve the user-created DIY scenes a device supports - custom lighting effects authored by the user in the Govee Home App - each returned as a selectable option that can then be applied through the Device Control API's diy_scene capability.

- **Human URL:** [https://developer.govee.com/reference/control-you-devices](https://developer.govee.com/reference/control-you-devices)
- **Base URL:** `https://openapi.api.govee.com/router/api/v1`

#### Tags

- DIY Scenes
- Custom Effects

#### Properties

- [API Reference](https://developer.govee.com/reference/control-you-devices)
- [OpenAPI](openapi/govee-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/govee.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/govee.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Govee Segment Color and Brightness API

Address individual segments of RGBIC lights independently via the Device Control endpoint's segment_color_setting capability - set per-segment RGB color (segmentedColorRgb) or per-segment brightness (segmentedBrightness) by passing the target segment index array plus the color or brightness value.

- **Human URL:** [https://developer.govee.com/reference/control-you-devices](https://developer.govee.com/reference/control-you-devices)
- **Base URL:** `https://openapi.api.govee.com/router/api/v1`

#### Tags

- Segment Control
- RGBIC
- Color
- Brightness

#### Properties

- [API Reference](https://developer.govee.com/reference/control-you-devices)
- [OpenAPI](openapi/govee-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/govee.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/govee.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Transports

- **REST** (`https://openapi.api.govee.com/router/api/v1`) — the documented cloud developer API, `Govee-API-Key` header auth.
- **MQTT** (`mqtts://mqtt.openapi.govee.com:8883`, topic `GA/{apiKey}`) — real-time device-event subscription. Not a WebSocket.
- **LAN API** (local UDP) — direct on-network control; multicast discovery to `239.255.255.250:4001`, device replies on `:4002`, commands sent to `:4003`. Enabled per device in the Govee Home App.

There is **no documented public WebSocket API**. See [review.yml](review.yml).

## Common Properties

- [GitHub Organization](https://github.com/Govee-API)
- [LinkedIn](https://www.linkedin.com/company/govee)
- [Website](https://www.govee.com)
- [Documentation](https://developer.govee.com/)
- [Plans](plans/govee-plans-pricing.yml)
- [Rate Limits](rate-limits/govee-rate-limits.yml)
- [Fin Ops](finops/govee-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
