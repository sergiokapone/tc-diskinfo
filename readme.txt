DiskInfo 1.4.9 - Lister plugin for Total Commander (32 and 64 bit)
=================================================================

Detailed disk information plus a DirSizeCalc-style space analyzer with an
interactive treemap. Languages: English, Russian, Ukrainian.

TABS
  Volume      label, serial, file system, GUID, mount points, cluster size,
              free space (quota aware), NTFS internals ($MFT), FS feature flags
  Device      vendor, model, firmware, bus, SSD or HDD, TRIM, logical/physical
              sector (512n/512e/4Kn), write cache, GPT/MBR, partition alignment
              (partition table needs administrator rights)
  Duplicates  duplicate files in the folder (see CHANGES, 1.3)
  All drives  cards for every drive letter with usage bars; click to inspect
  Analysis    background scan of a folder or whole drive:
              - interactive treemap, click a folder to drill down
              - folder contents with sizes, percentages, file counts
              - file types, heaviest extensions
              - files by age (last modified) and by size
              - the folder list shows sub-folders and the files of the open folder (sorted by size
                or by name); click a folder to enter it, a file to copy its path, Delete moves the
                row under the mouse to the Recycle Bin
              - file mask filter (*.jpg;*.png, or "all but")
              - the folder is watched: a banner and the Refresh button (F5) when it changes
                (AutoUpdate=1 rescans by itself)
              - 30 largest files (click copies the path)
              - copy the folder table to the clipboard (TSV, for Excel)

USAGE
  Ctrl+Q (Quick View) on a folder - analysis starts automatically.
  F3 on any file - then press 4 / pick the plugin to inspect that file's drive.
  Keys: V graphic/text view, S scan folder, A scan whole drive, U find duplicates, Z save snapshot,
        H HTML report, Shift+H Markdown report, D size on disk, X stop,
        O sort by size/name/type/date, M file filter, Delete to the Recycle Bin, Backspace = up, right click = context menu (all actions, keys shown),
        Ctrl+E copy table, Ctrl+C copy tab, T theme, L language, F5 refresh,
        Left/Right/Tab switch tabs.

INSTALL
  Open this zip in Total Commander (Enter) and confirm - TC installs it.
  Or: Configuration > Options > Plugins > Lister plugins (WLX) > Add, pick
  DiskInfo.wlx64.
  To make it open on folders in Quick View, set its detect string to
      EXT=""
  and keep it above other plugins that also use EXT="" (e.g. VisualDirSize).
  The plugin refuses plain files unless you force it (F3, then key 4), so
  other plugins still get them.

TEXT VIEW
  Press V (or set View=text in DiskInfo.ini): the same tabs as monospace
  console-style text with block progress bars; click a folder row to drill down.

LANGUAGE
  By default follows the Windows UI language (other -> English). To fix it,
  copy DiskInfo.ini.example to DiskInfo.ini next to the plugin and set
  Language=auto|uk|ru|en. In the viewer the L key cycles languages.

SETTINGS
  DiskInfo.ini (next to the plugin; see DiskInfo.ini.example): Language=auto|uk|ru|en,
  View=graphic|text, Theme=auto|dark|light, SizeOnDisk=0|1, Exclude=name1;name2,
  Sort=size|name|type|date, Filter=*.jpg;*.png, FilterExclude=0|1, AutoUpdate=0|1,
  Hints=1|0.
  The keys L, V, T, D, I, the sort menu and the view switch save the choice there; the
  file is read on every open.

