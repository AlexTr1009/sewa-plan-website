# SewaPlan Landing Page: Grobe Skizze (v2)

> Inhaltliche Grundlage: `docs/ROADMAP.md` (Verkaufskriterien, USP, Kernnutzen)
> Designsprache: Light, Outfit + Plus Jakarta Sans, Teal-Akzent hsl(173, 58%, 39%)
> Visuelles Konzept: Mehrere 3D-CSS-Mockups zeigen die Software in verschiedenen Situationen
> Technische Referenz: Workflow aus `app/agents/langgraph_orchestrator.py`, Planstruktur aus `app/models/care_plan.py`

---

## Seitenstruktur (Top → Bottom)

---

### 1. HEADER (sticky)

```
[S] SewaPlan          Produkt   Ablauf   Kontakt          [SewaPlan testen]
```

Kompakt, wie bisher. Keine Änderung nötig.

---

### 2. HERO

**Eyebrow:** KI-Fachassistenz für ambulante Pflege

**Headline:**
Pflegepläne erstellen. Fachlich prüfen. Fundiert aktualisieren.

**Subline:**
SewaPlan unterstützt Pflegeteams bei der Erstellung und Aktualisierung von Pflegeplänen auf Basis von AEDL, Assessments und aktuellen Expertenstandards.

**CTAs:** Kostenlos ausprobieren | Wie es funktioniert

**Stichpunkte:**
- Für ambulante Pflegedienste
- Aus Beobachtungen und Assessments werden vollständige Pflegepläne
- Fachliche Entscheidung bleibt beim Team

**🖼 BILD 1: 3D-Mockup "Eingabe & Analyse"**
Zeigt: Sidebar mit Patienten, Chat mit Nutzereingabe ("Patient benutzt nun innerhalb der Wohnung einen Rollator"), KI-Antwort mit erkannten AEDL-Bereichen, ähnlichen Fällen, Expertenstandards. Status-Spinner "Prüfe Vollständigkeit".
→ Bereits implementiert, bleibt wie es ist.

---

### 3. NUTZEN (Warum SewaPlan)

**Eyebrow:** Warum SewaPlan

**Headline:** Pflegepläne, die fachlich standhalten und im Alltag funktionieren.

**4 Karten (2×2 Grid):**

| Karte | Titel | Inhalt (gekürzt) |
|-------|-------|-------------------|
| 1 | Immer auf dem neusten fachlichen Stand | Live-Recherche von Expertenstandards, proaktiver Hinweis bei veralteten Maßnahmen, nicht erst bei der MD-Prüfung |
| 2 | Vollständige Pläne statt Lücken | SewaPlan erzeugt Pläne mit allen notwendigen Angaben: Probleme mit Ursachen und Symptomen, Ressourcen, Ziele mit Zeitrahmen und Maßnahmen mit konkreten Schritten, Häufigkeit und Zuständigkeit |
| 3 | Automatische Qualitätsprüfung | Jeder Plan wird auf Vollständigkeit, Konsistenz und fachliche Korrektheit geprüft, fehlende AEDL-Bereiche, inkonsistente Maßnahmen und Abweichungen von Expertenstandards werden erkannt |
| 4 | Entlastung für die PDL | Fachlich fundierte Entwürfe auf Knopfdruck, PDL prüft und gibt frei |

Kein Bild nötig. Icons reichen.

---

### 4. SO FUNKTIONIERT ES (Ablauf / Workflow)

**Eyebrow:** In drei Schritten

**Headline:** Von der Beobachtung zum fertigen Pflegeplan.

**3 Schritte vertikal oder horizontal:**

