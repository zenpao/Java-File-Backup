# Java-File-Backup (FileChamber)

A Java Swing desktop app that automatically backs up a single file to a chosen folder on a repeating timer — creating a timestamped copy each interval, even while the file is in use.

**A ready-to-use build is available in [`/dist`](./dist) — `app_betaFileChamber.jar` requires a Java Runtime, or run `FileChamber BETA.exe` directly on Windows.**

## Description

FileChamber lets you pick a source file and a destination folder, choose a backup interval, and then start automatic backups: on each interval, it copies the source file into the destination folder as a new file named `<original-name>_<timestamp>.<extension>`, preserving file attributes. This creates a running history of snapshots to guard against accidental deletion or data loss.

Per the project's own distributed README (Build Version 1.0 Beta, 2016): this is freeware, made for educational purposes, and the author advises running it from a drive root (e.g. `C:\`, `D:\`) rather than a restricted folder like `Program Files`.

## Features

- Select a source file to back up (`Browse..`)
- Select a destination folder to save backups to
- Choose a backup interval: 5, 10, 20, 30, 45, or 60 seconds
- **Start** automatic backups on a repeating timer
- **Pause / Stop** automatic backups at any time
- Each backup is saved as `<original-filename>_<yyyy-MM-dd_HH-mm-ss-SSS>.<extension>`, with file attributes preserved and existing files of the same name overwritten

## Tech Stack

- **Java** (Swing/AWT for the GUI)
- Built with **NetBeans 8.1** (Ant-based build, see `build.xml` / `nbproject/`)

## Prerequisites

- **Java Runtime Environment (JRE)** — to run the packaged jar or `.exe`
- **Java Development Kit (JDK)** + NetBeans (or another Java IDE/Ant) — only needed if building from source

## Installation

Clone the repository:

```bash
git clone https://github.com/paoradox/Java-File-Backup.git
cd Java-File-Backup
```

To build from source, open the project in NetBeans (or run Ant directly using `build.xml`).

## Usage

### Option 1: Run the packaged build (recommended)

From [`/dist`](./dist):

```bash
java -jar "app_betaFileChamber.jar"
```

Or, on Windows, run `FileChamber BETA.exe` directly.

> Per the author's note: run the app from a drive root (e.g. `C:\`, `D:\`) rather than a subfolder that requires special permissions (e.g. `Program Files`).

### Workflow

1. Click the file field to browse for and select the file you want to back up.
2. Click **Browse..** to choose the folder backups will be saved to.
3. Choose a backup interval from the **Every (seconds)** dropdown.
4. Click **Start** to begin automatic timestamped backups.
5. Click **Pause / Stop** at any time to stop backing up.

## Project Structure

```
Java-File-Backup/
├── dist/
│   ├── app_betaFileChamber.jar   # Packaged runnable jar
│   ├── FileChamber BETA.exe       # Windows launcher for the jar
│   ├── README.TXT                 # Original author's distribution notes
│   └── README.md                  # Original author's project description
├── src/
│   └── app_filechamber/
│       ├── App_betaFileChamber.java  # Main application window and backup logic
│       ├── App_betaFileChamber.form  # NetBeans GUI form definition
│       ├── App_FileChamber.java      # Unused/empty entry-point subclass
│       └── *.png                     # App icon/branding images
├── res/                           # Additional branding images/assets
├── build/                         # Compiled classes (Ant build output)
├── nbproject/                     # NetBeans project configuration
├── build.xml                      # Ant build script
└── manifest.mf                    # Jar manifest
```

## License

Apache License 2.0
