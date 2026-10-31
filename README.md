# Slopperino — download e installazione per Windows

Slopperino sincronizza le note ZotLit di Zotero con Obsidian. È gratuito.

**[Scarica Slopperino 2.8.0 (GitHub Releases)](https://github.com/Gbfarioli/Slopperino-Downloads/releases/tag/v2.8.0)**

Questo repository contiene i file destinati al download; lo sviluppo avviene separatamente in un repository privato.

## Prima di installare

Verifica di avere:
- Windows 10 o 11;
- Zotero installato e configurato;
- Obsidian installato, con il vault che vuoi sincronizzare;
- ZotLit installato e configurato in Obsidian;
- la CLI di Obsidian abilitata dalle impostazioni dell'app.

Devi conoscere il **nome esatto del vault**, il percorso di **Obsidian.com** (non Obsidian.exe) e la cartella dati di Zotero (quella che contiene `zotero.sqlite`). Il percorso tipico è `C:\Users\<utente>\Zotero`, ma può differire.

## Installazione passo passo

1. Apri la [pagina della release 2.8.0](https://github.com/Gbfarioli/Slopperino-Downloads/releases/tag/v2.8.0).
2. Nella sezione **Assets** scarica `Slopperino_Setup_2.8.0.exe` e `SHA256-2.8.0.txt`. Non serve GitHub CLI.
3. Con PowerShell nella cartella dei download, verifica l'integrità:
   ```powershell
   Get-FileHash .\Slopperino_Setup_2.8.0.exe -Algorithm SHA256
   ```
   Il valore deve coincidere con quello nel file `SHA256-2.8.0.txt`.
4. Fai una scansione con il tuo antivirus. Il file **non è firmato digitalmente**, perciò Chrome o Windows potrebbero segnalarlo; **non disattivare né aggirare le protezioni**. Se un download è bloccato, segnala il problema al referente.
5. Chiudi Zotero e Obsidian, quindi esegui l'installer. Alla prima installazione inserisci il percorso di Obsidian.com, il nome del vault e la cartella dati Zotero quando richiesti.
6. Riapri Zotero e Obsidian, con il vault scelto. Dal menu Start, avvia **Slopperino - Aggiorna note**. Attendi il riepilogo e verifica che `failed=0` e `metadataFailed=0`.

## Uso quotidiano

Slopperino avvia in modo invisibile un Bridge locale su `127.0.0.1:9092` e monitora gli aggiornamenti di Zotero. Puoi richiedere una sincronizzazione manuale con **Slopperino - Aggiorna note**. Le voci **Slopperino - Configura** e **Slopperino - Log** permettono rispettivamente di modificare i percorsi e consultare i messaggi di funzionamento.

Il controllo della disponibilità di nuove versioni è manuale e **non scarica né installa software automaticamente**. La diagnostica inviata all'esterno è facoltativa e può essere gestita tramite **Slopperino - Segnalazioni diagnostiche**.

## Problemi frequenti

**«Apri Obsidian nel vault configurato»** — apri Obsidian e assicurati di essere nel vault selezionato durante l'installazione.

**«Obsidian.com non trovato»** — abilita la CLI dalle impostazioni di Obsidian, poi controlla il percorso con **Slopperino - Configura**.

**«zotero.sqlite non trovato»** — verifica di avere scelto la cartella dati corretta di Zotero e non una cartella di allegati o di esportazione.

**Errore di download o avviso di sicurezza** — non ignorare gli avvisi. Chiedi supporto al referente; un checksum non sostituisce una firma digitale.

**Altri errori** — apri **Slopperino - Log** e condividi soltanto le righe pertinenti, oscurando percorsi o informazioni personali. Evita di inserire pubblicamente contenuti di Zotero, note, credenziali e dati personali.

## Stato dei collaudi

La versione 2.8.0 è stata verificata mediante aggiornamento da una versione precedente e sincronizzazione di **195 note su 195**, senza errori di metadati. **L'installazione pulita su un PC indipendente non è ancora stata verificata**: la guida può essere migliorata sulla base di quel collaudo.

## Privacy e trasparenza

La diagnostica è facoltativa. Il Bridge opera localmente. L'installer è attualmente **unsigned**; lo SHA-256 verifica che il download coincida con l'artefatto pubblicato ma non autentica l'identità dell'editore. Il software è gratuito e non richiede abbonamenti o servizi a pagamento.