| Schritt | Titel | Text |
|---------|-------|------|
| 01 | Situation beschreiben | Beschreiben Sie, was Sie beobachtet haben und wie die aktuelle Situation des Patienten aussieht. In eigenen Worten, ohne Fachformular. SewaPlan erkennt die relevanten AEDL-Bereiche automatisch. |
| 02 | Vorschläge prüfen und anpassen | SewaPlan generiert vollständige Planeinträge mit Problemen, Ressourcen, Zielen und Maßnahmen. Jeder Vorschlag kann einzeln akzeptiert, angepasst oder abgelehnt werden. |
| 03 | Freigeben und speichern | Wenn Sie mit den Vorschlägen zufrieden sind, übernehmen Sie die Einträge in den Pflegeplan. Bei manuellen Änderungen prüft SewaPlan zusätzlich auf Vollständigkeit und Konsistenz, bevor gespeichert wird. |

**🖼 BILD 2: 3D-Mockup "Generierter Plan mit Vorschlägen"**
Zeigt: Die gleiche App-Oberfläche. Im Hauptbereich eine Plantabelle mit AEDL-Einträgen in Kartenform. Jede Karte zeigt die vier Bereiche: Probleme (mit Ursachen/Symptomen), Ressourcen, Ziele (mit Zeitrahmen), Maßnahmen (mit Frequenz und Rolle). Inline-Vorschläge sichtbar: grüne Markierung für neue Einträge, Accept/Reject-Buttons. Sidebar zeigt den Patienten als aktiv.
→ Neuer 3D-Mockup. Gleiche Perspektive wie Hero, aber anderer Inhalt im Main-Bereich.

---

### 5. AUTOMATISCHE PLANPRÜFUNG (Verkaufskriterium: veraltete Maßnahmen erkennen)

**Eyebrow:** Automatische Planprüfung

**Headline:** SewaPlan erkennt, wenn ein Plan nicht mehr aktuell ist.

**Text:**
Bestehende Pflegepläne werden gegen aktuelle Expertenstandards, dokumentierte Assessments und interne Konsistenzregeln geprüft. SewaPlan findet veraltete Maßnahmen, abgelaufene Zieldaten, fehlende Evaluierungen, doppelte Einträge, Sicherheitslücken und inkonsistente Angaben. Konkrete Änderungsvorschläge erscheinen direkt im Plan mit Begründung. Das Team entscheidet per Klick, was übernommen wird.

**🖼 BILD 3: 3D-Mockup "Planprüfung mit Inline-Vorschlägen"**
Zeigt: App-Oberfläche mit einem bestehenden Pflegeplan. Im Plan sind Inline-Vorschläge sichtbar:
- Ein `diff`-Vorschlag: alte Maßnahme durchgestrichen, neue daneben in Grün, mit Begründung ("Empfehlung gemäß Expertenstandard Sturzprophylaxe 2024 aktualisiert")
- Ein `add`-Vorschlag: neuer Eintrag grün hervorgehoben mit Accept/Reject-Buttons
- Ein `hint`-Vorschlag: blaue Info-Box mit Hinweis
- Button "Plan überprüfen" ist aktiv markiert in der Header-Leiste
→ Neuer 3D-Mockup. Zeigt die proaktive Planprüfung mit Inline-Änderungsvorschlägen.

---

### 6. AUSFÜHRLICHE PFLEGEPLÄNE (Verkaufskriterium: lesbare Pläne für LK1/LK2)

**Eyebrow:** Für den Einsatz gemacht

**Headline:** Pflegepläne mit allen Angaben, die im Alltag gebraucht werden.

**Text (links):**
In vielen Pflegediensten sind Pflegepläne aus Zeitdruck zu knapp geschrieben. Wichtige Angaben fehlen: Welche konkreten Schritte müssen durchgeführt werden? Wie oft? Durch wen? Das führt dazu, dass Pflegefachassistenten und Fachkräfte mit LK1 und LK2 im Einsatz improvisieren müssen.

SewaPlan erzeugt vollständige Einträge mit allen relevanten Feldern. Jede Maßnahme enthält eine Beschreibung, die Häufigkeit, die zuständige Rolle und alle Durchführungsschritte im Detail.