CHANGES
  1.4.9
  [+] Version information in the DLLs (Properties > Details), for plugin managers.
  [+] Smooth (anti-aliased) shapes: donut chart, rounded bars, buttons, tiles, the (i) icon (GDI+).

  1.4.8
  [+] The status bar is on every tab; the graphic / text switch moved there from the tab bar.
  [+] Hints can be folded: the (i) icon at the top right or key I; Hints= in the ini.
  [~] The Up button sits next to the map and is greyed at the top level instead of disappearing.
  [~] List heading "Folder contents: sort by size" with a triangle that opens the sort menu.
  [-] Fixed: a click on the status bar went through to the list row scrolled under it.

  1.4.7
  [+] Text view: the folder list uses the same aligned columns as the tables below it (percent, size, files or
      date); the name column follows the window width in all tables.

  1.4.6
  [+] The scrollbar is drawn by the plugin: a thin rounded thumb in the theme colours (drag it, click the empty
      part to page; wheel and keys as before).
  [+] The right-click menu and the filter dialog use the theme colours too; the system frame around the menu is repainted.
  [-] The "Settings: <path>" item is removed from the right-click menu.

  1.4.5
  [+] Theme=auto (new default): the plugin follows Total Commander and takes the colours of its colour scheme
      (background, text, second background; [Colors] or [ColorsDark], also redirected to View\colors*.ini).
      Without a scheme colour it is dark or light by DarkMode= of wincmd.ini. Theme=dark and Theme=light
      work as before; key T sets one of them.

  1.4.4
  [+] Folders in the list are shown in brackets like in Total Commander: [folder]; files without.
  [~] On the [..] row of the panel the analysis shows the open folder, not its parent.
  [~] Any folder in the list can be opened (also those without sub-folders: their files are shown).

  1.4.3
  [+] The right-click menu ends with "Settings: <path>\DiskInfo.ini" - the ini file that is really used
      (the one next to the plugin DLL); a click shows it in Explorer.

  1.4.2
  [~] The status bar is flat like Total Commander's: scan statistics (files, folders, size) on the
      left, sorting on the right; the filter is shown there only while it is active.
  [+] Sorting by type and by date (key O or a click in the status bar): size, name, type, date.
  [-] The "files / folders only" switch (key F, ShowFiles=) is gone: files are always listed.
      Average file, depth and scan time are no longer shown in the statistics.

  1.4.1
  [~] Keys: N and P are taken by Total Commander's Lister (next/previous file), so the folder-list
      sorting is now O and the snapshot is Z.
  [~] Analysis tab: one row of buttons; Filter, "files and folders" and sorting moved to a status bar
      at the bottom; reports, snapshot and "copy table" are in the right-click menu.
  [~] The checkbox of the dark filter dialog is drawn in the dark theme (its text was dark grey).
  [~] The "Up" button is shown only when there is a level above the open folder.

  1.4
  [+] Replaces DirSizeCalc Charts and VisualDirSize (the DirSizeCalc column plugin, WDX, is a
      different thing and stays).
  [+] The folder list shows the files of the open folder too, not only sub-folders; sorting by
      size or by name (key O); empty folders are marked.
  [+] Delete moves the row under the mouse (folder or file) to the Recycle Bin, then rescans.
  [+] File mask filter (key M / Filter button, Filter= in the ini): only matching files are counted,
      or everything except them (FilterExclude=1). Masks use * and ?, no regular expressions.
  [+] The scanned folder is watched: a banner and a Refresh button (F5) when it changes;
      AutoUpdate=1 rescans by itself. The open sub-folder stays open after a rescan.
  [+] Markdown report (Shift+H / "MD report" button) and TXT report (button) next to the HTML one.
  [+] Right click opens a context menu with all actions and their keys (it used to go up; Backspace still does).
  [~] The context menu and the filter dialog follow the dark theme.
  [~] Buttons wrap onto a second row in a narrow window.
  1.3
  [+] Duplicates tab (key U): files of equal size, then equal first 64 KB, then equal 64-bit
      hash of the whole file; groups sorted by wasted space, "Copy list" gives a TSV for Excel;
      Shift+click on a path shows the file in Explorer. DupMinKB=1024 in the ini is the smallest
      file looked at. Files are not compared byte by byte; symlinks and cloud-only files are skipped.
  [+] Snapshots: key Z / "Save snapshot" stores folder sizes (DiskInfo-snapshots next to the plugin);
      the next scan of that folder shows what grew, shrank, appeared or vanished.
  [+] HTML report: key H / "HTML report" (DiskInfo-reports next to the plugin), opens in the browser.
  [+] Device tab: drive health - temperature (any drive) and the NVMe health log (wear, power-on
      hours, data written/read, unsafe shutdowns, media errors).
  [+] Key D: sizes as "size on disk" (rounded up to the cluster), rescans; SizeOnDisk=1 in the ini.
  [+] Exclude=.git;node_modules in the ini: those folder names are skipped by the scan.
  [+] Shift+click on a path in "Largest files" shows the file in Explorer.
  [~] Dark scrollbar in the dark theme.
  1.2
  [+] Volume tab: the drive name assigned in Total Commander ([DriveHints] in wincmd.ini)
      is shown in the header and in the "Label" row ("SYSTEM (assigned in TC)", with the
      system label too when it differs).
  [+] Network drives: the name of the shared folder (as in "net use") is shown as the
      drive name on the Volume and All drives tabs.
  [+] Hand cursor over everything that is clickable (tabs, Text/Graphics, Up, Copy table,
      drive cards, folder rows and tiles, largest files).
  [+] The row of the "Largest files" list under the mouse gets its path underlined.
  1.1.2
  [~] The Text/Graphics button saves the choice to DiskInfo.ini as well.
  1.1.1
  [+] Theme=dark|light in DiskInfo.ini.
  [~] Keys V, T and L save View, Theme and Language to DiskInfo.ini (before, they were
      only kept in memory); the ini is read on every open, so manual edits apply at once.
  1.1
  [+] Text (console-style) view, key V.
  1.0
  [+] First release.

NOTES
  - Only system DLLs are used (kernel32, user32, gdi32, mpr, msvcrt).
  - Sizes are logical file sizes (not size on disk). Symlinks and junctions
    are not followed.
  - Closed source; downloads and issues: https://github.com/sergiokapone/tc-diskinfo. Freeware.
