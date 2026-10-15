# offline-vi

Full archive of the offline speaker recognition & anti-spoofing project
(`voice-indentification`): source, models, docs, **plus** the self-contained
Python 3.8 environment (`venv/`, `python38/`).

The source alone lives at
[anderson-venture/voice-indentification](https://github.com/anderson-venture/voice-indentification).
This repo exists because the full archive is 708 MB and GitHub rejects any
single file over 100 MB, so the `.rar` is stored here as 8 byte-split parts.

## Rebuild the archive

The parts are a plain byte split, not a multi-volume RAR. Join them first,
then extract.

**Windows (cmd):**

```cmd
copy /b voice-indentification.rar.part00 + voice-indentification.rar.part01 + voice-indentification.rar.part02 + voice-indentification.rar.part03 + voice-indentification.rar.part04 + voice-indentification.rar.part05 + voice-indentification.rar.part06 + voice-indentification.rar.part07 voice-indentification.rar
```

**Git Bash / Linux / macOS:**

```bash
cat voice-indentification.rar.part* > voice-indentification.rar
```

## Verify

```bash
sha256sum -c voice-indentification.rar.sha256
```

Every line should report `OK`. The expected hash of the rebuilt archive is

```
b876fd8c06071f75d0b12db447e538b0c1114bbadee67bfaa98d94ce722898f3  voice-indentification.rar
```

On Windows without Git Bash: `certutil -hashfile voice-indentification.rar SHA256`.

## Extract

Extract to **`E:\Project\voice-indentification`** — that exact path. The
`venv\` is not relocatable: `pyvenv.cfg` and the launchers in `venv\Scripts\`
hold absolute paths. See `docs/SETUP.md` inside the archive.
