<div align="center">

<img src="assets/banner.png" alt="LocalPad++ banner" width="100%">

<br>

**A single-file, offline, Notepad++-style text editor that runs in any web browser.**
Built for jump servers, terminal servers and Citrix sessions where no editor is installed.

![No install](https://img.shields.io/badge/install-none-00a3e0?style=for-the-badge&labelColor=1b1f27)
![Offline](https://img.shields.io/badge/internet-not%20needed-a5d6a7?style=for-the-badge&labelColor=1b1f27)
![Single file](https://img.shields.io/badge/files-1%20HTML-ffb454?style=for-the-badge&labelColor=1b1f27)
![Dependencies](https://img.shields.io/badge/dependencies-0-bb9af7?style=for-the-badge&labelColor=1b1f27)
![License](https://img.shields.io/badge/license-MIT-f7768e?style=for-the-badge&labelColor=1b1f27)

<img src="assets/divider.svg" alt="" width="60%">

</div>

<table>
<tr>
<td width="150" align="center"><img src="assets/logo.png" width="130" alt="Pad-chan"></td>
<td>

**Meet Pad-chan, the LocalPad++ mascot.**
She lives in a single HTML file, needs no admin rights, and never phones home. If the machine has a browser, you have an editor.

> Developed with the help of [Claude](https://claude.ai) (Anthropic).

</td>
</tr>
</table>

<div align="center"><img src="assets/screenshot.png" alt="LocalPad++ editing a bash script in the Deep Blue theme" width="90%"></div>

---

## ⚡ Quick start

<img src="assets/flow.png" alt="Copy one file, double-click it, edit and save" width="100%">

1. Download `index.html` (rename it to `localpad.html` if you like).
2. Copy it to the target machine: RDP clipboard / drive mapping, Citrix file transfer, `scp`, USB, or paste the raw contents into a new `.html` file.
3. Double-click it. It opens in the default browser. Done.

There is no build step and no `npm install`.

## 📋 Requirements

| Requirement | Details |
|---|---|
| **Browser** | Any modern browser: Chrome, Edge (recommended), Firefox, Safari. Chrome / Edge 86+ for direct disk read/write. |
| **Operating system** | Anything that runs that browser: Windows (including Server editions), Linux, macOS. |
| **Install / admin rights** | **None.** |
| **Internet** | **Not needed.** The app makes no network requests. Only the optional "Google / Wikipedia search" menu items open a new tab when you click them. |
| **JavaScript** | Must be enabled. |
| **Disk space** | About 560 KB (the four theme wallpapers are embedded in the file). |
| **Hosting** | None. Open it with `file://`. GitHub Pages is optional. |

<details>
<summary><b>Browser capability notes</b></summary>

- **Chrome / Edge:** *Open* and *Save* use the File System Access API and write straight back to the original file. *Find in Files* (pick a folder) also works.
- **Firefox / Safari:** Files open through the file picker or drag and drop. *Save* downloads a copy instead of overwriting, because those browsers do not expose direct file writes.
- Open tabs and settings are kept in the browser's **localStorage / IndexedDB** and survive a restart. Private / incognito mode or "clear data on exit" policies will wipe them, so save anything important to disk.

</details>

## ✨ Features

<img src="assets/features.png" alt="LocalPad++ feature overview" width="100%">

<details>
<summary><b>Full feature list</b></summary>

- **Tabbed editing** with session restore, recently closed files and recent files
- **Syntax highlighting (23 languages):** C, C++, C#, Java, JavaScript, TypeScript, Go, Rust, PHP, Python, Ruby, SQL, Shell, Batch, PowerShell, JSON, CSS, HTML, XML, Markdown, YAML, INI, Diff
- **Find / Replace / Mark** with Normal, Extended (`\n \t \0 \xNN`) and Regex modes, Find in all open tabs, **Find / Replace in Files**
- **Line operations:** duplicate, delete, join, transpose, move, sort (ascending, descending, ignore case, numeric, by length), remove duplicate / empty lines, reverse
- **Case conversion,** trim whitespace, tab / space conversion, EOL conversion (CRLF / LF / CR)
- **Comment / uncomment,** word completion, auto-indent, brace matching
- **Bookmarks** (toggle, jump, cut / copy / delete bookmarked lines)
- **Column editor,** macro recording and playback (savable, repeatable)
- **Tools:** MD5 / SHA-1 / SHA-256 / SHA-512 hashes (selection or whole file), JSON format / minify, Base64, URL and HTML-entity encode / decode
- **Command palette** (`Ctrl+Alt+P`) that searches every feature
- Word wrap, show whitespace / EOL, zoom, full screen, distraction-free mode, read-only mode, print
- Drag and drop files onto the window to open them

Press `F1` for About and open *Shortcut List* in the Settings menu for every key binding. Browsers reserve `Ctrl+N / T / W / Tab`, so LocalPad++ also binds `Alt+N / T / W / Left / Right`.

</details>

## 🎌 Themes

Pick a theme under **Settings > Style Configurator (Themes)** or in **Preferences**.

<img src="assets/themes.png" alt="Anime themes: One Punch Man, Naruto, Attack on Titan, Chainsaw Man" width="100%">

| Theme | Style | Inspired by |
|---|---|---|
| **Deep Blue** (default look of this project) | Dark | Pad-chan's colours |
| **One Punch Man (Hero Yellow)** | Light | Yellow suit, red gloves, white cape |
| **Naruto (Hidden Leaf)** | Dark | Night-blue shinobi, orange jumpsuit, leaf green |
| **Attack on Titan (Survey Corps)** | Dark | Survey Corps green, wall stone, blood red |
| **Chainsaw Man (Pochita)** | Dark | Charred black, chainsaw orange, crimson |
| Default (Light), Monokai, Solarized Light / Dark | Classic | Notepad++ style |

Each anime theme also ships with a matching **dimmed background wallpaper** that fades out behind the text so code stays easy to read. Change it under **Settings > Preferences** (background image, dim and blur sliders), turn it off from the command palette (*Background Image*), or pick your own image.

> The anime themes are **unofficial, fan-made colour palettes**, and the bundled wallpapers are fan-made artwork. They are not affiliated with or endorsed by the creators or publishers of those series. The artwork belongs to its original artists and rights holders and is **not** covered by the MIT licence below. If you redistribute this project, credit the artists or replace the wallpapers with your own.

<div align="center"><img src="assets/divider.svg" alt="" width="60%"></div>

## 🧭 Use cases

**Locked-down and remote environments**

1. Edit config files on a **jump server / bastion host** with no editor installed
2. Work inside a **Citrix, RDS or VMware Horizon** published desktop where Notepad is removed by policy
3. Use on **Windows Server Core** machines or recovery consoles that have a browser but no GUI editor
4. Quick edits on **kiosks, shared lab PCs and VDI** images you cannot install software on
5. Use on a **customer or client machine** where you are not allowed to install tools

**Sysadmin / DevOps / Support**

6. Edit **hosts files, INI, YAML, JSON, `.conf`, `.env`** and registry-export files
7. Write and tweak **PowerShell, Batch and Bash** scripts before running them
8. **Read and search big log files** with regex, bookmarks and Find in Files
9. **Clean data:** sort lines, remove duplicates and blanks, trim whitespace
10. **Convert line endings** between Windows and Unix before a script breaks on `^M`
11. **Verify downloads and files** with SHA-256 / MD5 without installing a hashing tool
12. **Decode Base64 / URL strings** from tickets, logs and tokens
13. **Pretty-print or minify JSON** from API responses
14. Use as a **scratchpad for commands, ticket notes and runbooks** that survives a browser restart

**Developers and others**

15. Build **bulk edits with the column editor and macros** (generate SQL `INSERT`s, prefix / suffix lines)
16. **Offline use** on air-gapped or regulated networks where cloud editors are not allowed (nothing leaves the machine)
17. **Teaching, workshops and exams** that need a uniform, install-free editor
18. **Portable on a USB stick,** with no registry entries or leftover files

## 🔒 Security and privacy

- One static file. **No telemetry, no analytics, no external scripts, fonts or CDNs.**
- Nothing is uploaded; all processing happens locally in the browser.
- Session data lives in the browser's local storage and is not encrypted. On shared machines, close your tabs or clear site data when you are done.

## 🚀 Hosting on GitHub (optional)

1. Create a repo and add `index.html`, `README.md`, `LICENSE` and the `assets/` folder.
2. *Settings > Pages > Deploy from branch > `main` / root* gives you a hosted copy at `https://<user>.github.io/<repo>/`. On restricted networks, prefer downloading the file and running it locally.
3. Attach `index.html` to a **Release** so users can grab a single file directly.

The `assets/` folder is only used by this README. The app itself (`index.html`) needs nothing else.

## 🤝 Contributing

Issues and pull requests are welcome. The whole app is intentionally **one HTML file with no dependencies**; please keep it that way so it stays easy to copy into restricted environments.

## 📄 License

[MIT](LICENSE). Pad-chan and the project graphics are part of this project and share the same license. The embedded anime wallpapers are third-party artwork and are excluded (see the note under *Themes*).

<div align="center"><sub>Made with ☕ and a little help from Claude.</sub></div>
