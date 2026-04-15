# HNG Internship — Frontend, Stage 1a Advanced Todo Card (stage 0 task advancement)

## Live Project Overview

This project extends the **Stage 0 Todo Card** into a richer **interactive and stateful single-card experience** using **semantic HTML, modern CSS, and vanilla JavaScript**.

The focus of this stage is:

* interactive editing
* synchronized task states
* expandable long descriptions
* dynamic due-time logic
* stronger accessibility
* responsive layout resilience

---

# What Changed from Stage 0

## 1) Edit Mode Added

The card now supports a fully functional edit workflow.

### Features

* Edit button switches the card into **edit mode**
* Editable fields:

  * title
  * description
  * priority
  * due date
* Save updates the live task state
* Cancel restores the previous visible card state
* Focus returns to the **Edit button** after closing edit mode

### Required Test IDs Included

* `test-todo-edit-form`
* `test-todo-edit-title-input`
* `test-todo-edit-description-input`
* `test-todo-edit-priority-select`
* `test-todo-edit-due-date-input`
* `test-todo-save-button`
* `test-todo-cancel-button`

---

## 2) Stateful Status Synchronization

Task status is now fully interactive and synchronized.

### Supported statuses

* Pending
* In Progress
* Done

### Sync rules implemented

* Checkbox checked → status becomes **Done**
* Checkbox unchecked after Done → status becomes **Pending**
* Status dropdown set to Done → checkbox auto-checks
* UI badge, dropdown, and checkbox remain visually synced

### Required Test ID Included

* `test-todo-status-control`

---

## 3) Priority Visual Indicator

Priority now has a stronger visual treatment.

### Enhancements

* Dynamic left card border accent
* Dynamic colored dot indicator
* Live updates when edited

### Supported levels

* Low → green
* Medium → amber
* High → red

### Required Test ID Included

* `test-todo-priority-indicator`

---

## 4) Expand / Collapse Description

Long descriptions are collapsed by default and can be expanded.

### Behavior

* Long text truncates automatically
* Expand button reveals full content
* Collapse restores truncated state
* Accessible toggle with ARIA

### Accessibility support

* `aria-expanded`
* `aria-controls`
* matching collapsible section id

### Required Test IDs Included

* `test-todo-expand-toggle`
* `test-todo-collapsible-section`

---

## 5) Dynamic Time + Overdue Logic

Time behavior is more granular and state-aware.

### Supported states

* Due in X days
* Due in X hours
* Due in X minutes
* Due now
* Overdue by X hours/minutes
* Completed

### Additional behavior

* Updates every **30 seconds**
* Stops updating when task status becomes **Done**
* Shows explicit overdue badge when late

### Required Test ID Included

* `test-todo-overdue-indicator`

---

# Design Decisions

## UI / UX Choices

The card uses a premium modern UI with:

* glassmorphism card styling
* responsive spacing
* visual hierarchy for status and priority
* expandable inline description flow
* clear CTA buttons
* safe wrapping for long text and tags

## Responsiveness

Optimized for:

* 320px mobile
* 768px tablet
* 1024px+ desktop

### Mobile behavior

* stacked top row
* buttons become flexible
* badges reposition safely
* no horizontal overflow

---

# Accessibility Notes

The implementation includes:

* semantic `<article>` root
* proper heading hierarchy
* labeled form fields with `label for`
* accessible checkbox
* keyboard-focusable buttons
* visible focus styles
* accessible status dropdown
* `aria-live="polite"` for time updates
* expand toggle ARIA support
* full keyboard flow preserved

### Keyboard Flow

Tab order remains:

1. checkbox
2. status control
3. expand toggle
4. edit
5. delete
6. save / cancel in edit mode

---

# Known Limitations

* Focus trap inside edit mode is not implemented (optional bonus requirement)
* Data persistence is in-memory only (page refresh resets state)
* Single-card implementation only (per task brief)

---

# Acceptance Criteria Checklist

## Stage 0 compatibility

* all original test IDs retained
* original semantic structure preserved

## Stage 1a additions

* edit mode functional
* state sync functional
* overdue logic functional
* expand/collapse accessible
* keyboard support maintained
* responsive layout safe
* no overflow with long content

---

# Tech Stack

* HTML5
* CSS3
* Vanilla JavaScript

No external libraries used.

---

# Final Notes

This submission intentionally keeps the solution as a **single highly testable HTML file** to align with the brief’s emphasis on:

* testability
* accessibility
* clean state management
* frontend fundamentals
* UI craftsmanship

The implementation is designed to feel like a **small app-like component** rather than a static card, matching the Stage 1a goal precisely.