**🖼 BILD 4: Vergleichs-Darstellung "Vorher / Nachher"**

Links ein typischer Praxis-Plan (unvollständig):
```
AEDL 02: Sich bewegen

Problem: Sturzgefahr, Pat. unsicher auf den Beinen
Ressource: –
Ziel: Mobilität erhalten
Maßnahme: Rollator bereitstellen, auf Sturzrisiko achten
```

Rechts der SewaPlan-Plan (vollständig und strukturiert):
```
AEDL 02: Sich bewegen

Problem:
  Beschreibung: Erhöhte Sturzgefahr durch eingeschränkte
  Mobilität innerhalb der Wohnung seit Nutzung eines
  Rollators.
  Ursachen: Gangunsicherheit, eingeschränkte Kraft in
  den unteren Extremitäten
  Symptome: Unsicheres Gangbild, Festhalten an Möbeln,
  verlangsamte Bewegungsabläufe

Ressourcen:
  - Patient ist motiviert, sich selbstständig zu bewegen
  - Rollator vorhanden und funktionstüchtig
  - Angehörige unterstützen bei Arztbesuchen

Ziel:
  Beschreibung: Patient bewegt sich sicher mit Rollator
  in allen Wohnräumen ohne Sturzereignis.
  Typ: Erhaltungsziel
  Evaluation: 31.12.2026
  Priorität: Hoch

Maßnahmen:
  1. Begleitung bei Transfers
     Frequenz: Bei jedem Einsatz
     Rolle: Pflegefachkraft
     Details:
     - Rollator vor dem Aufstehen in Reichweite stellen
     - Standsicherheit nach dem Aufstehen abwarten
     - Gehstrecke innerhalb der Wohnung begleiten
     - Auf Schwindel oder Unsicherheit achten

  2. Wohnumfeld-Check
     Frequenz: 1x monatlich
     Rolle: Pflegefachkraft
     Details:
     - Stolperfallen prüfen (Teppichkanten, Kabel,
       Türschwellen)
     - Beleuchtung in Flur und Bad kontrollieren
     - Haltegriffe auf festen Sitz prüfen

  3. Sturzprotokoll führen
     Frequenz: Bei jedem Sturzereignis
     Rolle: Alle Pflegekräfte
     Details:
     - Zeitpunkt, Ort und Umstände dokumentieren
     - Verletzungen erfassen
     - Hausarzt informieren bei Verletzung
     - Maßnahmenplan ggf. anpassen
```

→ Kein 3D-Mockup, sondern zwei nebeneinander gestellte Karten. Links blass/grau mit rotem Akzent ("unvollständig"), rechts in Akzentfarbe ("vollständig"). Einfaches, eindrückliches Design.

---

### 7. VERTRAUEN & SICHERHEIT

**Eyebrow:** Vertrauen und Datenschutz

**Headline:** Die fachliche Entscheidung bleibt immer beim Team.

**4 Punkte (Icon + Kurztext) als horizontale Leiste oder kleine Karten:**

| Icon | Titel | Text |
|------|-------|------|
| Schild | KI-Vorschlag, kein Automatismus | Jeder Vorschlag wird vom Pflegeteam geprüft und freigegeben. SewaPlan entscheidet nicht autonom. |
| Stift | Jederzeit manuell anpassbar | Das Team kann jeden Eintrag im Plan jederzeit selbst bearbeiten, ergänzen oder entfernen. |
| Schloss | Daten bleiben lokal | Patientendaten werden lokal verarbeitet. Keine externen Cloud-Dienste für sensible Daten. |
| Auge | Nachvollziehbare Quellen | Jeder Expertenstandard-Verweis zeigt die Quelle. Änderungsvorschläge zeigen, was sich warum ändert. |

Kein Bild nötig. Icons + Text reichen.

---

### 8. CTA / KONTAKT

**Headline:** Bereit für vollständige Pflegeplanung?

