# Govee (govee)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
