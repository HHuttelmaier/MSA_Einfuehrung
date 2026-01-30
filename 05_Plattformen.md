# Marketing-Automation Plattformen, Workflow-Automation und KI-Agenten-Frameworks

Neben **"klassischen" Marketing-Automation-Plattformen** wie bspw. Hubspot Marketing Hub, Salesforce Marketing Cloud, Adobe Marketo Engage, Microsoft Dynamics 365 Customer Insights oder Mautic rücken immer mehr auch **Workflow-Builder** (bspw. make, n8n) und **KI-Agenten-Frameworks** (bspw. Langflow, Flowise) in den Fokus, wenn es um Automation von Marketing- und Vertriebsprozessen geht. Unternehmen stehen vor der Frage, welches Tool sie für welchen Zweck einsetzen sollen.

## Spezialisierung, Zielgruppe und Architektur als Unterscheidungsmerkmale

Der Unterschied zwischen diesen Tool-Kategorien verläuft entlang **drei Dimensionen**:

**Dimension 1 – Spezialisierung:** Marketing Automation Plattformen sind domänenspezifisch. Sie bringen vorkonfigurierte Objektmodelle mit (Leads, Contacts, Campaigns, Deals) und implementieren Marketing-spezifische Best Practices. Workflow-Builder hingegen sind domänenagnostisch – sie automatisieren *irgendwelche* Prozesse, nicht nur Marketing.

**Dimension 2 – Zielgruppe und Kompetenzprofil:** Marketing Automation Plattformen sind für Marketer ohne Code-Kenntnisse gebaut. n8n richtet sich an technische User oder "Low-Code"-affine Personen. LangFlow setzt zumindest rudimentäre Entwicklerkompetenz voraus.

**Dimension 3 – Architekturparadigma:** Marketing-Plattformen sind vertikal integrierte Monolithen mit eigener Datenhaltung, CRM und Analytics. Workflow-Builder sind horizontale Integrations-Layer, die bestehende Tools verbinden. KI-Agenten-Frameworks sind Baukästen für intelligente Komponenten, die in andere Systeme eingebettet werden.

Die Wahl des richtigen Werkzeugs hängt damit weniger von technischer Raffinesse ab als von drei Fragen: *Wer* nutzt es, *wofür*, und *mit welcher bestehenden Infrastruktur*?

::: {.flip-card}
#### Marketing-Automation-Plattformen
Vertikal integrierte, domänenspezifische Plattform mit vorkonfigurierten Objektmodellen (Leads, Contacts, Campaigns), die vorgefertigte Tools für bspw. E-Mail-Marketing, Landing Pages, Lead Scoring und Customer Tracking bereitstellt. Zielgruppe: Marketer ohne Code-Kenntnisse.
:::

::: {.flip-card}
#### Workflow Automation
Domänenagnostischer, horizontaler Integrations-Layer. Verbindet bestehende Anwendungen über Trigger-Action-Logik, ohne eigene Datenhaltung. Zielgruppe: Technical Marketers, RevOps, Low-Code-affine User.
:::

::: {.flip-card}
#### KI-Agenten-Frameworks
Framework (visuelle Entwicklungsumgebung) zur Orchestrierung von LLMs, Prompts und Vektordatenbanken. Produziert intelligente Komponenten, die in andere Systeme eingebettet werden und komplexe Reasoning-Aufgaben übernehmen können. ZZielgruppe: Technical Marketers, RevOps, Low-Code-affine User mit rudimentären Code-Kompetenzen.
:::

## Die drei Kategorien im Detail

### Marketing-Automation-Plattformen

Hubspot Marketing Hub, Salesforce Marketing Cloud, Adobe Marketo Engage und Mautic sind **Software-Suiten**, die spezifische Geschäftsprobleme lösen. Sie bieten vorkonfigurierte Tools für E-Mail-Kampagnen, Landing Pages, Lead Scoring, Customer Tracking usw. Der Nutzer zahlt für die Convenience, diese Werkzeuge nicht selbst bauen zu müssen. Niemand möchte einen E-Mail-Server von Grund auf konfigurieren oder eine CRM-Datenbank selbst designen.

Der entscheidende Mehrwert liegt aber nicht in der Bequemlichkeit allein, sondern in der **eingebauten Domänenlogik**. HubSpot "weiß", was ein Lead ist, wie ein Sales Funnel funktioniert, und welche Metriken (Open Rate, Click-Through-Rate, Conversion) relevant sind. Diese Konzepte sind als Objekte und Dashboards vorkonfiguriert – der Marketer muss sie nicht selbst modellieren.

::: {.details}
#### Die monolithische Architektur klassischer Marketing-Automation Plattformen