**Subline:**
Testen Sie SewaPlan kostenlos in Ihrem Pflegedienst. Kein Vertrag, kein Risiko.

**CTA-Button:** Jetzt kostenlos starten

**Alternativ:** Kontaktformular (Name, Einrichtung, E-Mail, Nachricht) oder einfache Mailto-Verlinkung für den MVP.

Kein Bild nötig. Großer CTA auf sanftem Hintergrund.

---

### 9. FOOTER

```
SewaPlan                               Produkt · Ablauf · Kontakt
KI-Fachassistenz für                   Impressum · Datenschutz
ambulante Pflegeplanung
                                       © 2026 SewaPlan
```

Kein Bild nötig.

---

## Bildplan: Übersicht der 4 Visuals

| # | Sektion | Typ | Was es zeigt | Warum |
|---|---------|-----|-------------|-------|
| 1 | Hero | 3D-CSS-Mockup | Eingabe einer Beobachtung, KI analysiert AEDL-Bereiche, findet ähnliche Fälle und Standards | Erster Eindruck: "So sieht die Software aus" |
| 2 | Ablauf (Schritt 2) | 3D-CSS-Mockup | Generierte Planeinträge mit Accept/Reject pro Eintrag | Zeigt das Ergebnis: "Das kommt raus" |
| 3 | Automatische Planprüfung | 3D-CSS-Mockup | Bestehender Plan mit Inline-Vorschlägen (diff/add/hint) und Begründungen | Verkaufskriterium: "Die Software denkt mit und zeigt warum" |
| 4 | Ausführliche Pläne | Vorher/Nachher-Karten | Knapper Praxis-Plan vs. vollständiger SewaPlan-Plan mit allen Feldern | Verkaufskriterium: "Pläne mit allen Angaben für den Einsatz" |

### Beschreibung der 3D-Mockups

Alle 3D-Mockups verwenden das gleiche Grundgerüst (Sidebar + Main-Bereich + Footer-Input), nur der Inhalt im Hauptbereich wechselt. Die Perspektive wird leicht variiert (Drehwinkel), damit die Seite nicht monoton wirkt.

**Mockup 1 (Hero):** Perspektive leicht nach links gedreht. Chat-Verlauf mit Eingabe und KI-Antwort-Karten. Status-Spinner aktiv. Helle, einladende Stimmung.

**Mockup 2 (Ablauf):** Perspektive leicht nach rechts gedreht (gespiegelt). Statt Chat: generierte Planeinträge als Karten mit den vier Bereichen (Probleme, Ressourcen, Ziele, Maßnahmen). Neue Vorschläge grün hervorgehoben mit Accept/Reject-Buttons.

**Mockup 3 (Planprüfung):** Perspektive frontal mit leichtem Tilt. Zeigt bestehenden Plan mit Inline-Änderungsvorschlägen: diff-Einträge (alt durchgestrichen, neu in Grün), add-Einträge (grün hervorgehoben), hint-Einträge (blaue Info-Box). Button "Plan überprüfen" ist aktiv markiert. Zeigt, dass die Software eigenständig prüft und Begründungen liefert.

---

## Content-Herkunft (Mapping auf ROADMAP)

| Sektion | Quelle in ROADMAP.md |
|---------|---------------------|
| Hero | Positionierung (Ein-Satz), Kurz-USP |
| Nutzen | Verkaufskriterien 1–5 |
| Ablauf | Demo-Story (Phase 1.3), Workflow aus langgraph_orchestrator |
| Automatische Planprüfung | Verkaufskriterium 2, Differenzierungsmerkmal 5, plan_review_agent.py |
| Ausführliche Pläne | Verkaufskriterium 3, Planstruktur aus care_plan.py |
| Vertrauen | Leitgedanken 3 ("Vertrauen vor Features"), Phase 0.4 |
| CTA | Phase 1.1 (Pilotakquise), Pilotangebot |
