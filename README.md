# Vox4D — release

Questo repository contiene **solo i binari**: gli APK firmati, il manifest degli
aggiornamenti e le note di versione. Il codice dell'app sta in un repository
privato.

Vox4D trasforma il telefono in uno scanner 3D: scatta foto sovrapposte e
geolocalizzate girando intorno a un oggetto o lungo un'area, e le manda al tuo
server [NodeODM](https://github.com/OpenDroneMap/NodeODM) (OpenDroneMap), che
restituisce un modello 3D con texture e una nuvola di punti. Gratis, senza
account, senza pubblicita'.

- **Sito, in 13 lingue:** [vox4d.bais.info](https://vox4d.bais.info) (il
  pulsante di download porta sempre all'ultima release pubblicata)
- **Link diretto stabile:**
  [`vox4d-arm64.apk`](https://github.com/bdbais/vox4d-releases/releases/latest/download/vox4d-arm64.apk)
- **Novita':** [CHANGELOG.md](CHANGELOG.md)
- **Sostieni il progetto:** [paypal.me/bellizia](https://paypal.me/bellizia)

## Aggiornamenti automatici

L'app legge [`latest.json`](latest.json) da questo repository all'avvio e, se
c'e' una versione piu' nuova, propone di scaricarla. Per restare aggiornato non
serve altro: installa una volta l'APK dal sito o da qui, poi fa tutto l'app.

Chi preferisce seguire le versioni da GitHub puo' usare **Watch → Custom →
Releases** su questo repository, oppure un client come
[Obtainium](https://github.com/ImranR98/Obtainium) puntato all'indirizzo del
repository.

## Come verificare quello che installi

Ogni release pubblica due copie dello stesso APK — una col numero di versione,
una a nome fisso — e un `latest.json` con lo `sha256` del file. Fuori dal Play
Store quel numero e' l'unica garanzia che il file installato sia quello
compilato dalla build automatica:

```bash
sha256sum vox4d-arm64.apk
curl -s https://raw.githubusercontent.com/bdbais/vox4d-releases/main/latest.json
```

I due valori devono combaciare. L'app fa la stessa verifica da sola prima di
installare un aggiornamento, e rifiuta il file se non corrisponde.

Tutte le release sono firmate con la stessa chiave: se Android si lamenta della
firma durante un aggiornamento, il file non viene da qui.

## `latest.json`

E' il file che l'app interroga. Vive sul ramo `main` — non fra gli asset —
perche' `raw.githubusercontent.com` non ha limiti di chiamate. Finche' non esce
la prima versione non c'e', e l'app lo tratta come "nessun aggiornamento".

```json
{
  "versionName": "0.1.0",
  "versionCode": 1,
  "releaseDate": "2026-09-27",
  "mandatory": false,
  "notes": "una riga di novita'",
  "android": {
    "url": "https://github.com/bdbais/vox4d-releases/releases/download/v0.1.0/vox4d-arm64.apk",
    "sha256": "...",
    "sizeBytes": 0
  }
}
```

## Requisiti

Android 7 o successivo, 64 bit (arm64-v8a), con fotocamera e GPS. Per i
telefoni a 32 bit ogni release pubblica anche un APK `arm32`. La ricostruzione
3D gira sul tuo server NodeODM:
`docker run -d -p 3000:3000 opendronemap/nodeodm`.

---

Vox4D e' un progetto indipendente ispirato ad app di fotogrammetria come
PIX4Dcatch. Non e' affiliato a Pix4D; PIX4Dcatch e Pix4D sono marchi dei
rispettivi proprietari.
