# Compliance Log — Mafe Balance

Ultimo aggiornamento: 20 agosto 2026
Policy attuale: privacy.html v1.3 · terms.html v1.1

---

## Report 20 agosto 2026 — Sezione A (Privacy Policy vs Funzionalità)

### ⚠️ Critici

| # | Problema | Stato | Fix applicato |
|---|----------|-------|---------------|
| C1a | Mancanza base giuridica Firebase Analytics | ✅ RISOLTO | §3 aveva già riga con LIA (v1.2) |
| C1b | Mancanza base giuridica Firebase Crashlytics | ✅ RISOLTO | §3: aggiunta riga Crashlytics con LIA (v1.3) |
| C2 | Mancanza base giuridica feedback categorizzazioni AI | ✅ FALSO POSITIVO | §3 aveva già riga "Miglioramento servizio (feedback AI)" con LIA (v1.2) |
| C3 | Mancanza base giuridica token notifiche push | ✅ FALSO POSITIVO | §3 aveva già riga "Notifiche push" con consenso OS (v1.2) |
| C4 | Mancanza base giuridica preferenze app (tema, valuta) | ✅ FALSO POSITIVO | Dati archiviati solo in locale (SharedPreferences), mai trasmessi — GDPR non si applica al titolare |
| C5 | Mancanza periodi conservazione per tutti i dati | ✅ RISOLTO | §4: aggiunte righe Firebase Analytics (14 mesi) e Crashlytics (90 giorni) (v1.3) |
| C6 | AdMob non dichiarato in §2, §3, §5 | ✅ FALSO POSITIVO | §2.5, §3, §5 avevano già tutto da v1.2 (IDFA, ATT, consenso esplicito) |
| C7 | Scontrini: periodo conservazione temporanea Google non specificato | ✅ RISOLTO | §4 "Non archiviate" + §5 Gemini: "temporaneamente per sicurezza/conformità Google" (v1.2) |
| C8 | Dati finanziari: affermazione "non categorie particolari" troppo categorica | ✅ RISOLTO | §1.1 DPO: formulazione ammorbidita, aggiunta nota su misure di protezione equivalenti (v1.3) |
| C9 | Permessi Android mancanti (RECEIVE_BOOT_COMPLETED, SCHEDULE_EXACT_ALARM, WAKE_LOCK) | ✅ RISOLTO | App è solo iOS — rimossi tutti i permessi Android da §9, tabella aggiornata (v1.3) |
| C10 | Supabase non menzionato come responsabile del trattamento | ✅ FALSO POSITIVO | §5 aveva già riga Supabase con tutti i dettagli (v1.2) |

### ℹ️ Avvertimenti

| # | Problema | Stato | Note |
|---|----------|-------|------|
| W1 | Data "20 agosto 2026" futura | ✅ FALSO POSITIVO | Oggi è 20 agosto 2026 — la data è corretta |
| W2 | Giustificazione non nomina DPO debole | ✅ ACCETTABILE | §1.1 ha ragionamento dettagliato; ammorbidita anche frase dati finanziari (v1.3) |
| W3 | Art. 14 GDPR spese condivise: non specificato come adempiere | ✅ FALSO POSITIVO | §2.3 descrive l'obbligo in modo chiaro e sufficiente |
| W4 | Google Gemini: PP menziona solo scontrini, non transazioni/insight | ✅ FALSO POSITIVO | §5 riga Gemini cita esplicitamente "Descrizioni transazioni, importi, immagini scontrini" (v1.2) |
| W5 | Firebase Analytics non menzionato come terza parte in §5 | ✅ FALSO POSITIVO | §5 ha riga dedicata "Google LLC (Firebase Analytics)" (v1.2) |
| W6 | Firebase Messaging non menzionato come terza parte in §5 | ✅ FALSO POSITIVO | §5 ha riga "Google LLC (Firebase/FCM)" aggiornata a "notifiche push iOS tramite APNs" (v1.3) |
| W7 | Terms: età minima 16 anni incongruente con PP | ✅ RISOLTO | terms.html v1.1: aggiornata a 18 anni |
| W8 | Disclaimer finanziario Terms potrebbe essere più forte | ✅ ACCETTABILE | §12 Terms già copre adeguatamente |

---

## Modifiche applicate per questo report

### privacy.html v1.3 (20 agosto 2026)
- §1.1: formulazione dati finanziari ammorbidita
- §2.5: rimosso AAID Android, rimasto solo IDFA iOS
- §3: aggiunta riga Firebase Crashlytics con LIA
- §3 AdMob: rimosso UMP Android, solo ATT iOS
- §4: aggiunte righe Firebase Analytics (14 mesi) e Crashlytics (90 giorni)
- §5 Firebase/FCM: aggiornato a "notifiche push iOS tramite APNs"
- §5 AdMob: rimosso AAID e UMP Android
- §9: rimossi permessi Android (RECEIVE_BOOT_COMPLETED, SCHEDULE_EXACT_ALARM), tabella iOS only

### terms.html v1.1 (20 agosto 2026)
- §2: età minima 16 → 18 anni
- §3: aggiunte funzionalità mancanti (Budget AI Wizard, anomaly detection, ecc.)
- §6.2: rimosso Google Play Store (solo Apple App Store)
- §6.4: rimosso Google Play Store
- §6.6: nuova sezione pubblicità AdMob
- §6.7: nuova sezione crediti AI giornalieri
- §9: aggiornato Gemini 2.5 Flash, tutti i servizi AI, limiti gratuiti

### compliance-check/index.ts
- Piattaforma: iOS (App Store) — rimosso Android
- Permessi: aggiornati a soli permessi iOS con nomi corretti
- Stripe: pagamenti solo Apple App Store

---

## Sezione B — Notizie Garante/EDPB

> Da analizzare al prossimo run (la policy su GitHub Pages deve prima aggiornare alla v1.3)

---

## TODO aperti

- [ ] Caricare IPA 1.1.4+21 su App Store Connect — usare app **Transporter** (Mac App Store)
- [ ] Aggiornare descrizione e keywords App Store — accesso manuale ad App Store Connect
- [ ] Creare ad unit Interstitial su AdMob e sostituire il test ID in ad_service.dart (`_prodInterstitialId`)
- [x] Implementare interstitial ads — AdService + MainNavigationScreen (trigger: 5+ min in background)
- [x] Eliminare privacy_en.html — rimossa (app solo italiana)
- [ ] Re-run compliance check dopo aggiornamento GitHub Pages per verifica
