%%%
Title = "soundfont sidecarfiles"
area = "Internet"
workgroup = "Internet"

[seriesInfo]
name = "midisoundfontsidecarfiles"
value = "draft-soundfont-sidecarfiles-leonvankammen-00"
stream = "IETF"
status = "informational"

date = 2022-08-01 

[[author]]
initials="L.R."
surname="van Kammen"
fullname="L.R. van Kammen"

%%%

<!-- for annotated version see: https://raw.githubusercontent.com/ietf-tools/rfcxml-templates-and-schemas/main/draft-rfcxml-general-template-annotated-00.xml -->

.# Abstract

A simple, implicit method for media players to automatically load soundfont files (.DLS or.SF2) when playing MIDI files, enhancing the playback experience without requiring user configuration.

{mainmatter}

# MIDI Soundfont Sidecar specification

* **Level:** 0
* **Version:** 1.0

1. **Sidecar File Detection:**

- **Primary:** Media players SHOULD first look for a `.DLS` sidecar file with the exact same name as the MIDI file (excluding the file extension).
- **Fallback:** If a `.DLS` file is not found, media players SHOULD then look for a `.SF2` sidecar file with the same naming convention.

2. **File Naming Convention:**

- The sidecar file MUST have the same name as the MIDI file, differing only by the file extension (`.DLS` or `.SF2`).
- **Example:**
 - `mysong.mid` → `mysong.DLS` (primary) or `mysong.SF2` (fallback)

3. **Playback Behavior:**

- Upon finding a matching sidecar file, the media player SHOULD load the soundfont from this file for the duration of the MIDI file playback.
- If no sidecar file is found, the media player SHOULD fall back to its default soundfont or configured soundfont settings.

4. **Implementation Notes:**

- This spec is designed to be lightweight and easy to implement, encouraging broad adoption across various media players and platforms.
- Implementors are encouraged to provide an option for users to override this behavior if desired (e.g., always using a default soundfont, disabling sidecar loading).

5. **Relation to RMID and Other Formats:**

- This specification might serve as an 'override' feature for RMID files, allowing users to play RMID content with a custom soundfont without re-encoding.
- It is format-agnostic, meaning it can be applied to various MIDI file formats beyond RMID.

**Adoption and Feedback:**

- Implementors and interested parties are invited to provide feedback and suggestions for future revisions.
- A list of adopting media players and software will be maintained to track the spec's ecosystem impact.

**Revision History:**

- **v0.5:** Initial release.

---

**Next Steps:**

1. **Review and Feedback:** Circulate this draft among the mentioned projects (VLC-player, fluidsynth, etc.) and relevant communities for feedback.
2. **Revision (if necessary):** Based on the feedback received, revise the spec to better meet the needs of implementors and users.
3. **Publication and Promotion:** Publish the finalized spec on a dedicated webpage or within relevant developer resources, and promote it across music tech, developer, and open-source communities.

* leonvankammen|isvery.ninja

# IANA Considerations

This document has no IANA actions.

# Acknowledgments

TODO acknowledge.