Klassische Marketing-Automation-Plattformen sind monolithisch aufgebaut: CRM, E-Mail-Engine, Analytics, Landing-Page-Builder und Automation-Workflows sind in einer einzigen Codebasis integriert und teilen eine gemeinsame Datenbank. Das schafft Konsistenz (ein Kontakt ist überall derselbe Kontakt), erzeugt aber auch Rigidität. Die Plattform definiert, welche Objekte existieren und wie sie zusammenhängen. Wer ein Datenmodell braucht, das HubSpot nicht vorsieht, stößt an Grenzen.

Die architektonische Schwäche dieser Plattformen liegt entsprechend in ihrer Geschlossenheit. Daten verbleiben größtenteils *innerhalb* der Plattform. Wenn Salesforce bspw. keine native Integration zu einem Nischenwerkzeug bietet, das das Unternehmen nutzt, entsteht ein Datenbruch.

Zwar versuchen die großen Anbieter diese Lücke zunehmend zu schließen (Hubspot z.B. mit dem Operations Hub für programmierbare Automatisierung oder Breeze AI Features). Trotzdem bleibt auch programmierbare Logik innerhalb der Plattform ein Teil des "Walled Garden" – man optimiert das Silo, bricht es aber nicht auf.

:::

Die **Zielgruppe** dieser Plattformen sind Marketer, Vertriebsmitarbeiter und Business User ohne tiefgreifende technische Expertise. Das Setup erfolgt "out of the box" – Registrierung, Konfiguration, Start (OK, in der Realität ist es dann doch nicht ganz so einfach ;-).

### Workflow Automation Tools

Workflow-Automation-Tools wie n8n, Make oder Zapier sind "Schnittstellen"-Werkzeuge, deren Zweck vor allem darin besteht, verschiedene Anwendungen, Dienste und Datenbanken miteinander zu verknüpfen, um Geschäftsprozesse zu automatisieren.

Das Funktionsprinzip ist ereignisgesteuert: Ein **Trigger** (etwa ein neuer Eintrag in einem Google Sheet, eine neue E-Mail oder ein Webhook) löst eine **Action** aus (Daten auslesen, umwandeln, filtern, anreichern und in andere Systeme schreiben; etwa das Anlegen des Google-Sheet-Eintrags in HubSpot).

So lassen sich etwa Support-Anfragen automatisch kategorisieren, an ein Ticket-System senden und parallel eine Slack-Nachricht ans Team auslösen. Ebenso kannst du CRM-Daten aktualisieren, Rechnungen erstellen, Kalendertermine anlegen oder Dateien in Cloud-Speichern sortieren.

Die Tools übernehmen die Orchestrierung: Reihenfolge, Feldzuordnung (z. B. Name/E-Mail/Betrag) und Bedingungen wie „wenn Betrag > 1.000, dann…“. Häufig enthalten sie Fehlerbehandlung (Retries, Alerts), Logs zur Nachvollziehbarkeit und Zeitpläne für regelmäßige Läufe.

Der entscheidende Unterschied zu Workflows in "klassischen" Marketing-Automation-Plattformen: n8n & Co. automatisiert nicht nur *innerhalb* einer Plattform, sondern *quer durch das gesamte Internet*.

n8n wird oft wegen Kontrolle, Self-Hosting und Anpassbarkeit genutzt, Make wegen sehr visueller, schneller Konfiguration mit vielen App-Modulen. n8n zeichnet sich insbesondere durch seinen „Fair-Code“-Ansatz aus. Das bedeutet, der Quellcode ist einsehbar und die Software kann kostenlos auf eigenen Servern selbst gehostet werden, solange sie nicht kommerziell weiterverkauft wird. Alternativ steht eine kostenpflichtige Cloud-Version zur Verfügung.

Eine der größten Stärken von n8n ist die technische Flexibilität. Während einfache Aufgaben komplett visuell gelöst werden können, erlaubt n8n technisch versierten Nutzern, an jedem Punkt JavaScript einzufügen. Dadurch lassen sich komplexe Datenmanipulationen, logische Verzweigungen und benutzerdefinierte HTTP-Requests durchführen, die in anderen Tools oft nicht möglich oder sehr teuer sind.

::: {.details}
#### Case: Stripe-Mautic-Integration

Ein E-Commerce-Unternehmen nutzt Stripe für die Zahlungsabwicklung und Mautic für Marketing-Automation. Das Problem: Wenn ein Kunde bezahlt, muss diese Information manuell ins Marketing-Automation-System übertragen werden.

**Lösung mit n8n:** Ein Workflow hört auf das Stripe-Event "payment_succeeded", transformiert die Kundendaten mittels JavaScript-Node (Formatierung, Anreicherung) und pusht das Ergebnis via API in Mautic. Der Kontaktdatensatz wird automatisch aktualisiert, ein Tag vergeben, und der Kunde in die Post-Purchase-Sequenz eingesteuert. Zeitaufwand nach Setup: null.
:::

