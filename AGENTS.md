# Agent Instructions - MultiCamiGo

## Context
MultiCamiGo is a single-file web application for multiplication practice, built using **Vibe Coding** principles. It focuses on high UX, portability, and immediate engagement.

## Technical Stack
- **Architecture:** All-in-one `index.html`.
- **Styling:** Bootstrap 5 with CSS variable overrides. Custom CSS prevents layout shifts during feedback.
- **Audio:** Custom synthesizer via `Web Audio API`. No external MP3s.
- **I18n:** Bilingual support (FR/EN) using a `translations` object and `data-i18n` attributes.
- **Persistence:** `localStorage` for configuration (`mm_config_v1`) and high scores (`mm_records_v1`).

## Implementation Details
- **Records:** High scores use a configuration-based hash. Changing any setting (tables, method, timer) refreshes the record display.
- **Game Engine:**
    - `generateQuestionData()` selects from current tables and handles the `retryQueue`.
    - `submitAnswer()` handles sound, visual feedback, and the pause state for errors.
- **Theme:** Controlled via `data-theme="dark"` on the `<body>`.

## Maintenance
- Ensure all new strings are added to the `translations` object in `index.html`.
- Keep the single-file structure intact.
- Maintain the one-instruction-per-line formatting in JavaScript.