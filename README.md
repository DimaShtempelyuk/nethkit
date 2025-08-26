# Todo

## App shell & navigation
- [ ] Scaffold app shell (state store, router, global toasts).
- [ ] Routes: **Start → Swipe → Review → Export/Forge → Settings**.
- [ ] Persist last route + session guard (resume or new session).
- [ ] Keyboard hints (no hard hotkeys yet; show discoverable UI).
- [ ] Error boundary + fallback screen.

## Scanner
- [ ] Select root folder(s).
- [ ] Support **WAV/MP3**; optional recursion; ignore hidden/system files.
- [ ] Compute `content_hash` (stable, based on decoded audio bytes + path salt).
- [ ] Extract basic metadata (duration, sample rate, channels, bitrate).
- [ ] Write scan stats to session.

## Player service
- [ ] Instant play/pause; seek; volume.
- [ ] Preload next item (smart buffer).
- [ ] Surface playback errors as toasts and mark file as problematic.
- [ ] Respect autoplay toggle from Swipe UI.

## Swipe UI
- [ ] Large waveform/preview (fallback to filename if no waveform).
- [ ] Big action buttons (Accept / Decline / Skip).
- [ ] Autoplay toggle.
- [ ] “Decline Folder/Kit” quick action (apply to current folder scope).
- [ ] Dual-view switch when not in “swiping mode”.

## Review (dual-view)
- [ ] Summary counts: accepted / declined / skipped / duplicates.
- [ ] List with remove/undo.
- [ ] Open-in-Explorer / Reveal-in-Finder per item.
- [ ] Search/filter by filename, folder/kit, duration, decision tag.

## CSV ledger
- [ ] Append/resume on re-scan (no duplicates).
- [ ] Implement **v1 schema** (id, path, content_hash, decision, label, timestamp, notes, …).
- [ ] Safe write (temp file + atomic move).
- [ ] Export current session snapshot.

## Forge wizard (Export/Forge)
- [ ] Pick **output root**.
- [ ] Copy/move strategy (choose per run).
- [ ] **label → subfolder** mapping UI (preview resulting tree).
- [ ] Conflict rules (skip/overwrite/rename with counter).
- [ ] Dry-run preview + summary before executing.
- [ ] Progress bar + cancel; final report.

## Session autosave
- [ ] Autosave position/state (current file, queue, decisions, settings).
- [ ] Resume prompt on launch (Continue / Discard).
- [ ] Version guard for schema changes.

## Settings page
- [ ] Config editor (paths, recursion, conflict rule default, autoplay default).
- [ ] Label manager (create/rename/delete, color/icon).
- [ ] Import/export settings JSON.

## Duplicate handling
- [ ] Build hash index during scan.
- [ ] Auto-skip true duplicates; show badge in UI.
- [ ] Per-item override (force include even if duplicate).
- [ ] Report duplicates in Review counts.

## Extensibility stub
- [ ] Reserve **.nfo branding hook** (no logic yet).
- [ ] Plumb placeholder in Forge (optional file drop per kit).

---

### Engineering hygiene (nice-to-have, still scoped)
- [ ] Basic unit tests for hash, scanner, CSV IO.
- [ ] E2E happy path: scan → swipe few items → forge dry-run → export.
- [ ] Telemetry toggle (anonymous counts only) + logs directory.
- [ ] CI lint/format/test.
