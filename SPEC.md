# SPEC.md - MultiCamiGo

## 1. Core Identity
*   **Name:** MultiCamiGo
*   **Platform:** Single-file web application (PWA) designed for mobile-first usage.
*   **Target Audience:** Children learning multiplication tables (and adults wanting to sprint).
*   **Design Philosophy:** "Vibe Coding" – prioritize fun, responsiveness, and immediate visual feedback.
*   **Visual Theme:**
    *   **Palette:** Purple (`#9b59b6`), Soft Purple (`#f5edfa`), and Light Blue (`#e3f2fd`).
    *   **Dark Mode:** Deep blue/black background with high-contrast purple accents.
    *   **Elements:** Bootstrap 5 with custom overrides (no default blue).

## 2. Functional Requirements

### 2.1 Configuration
*   **Table Selection:** Checkbox grid for tables 1 through 13.
*   **Question Formats:** Four togglable formats: `a x b = ?`, `b x a = ?`, `a x ? = c`, `? x b = c`.
*   **Input Methods:**
    *   **Buttons (Default):** Grid of choice buttons. 3-5 items in a single row; 6-8 items in two rows.
    *   **Keyboard:** Numeric input field.
*   **Timers (per question):** Unlimited, 5s (Expert), 10s (Normal), 20s (Easy).
*   **Bilingual:** Seamless switch between French 🇫🇷 and English 🇬🇧.

### 2.2 Game Modes
1.  **Series (Fixed):** complete 10 to 50 correct answers. Failed questions are re-queued for later mastery.
2.  **Streak (Suite):** reach X correct answers in a row. Errors reset the counter.
3.  **Sprint (Time Attack):** highest score in 1, 2, 3, or 5 minutes.

### 2.3 Gameplay Loop & Feedback
*   **Correct:** Sound "Ding!" (sequence), Green equation, random fun emoji, 1s delay.
*   **Incorrect / Timeout:** Sound "Buzz" (Sawtooth 150Hz), Red equation with correct answer. Interface pauses for "Suivant ➡" button click.
*   **Stability:** Interaction zone has a fixed height to prevent layout shifts.

### 2.4 Persistence & Records
*   **Storage:** `localStorage` for config and records.
*   **Smart Records:** High scores are hashed based on the exact configuration (tables, mode, input type, timer).
*   **Victory:** Confetti and mistake summary ("À revoir").

## 3. Technical Implementation
*   **Architecture:** Single `index.html` file.
*   **Audio:** Native `Web Audio API` synthesizer.
*   **UX:** `touch-action: manipulation` for mobile responsiveness.
