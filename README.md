# EcoTrace — Improved Starter Prototype

A beginner-friendly recycling tracker built with HTML, CSS, and JavaScript. No external libraries or account are required.

## Run on Ubuntu

1. Download `ecotrace_improved.zip`.
2. Extract it. In most browsers, the ZIP will be in `~/Downloads`.
3. Open Terminal (`Ctrl` + `Alt` + `T`) and run:

   ```bash
   cd ~/Downloads
   unzip ecotrace_improved.zip
   cd ecotrace_improved
   python3 -m http.server 8000 --bind 127.0.0.1
   ```

   If `unzip` is not installed, run `sudo apt install unzip`.

4. Open Firefox or Chrome and visit **http://localhost:8000**.
5. To stop the local server, go back to Terminal and press `Ctrl+C`.

If port 8000 is already in use, use `python3 -m http.server 8001 --bind 127.0.0.1` and open `http://localhost:8001`.

## Verify Records feature

Click **Verify records**. The app recalculates each record's SHA-256 hash from its stored fields and checks:
- The recalculated hash equals the saved hash.
- The first record points to `GENESIS`.
- Every later record's `previousHash` equals the preceding record's hash.

The browser displays a green pass message or a red failure message listing the issue(s).

## Replacing your old project

Recommended: keep a backup of the old folder first. Extract this improved ZIP to a new folder and test it before replacing anything.

The browser saves records under the localStorage key `ecotrace_records_v1`. The improved version keeps that same key and uses the same field order for the hash payload, so records made with the previous starter version should still verify. Do not clear browser data if you want to keep your existing local records.

If you want the improved version to become your main project folder, you can rename the old folder to `ecotrace_backup`, then rename the extracted `ecotrace_improved` folder to `ecotrace_starter` after stopping the server. Be careful to rename the actual folder, not the ZIP file.

## What this prototype is — and is not

It is a local browser demo. Records are stored only in that browser on that device. SHA-256 chaining can make edits detectable when checked against the stored hashes, but it is not a live blockchain, does not store data on a decentralized network, and cannot prevent someone from changing both the record and its hash. Describe these limits honestly in a hackathon submission.
