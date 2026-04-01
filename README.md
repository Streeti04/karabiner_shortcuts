# Karabiner Shortcuts

Diese Sammlung enthaelt eigene Karabiner-Elements-Regeln fuer ein Windows/Linux-aehnliches Shortcut-Verhalten auf macOS.

## Inhalt

- shortcuts.json
  - bisherige Gesamtdatei mit allen Regeln
- categories/
  - aufgeteilte Regeln nach Funktion, damit Aenderungen einfacher sind

## Kategorien

- categories/01_browser_controls.json
  - Ctrl+Q/W/L in Browsern auf Cmd+Q/W/L
- categories/02_option_spotlight.json
  - Left Option: tippen = Spotlight, halten = Option
- categories/03_altgr_symbols.json
  - AltGr-Zeichen fuer deutsches Layout
- categories/04_a_f_ctrl_cmd_swap.json
  - Ctrl/Cmd-Tausch fuer A und F
- categories/05_terminal_shortcuts.json
  - Terminal-spezifische Regeln
- categories/06_system_shortcuts_except_terminal.json
  - systemweite Ctrl-Shortcuts (ausser Terminal)
- categories/07_navigation_and_delete.json
  - Wortnavigation und Loeschen (ausser Terminal)

## Bearbeiten

1. Passende Datei in categories/ oeffnen.
2. Regel anpassen oder neue Regel im selben Block ergaenzen.
3. JSON pruefen.

Beispiel:

```bash
for f in categories/*.json shortcuts.json; do
  ruby -rjson -e 'JSON.parse(File.read(ARGV[0]))' "$f" || exit 1
done
echo "JSON validation ok"
```

## Hinweise

- Die Dateien in categories/ sind fuer eine bessere Wartung gedacht.
- shortcuts.json bleibt als Referenz bzw. Gesamtstand erhalten.
- Beim Aendern immer auf gueltiges JSON achten (Kommas, Klammern, Quotes).
