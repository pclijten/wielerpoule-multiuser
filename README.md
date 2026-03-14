+# Directeur Sportief 2026 (multi-user)
+
+Een simpele webapp voor een wielerpoule met meerdere gebruikers.
+De app draait volledig in de browser (één `index.html`) en gebruikt Firebase voor authenticatie en opslag.
+
+## Wat kun je ermee?
+
+- Inloggen met Google of e-mail/wachtwoord.
+- Eigen teams importeren via copy/paste.
+- Wedstrijdkalender bekijken.
+- Zien welke van je renners op een startlijst staan.
+- Puntenstand per team en totaalklassement bekijken.
+- Admin-functies voor beheer van kalender, resultaten en gebruikerscommunicatie.
+
+## Techniek
+
+- **Frontend:** HTML/CSS/vanilla JavaScript (module script in `index.html`)
+- **Backend services:** Firebase Authentication + Cloud Firestore
+- **Data-opzet (Firestore):**
+  - `users/{uid}`
+  - `users/{uid}/teams`
+  - `races`
+  - `results`
+
+## Snel starten (lokaal)
+
+Omdat de app Firebase modules via `https://www.gstatic.com/...` laadt, moet je hem via een lokale webserver openen (niet via `file://`).
+
+### Optie 1: Python
+
+```bash
+python3 -m http.server 8080
+```
+
+Open daarna: <http://localhost:8080>
+
+### Optie 2: Node (serve)
+
+```bash
+npx serve .
+```
+
+## Firebase configuratie
+
+De huidige Firebase-config staat hardcoded in `index.html` in `firebaseConfig`.
+
+Als je een eigen Firebase-project wilt gebruiken:
+
+1. Maak een Firebase-project aan.
+2. Activeer **Authentication** (Google en/of E-mail/Wachtwoord).
+3. Activeer **Cloud Firestore**.
+4. Vervang `firebaseConfig` in `index.html` met je eigen web-app configuratie.
+
+## Beheer en rollen
+
+- De app toont een **Admin-tab** voor admin-gebruikers.
+- Via de adminfuncties kun je o.a.:
+  - standaardkalender laden,
+  - wedstrijden toevoegen,
+  - startlijsten / eindklassement / etappes importeren,
+  - resultaten toevoegen/verwijderen,
+  - resetmails versturen.
+
+> Let op: auth-accounts aanmaken gebeurt in de Firebase Console, niet direct vanuit deze app.
+
+## Bekende aandachtspunten
+
+- Dit project bevat momenteel geen aparte buildstap of testsuite.
+- Het is een single-file app; voor grotere uitbreidingen is opsplitsen in meerdere bestanden aan te raden.
+
+## Bestandsoverzicht
+
+- `index.html` – volledige applicatie (UI + logica)
+- `README.md` – deze documentatie
 
EOF
)
