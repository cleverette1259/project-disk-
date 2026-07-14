
✅ Battery can be replaced without removing the display.

✅ USB-C board can be replaced without removing the motherboard.

✅ Buttons can be serviced independently.

✅ Display cable is accessible after removing only the rear cover.

Examples of poor design:

❌ Battery glued beneath the motherboard.

❌ Screen permanently bonded to the frame.

❌ Headphone jack soldered directly to the main board when a replaceable daughterboard is practical.

Project Disc should always favor layouts that reduce repair time and simplify maintenance, even if this requires a slightly larger enclosure.

---

# 🚀 Now... the real engineering starts.

This is where most hardware projects either succeed or fail.

Most people do this:

> "I need a Raspberry Pi."

Then:

> "What screen should I buy?"

Then:

> "Now I need buttons."

Eventually they realize nothing fits together.

---

## We're going to do it backwards.

We're going to design the **product first**.

Then we'll choose the hardware that best matches that design.

That's how professional hardware teams work.

---

# 📁 docs/

## File: `SYSTEM_ARCHITECTURE.md`

This will become the single most important document in the project.

Everything else points back to it.

---

# Project Disc Architecture

```text
                        USER

                          │

                Physical Controls

                          │

        ┌─────────────────┼─────────────────┐

        │                 │                 │

     Display          Disc Core         LEDs

        │                 │                 │

        └────────────┬────┴─────┬───────────┘

                     │          │

                Audio Engine  Storage

                     │          │

                     └────┬─────┘

                          │

                        DAC

                          │

                 Headphones / AMP
```

Notice something?

The DAC is **one module**, not the center of the system. That means we can upgrade it later without redesigning everything.

---

# Step 1 — Define the Modules

I think we should define every major hardware module before we pick any specific parts.

## Module 1 — Display Assembly

Responsible for:

* Circular LCD
* Touch (optional)
* Front lens
* Backlight
* Mounting points

---

## Module 2 — Compute Module

Responsible for:

* Running Disc Core
* User interface
* File management
* Networking
* Playback control

---

## Module 3 — Audio Module

Responsible for:

* DAC
* Headphone amplifier
* Audio filtering
* Headphone jack

Keeping the audio section physically separate from noisy digital electronics will help reduce interference.

---

## Module 4 — Battery Module

Responsible for:

* Battery
* Charging
* Battery management
* Fuel gauge

---

## Module 5 — I/O Module

Responsible for:

* USB-C
* Expansion
* Future accessories

Making this a separate board means a damaged USB-C port can be replaced without replacing the main board.

---

## Module 6 — Control Module

Responsible for:

* Volume encoder
* Playback buttons
* Power button

These should be mounted in a way that reduces mechanical stress on the main electronics.

---

## Module 7 — Lighting Module

Responsible for:

* RGB LEDs
* Ambient effects

Optional for future revisions, but the software should be ready for it.

---

# Before We Choose Hardware...

I want us to define **requirements** rather than parts.

For example:

Instead of saying:

> "Use a Raspberry Pi Zero."

We say:

### Compute Module Requirements

* Boots in under 15 seconds (target).
* Renders the UI smoothly.
* Supports Wi-Fi.
* Runs Linux.
* Supports our chosen display.
* Has enough performance for audio playback and animations.
* Fits within our power budget.

Then we compare hardware against those requirements.

That way, if something better than a Raspberry Pi comes along in two years, we can swap it in without changing the project's goals.

---

# 🎯 I Think Our Next Deliverable Should Be the Product Requirements Document (PRD)

This is what real hardware companies write before they build prototypes.

Instead of saying:

> "We're making a music player."

It says things like:

* The device **shall** boot in less than 15 seconds.
* The device **shall** support FLAC playback.
* The device **shall** survive a 1-meter drop (long-term goal).
* The battery **shall** be replaceable.
* The display **shall** remain readable indoors.
* The user **shall** be able to replace the battery with basic hand tools.

These are measurable requirements, not ideas. They give us something concrete to design and test against.

## One Suggestion for Keeping This Manageable

As this grows, I think we should split the work into three parallel tracks:

1. **📘 Documentation** – specifications, handbooks, and design records.
2. **🔩 Hardware** – enclosure, electronics, and PCB layout.
3. **💻 Software** – Disc Core, UI, and synchronization.

That way, we can make steady progress in each area without getting overwhelmed, and every decision in one track is supported by the others. I think that's the closest we'll get to a professional development workflow while still keeping it fun and approachable.