Die **Zielgruppe** für n8n sind Developer, RevOps-Spezialisten und Technical Marketers. Das Setup erfolgt auf einer "Blank Canvas" – der Nutzer baut den Prozess selbst.

### KI-Agenten-Frameworks

LangFlow besetzt eine dritte, noch jüngere Kategorie: die **visuelle IDE für LLMs** (Large Language Models). Während n8n Daten von A nach B *bewegt*, *transformiert* LangFlow Daten durch komplexes Reasoning und hält den Kontext (Memory) über lange Konversationen hinweg. Das Werkzeug ermöglicht es, Prompts, Vektordatenbanken (für semantische Suche in Dokumenten) und LLMs zu einer Prozesskette zu verbinden. Das Ergebnis ist kein simpler If-Then-Workflow, sondern ein System, das liest, versteht und intelligent antwortet.

Tatsächlich verschwimmen die Grenzen insb. zu n8n hier jedoch, da n8n in diesen Bereichen massiv aufholt. Durch neue, native LangChain-Integrationen in n8n lassen sich "einfache" KI-Aufgaben (z.B. einfache Chatbots, Fasse diese E-Mail zusammen oder Extrahiere Sentiment) heute problemlos direkt in n8n lösen.

Wozu also noch LangFlow oder Flowise? Sie bleiben das Werkzeug der Wahl für komplexe, autonome Agenten (zumal Langflow zu 100% auf Python Basis läuft). Wenn die KI nicht nur einen Schritt ausführen, sondern einen Plan entwickeln, Werkzeuge selbstständig wählen oder komplexe Python-Logik innerhalb der Chain ausführen muss ("Agentic Workflows"), bieten dedizierte AI-Builder eine Flexibilität und Debugging-Tiefe, die n8n als Generalist (noch) nicht erreicht.

Die **Zielgruppe** sind AI Engineers und technische Entwickler. Das Setup erfordert Verständnis für Prompt Engineering, Embedding-Modelle und API-Architektur.

## Der Tech-Stack: Schichten statt Alternativen

In einer technisch ausgereiften Umgebung werden diese drei Tool-Kategorien nicht als Alternativen begriffen, sondern als **Schichten eines Stacks**. Sie werden übereinandergelegt, nicht gegeneinander ausgetauscht.

::: {.details}
#### Case: Intelligente Lead-Qualifizierung

Ein B2B-Unternehmen erhält komplexe Anfragen über ein Webformular. Das Problem: Die manuelle Kategorisierung und Erstantwort kostet Zeit und führt zu inkonsistenter Bearbeitung.

#### Der integrierte Lösungsstack:

**Schicht 1 – Der Trigger (n8n):** n8n detektiert die neue Formulareinreichung via Webhook.

**Schicht 2 – Das Gehirn (LangFlow):** n8n sendet den Anfragetext an einen LangFlow-Agenten. Dieser analysiert das Sentiment, kategorisiert die Anfrage (Support vs. Sales vs. Partnership), und generiert einen personalisierten Antwortentwurf.

**Schicht 3 – Die Applikation (HubSpot):** n8n nimmt die KI-generierte Antwort und Kategorisierung, erstellt einen Deal in HubSpot, ordnet ihn dem richtigen Pipeline-Stage zu, und weist einem Vertriebsmitarbeiter eine Aufgabe zu.

Das Ergebnis: Vom Formulareingang bis zur qualifizierten Vertriebsaufgabe vergehen Sekunden statt Stunden.
:::

Diese Architektur lässt sich metaphorisch fassen: HubSpot ist das **Büro**, in dem die Kundenarbeit stattfindet. n8n ist die **digitale Infrastruktur** im Büro (das Verbindungsglied), der Daten zwischen Website, Billing-System und CRM transportiert. LangFlow ist der **KI-Mitarbeiter**, der liest, schlussfolgert und intelligente Texte produziert.

## Entscheidungslogik für die Tool-Auswahl

Die Wahl des richtigen Werkzeugs folgt einer einfachen Heuristik, die sich an den Ressourcen und Anforderungen des Unternehmens orientiert.

Unternehmen mit standardisierten Marketingbedürfnissen und begrenzten technischen Ressourcen sollten bei *Marketing Automation Plattformen* bleiben. Wer Daten über *fünf oder mehr Applikationen* verteilt hat und manuelle CSV-Exporte leid ist, ergänzt den Stack um *n8n*. Wer *intelligente, komplexe, autonome Agenten* benötigt, die über eine simple Wenn-Dann-Logik und über die Standard-KI-Funktionen non n8n hinausgehen, integriert spezialisierte Frameworks wie LangFlow oder Flowise.

Die Entscheidung ist dabei nicht binär. Ein Unternehmen kann mit Mautic, Hubspot & Co. starten, n8n hinzufügen, sobald Integrationsschmerzen auftreten, und LangFlow ergänzen, wenn KI-gestützte Automatisierung strategisch wird. Der Stack wächst mit den Anforderungen.