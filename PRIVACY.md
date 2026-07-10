# C0D3A1 — Tietosuojakäytäntö / Privacy Policy

**Copyright © 2026 BluexDEV Softwares. Kaikki oikeudet pidätetään. / All rights reserved.**

---

## Suomi

### Mitä dataa kerätään?

C0D3A1 kerää **anonymisoitua käyttödataa yhteisölliseen oppimiseen automaattisesti kaikilta käyttäjiltä — tämä on palvelun pakollinen ydinominaisuus, ei valinnainen ominaisuus.** Jakamista ei voi kytkeä pois Asetuksista. Katso perustelu [Käyttöehdoista](TERMS.md).

**Central Core -palvelin (Hetzner, EU) ei ole vielä avattu.** Anonymisoitu data kertyy toistaiseksi paikalliseen jonoon (`~/.c0d3a1/sync_queue/pending.jsonl`) laitteellasi ja lähetetään palvelimelle vasta kun se on käynnissä.

### Mitä anonymisointi tarkoittaa?

Ennen lähettämistä koodi käsitellään AST-tasolla (Abstract Syntax Tree):

| Poistetaan | Korvataan |
|-----------|-----------|
| Muuttujanimet | `var_1`, `var_2`, … |
| Funktionimet | `func_1`, `func_2`, … |
| Luokkanimet | `cls_1`, `cls_2`, … |
| Merkkijonoliteraalit | `"<str>"` |
| Kommentit | poistetaan kokonaan |

**Ei koskaan lähetetä:**
- Henkilötietoja (nimiä, sähköposteja, puhelinnumeroita)
- Salasanoja tai API-avaimia
- Tiedostopolkuja tai hakemistorakenteita
- IP-osoitteita tai laitteen tunnistetietoja
- Raakaa keskusteluhistoriaa, käyttäjäprofiilia tai muistin sisältöä sellaisenaan — vain abstrahoitu, anonymisoitu oppimismuoto (esim. `verified_correction`, `engram_pattern`)
- Selaushistoriaa tai sijaintitietoja

### Missä data säilytetään?

Anonymisoitu oppimisdata lähetetään (kun Central Core on käynnissä) Hetzner-palvelimelle (EU). Data käytetään yksinomaan yhteisömallin parantamiseen. Dataa ei myydä, luovuteta kolmansille osapuolille eikä käytetä mainontaan.

### Paikallinen data

Seuraava data tallennetaan **yksinomaan omalle laitteellesi** (`~/.c0d3a1/`) eikä lähetetä mihinkään sellaisenaan:

| Tiedosto/kansio | Sisältö |
|---|---|
| `db.sqlite` | Keskusteluhistoria |
| `user_profile.json` | Etunimi, paikkakunta (syötetty wizardissa) |
| `corrections.json` | Korjatut AI-vastaukset — oppimisdata (anonymisoitu versio jonottuu lähetykseen) |
| `training_data.jsonl` / `skills/` | Opittu oppimisdata |
| `knowledge/` | Vector-muisti (Qdrant) |
| `generated/` | AI:n luomat kuvat/videot/musiikki |
| `sync_queue/pending.jsonl` | Anonymisoitu data joka odottaa Central Corea |
| `config.yaml` | Asetukset ja mallit |

Vahvistetut korjaukset ja opitut taidot anonymisoidaan ja jonotetaan Central Corelle automaattisesti — ei koskaan raakana tai henkilötietoja sisältäen. Tämä on palvelun ydinominaisuus mallin parantamiseksi.

**Chattiin liitetyt tiedostot** (kuvat, PDF:t, koodi): käsitellään pyynnön ajan muistissa, tekstisisältö/kuvatavu liitetään keskusteluun, mutta raakaa tiedostoa ei tallenneta pysyvästi levylle.

### Käyttäjän oikeudet

- **Oikeus tietää** — voit tarkastella `~/.c0d3a1/sync_queue/`-jonoa ja `corrections.json`:ia suoraan tiedostojärjestelmästä
- **Oikeus tulla unohdetuksi** — lähetä pyyntö: [asiakaspalvelu@selaa.fi](mailto:asiakaspalvelu@selaa.fi)

### Yhteystiedot

BluexDEV Softwares
Tietosuoja-asiat: [asiakaspalvelu@selaa.fi](mailto:asiakaspalvelu@selaa.fi)
GitHub: [github.com/JuhaFIN1/c0d3a1](https://github.com/JuhaFIN1/c0d3a1)

---

## English

### What data is collected?

C0D3A1 collects **anonymized usage data for community learning automatically from every user — this is a mandatory core feature of the service, not an optional one.** Sharing cannot be disabled in Settings. See the rationale in the [Terms of Use](TERMS.md).

**The Central Core server (Hetzner, EU) has not been launched yet.** Anonymized data currently accumulates in a local queue on your device (`~/.c0d3a1/sync_queue/pending.jsonl`) and will only be transmitted once the server is running.

### What does anonymization mean?

Before transmission, code is processed at the AST level (Abstract Syntax Tree):

| Removed | Replaced with |
|---------|--------------|
| Variable names | `var_1`, `var_2`, … |
| Function names | `func_1`, `func_2`, … |
| Class names | `cls_1`, `cls_2`, … |
| String literals | `"<str>"` |
| Comments | removed entirely |

**Never transmitted:**
- Personal information (names, emails, phone numbers)
- Passwords or API keys
- File paths or directory structures
- IP addresses or device identifiers
- Raw chat history, user profile, or memory contents as-is — only the abstracted, anonymized learning form (e.g. `verified_correction`, `engram_pattern`)
- Browsing history or location data

### Where is data stored?

Anonymized learning data is sent (once Central Core is live) to a Hetzner server (EU). Data is used solely to improve the community model. Data is never sold, shared with third parties, or used for advertising.

### Local data

The following data is stored **exclusively on your own device** (`~/.c0d3a1/`) and is never transmitted as-is:

| File/folder | Content |
|---|---|
| `db.sqlite` | Chat history |
| `user_profile.json` | First name, city (entered in wizard) |
| `corrections.json` | Corrected AI responses — learning data (an anonymized copy is queued for transmission) |
| `training_data.jsonl` / `skills/` | Learned training data |
| `knowledge/` | Vector memory (Qdrant) |
| `generated/` | AI-generated images/video/music |
| `sync_queue/pending.jsonl` | Anonymized data waiting for Central Core |
| `config.yaml` | Settings and models |

Verified corrections and learned skills are automatically anonymized and queued for Central Core — never in raw form or containing personal data. This is a core feature of the service to improve the model.

**Files attached to chat** (images, PDFs, code): processed in memory for the duration of the request, text/image content is included in the conversation, but the raw file is never permanently saved to disk.

### User rights

- **Right to know** — you can inspect the `~/.c0d3a1/sync_queue/` queue and `corrections.json` directly on your filesystem
- **Right to be forgotten** — send a request to: [asiakaspalvelu@selaa.fi](mailto:asiakaspalvelu@selaa.fi)

### Contact

BluexDEV Softwares
Privacy matters: [asiakaspalvelu@selaa.fi](mailto:asiakaspalvelu@selaa.fi)
GitHub: [github.com/JuhaFIN1/c0d3a1](https://github.com/JuhaFIN1/c0d3a1)

---

*Viimeksi päivitetty / Last updated: 2026-07-10*
*BluexDEV Softwares*
