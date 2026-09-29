# Animated Gate Card

A polished, responsive Home Assistant Lovelace card for gate and other cover entities. Its inline SVG depicts a double-leaf entrance gate, with separate opening and closing animations driven by the entity's live cover state.

The card is display-only: it does not call cover services, change position, fetch external assets, or contain personal entity IDs.

## Features

- Original SVG artwork of an entrance gate, pillars, fence, and driveway.
- Distinct animations for `opening` and `closing`; static open/closed appearance for those states.
- State pill, friendly name, and current position when the cover exposes `current_position`.
- Native entity selector in the card editor; each user chooses their own `cover` entity.
- Responsive layout with Home Assistant theme colors.
- Honors the operating system's reduced-motion preference.
- Unknown, unavailable, and nonstandard cover states degrade gracefully.

## Install with HACS

1. In Home Assistant, open **HACS → ⋮ → Custom repositories**.
2. Add `https://github.com/Liionboy/lovelace-animated-gate-card` with category **Dashboard**.
3. Install **Animated Gate Card** and refresh the browser.
4. Add the card to your dashboard and select a `cover` entity in the visual editor.

This is a HACS Dashboard plugin, not a Home Assistant backend integration. The visual config editor uses the native `getConfigForm` API, available in Home Assistant 2026.6 and later.

## Configuration

The visual editor is recommended. Select any cover entity; no entity IDs are built into the card.

```yaml
type: custom:animated-gate-card
entity: cover.my_gate
title: Entrance gate
```

The card animates in response to the standard Home Assistant cover states: `opening`, `open`, `closing`, and `closed`. The current-position indicator is shown only when the entity supplies a numeric `current_position` attribute.

## Manual resource install

Copy `dist/animated-gate-card.js` to `/config/www/animated-gate-card.js`, add `/local/animated-gate-card.js` as a JavaScript module resource in **Settings → Dashboards → Resources**, refresh the browser, and use `type: custom:animated-gate-card`.

## Development

Dependency-free ES module:

```sh
npm run check
```

## License

MIT. See [LICENSE](LICENSE).
