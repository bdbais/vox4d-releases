# Changelog

Vox4D e' gratis, senza pubblicita' e senza tracciamento. Se ti e' utile, puoi
sostenere il progetto: **[paypal.me/bellizia](https://paypal.me/bellizia)**.

Le versioni seguono `MAJOR.MINOR.PATCH`. Il `versionCode` di Android e' il
numero dopo il `+` in `app/pubspec.yaml` e cresce di uno a ogni rilascio: e' il
numero su cui l'app decide se c'e' un aggiornamento.

## 0.1.0 — prima versione

### Scatta

- Tre modi di scatto: **manuale**, **a tempo** (una foto ogni N secondi) e
  **a distanza** (una foto ogni N metri percorsi).
- Ogni foto salva latitudine, longitudine, quota e precisione del GPS; un
  indicatore verde, giallo o rosso dice quanto e' affidabile la posizione.
- Lo schermo resta acceso durante la scansione e ogni scatto vibra.

### Controlla

- Griglia delle foto, dettaglio con la posizione, eliminazione delle foto
  venute male.
- Mappa del percorso su OpenStreetMap, con la precisione di ogni punto.

### Elabora

- Le foto vanno al tuo server **NodeODM** (OpenDroneMap), con tre livelli di
  qualita' e la scelta fra scansione di oggetti e rilievo del terreno.
- L'app segue l'avanzamento anche se esci dalla schermata, poi scarica il
  modello 3D con texture, la nuvola di punti e i report.
- Esportazione in zip con `geo.txt` e un CSV delle posizioni per Pix4Dmatic,
  Metashape e RealityCapture.

### E poi

- Tredici lingue: italiano, inglese, spagnolo, francese, tedesco,
  portoghese, turco, russo, ucraino, arabo, cinese, giapponese e coreano.
- Aggiornamenti dall'app, con verifica SHA-256 del file.
- Schermata Informazioni con donazioni, ringraziamenti e i token spesi per
  svilupparla.
