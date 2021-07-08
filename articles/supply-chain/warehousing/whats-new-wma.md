---
title: Novità o modifiche nell'app per dispositivi mobili Warehouse Management
description: Questo argomento elenca le funzionalità nuove e modificate per ogni versione rilasciata dell'app per dispositivi mobili Warehouse Management per Microsoft Dynamics 365 Supply Chain Management.
author: ivanv-microsoft
ms.date: 06/07/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 61124728942c0b8162de9f687ae752773c47d07e
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261784"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a>Novità o modifiche nell'app per dispositivi mobili Warehouse Management

[!include [banner](../includes/banner.md)]

Questo argomento elenca le funzionalità nuove, le correzioni, i miglioramenti e i problemi noti per ogni versione rilasciata dell'app per dispositivi mobili Warehouse Management per Microsoft Dynamics 365 Supply Chain Management.

## <a name="version-2060"></a>Versione 2.0.6.0

### <a name="new-features-fixes-and-improvements-in-version-2060"></a>Nuove funzionalità, correzioni e miglioramenti nella versione 2.0.6.0

Questa versione introduce le seguenti nuove funzionalità, correzioni e miglioramenti:

- La modalità demo ora mostra tutte le etichette nella lingua del dispositivo.
- È meno probabile che venga visualizzato il seguente messaggio di errore: "Impossibile trovare una vista adatta per la dimensione specificata".
- L'altezza minima per le schede di lavoro è stata aumentata (nei casi in cui sono configurati al massimo tre campi per la visualizzazione nell'elenco di lavoro).
- I margini (dissolvenza) nella parte inferiore delle schede dei dettagli sono stati migliorati.
- I simboli non validi nei file XML scambiati con il server ora vengono gestiti correttamente. Ad esempio, i caratteri non stampabili ora vengono gestiti correttamente e non causano più il blocco dell'app.
- Gli errori HTTP (come "errore 503") quando viene inviata una richiesta al server ora vengono gestiti correttamente.
- Mentre viene visualizzato un errore, l'elenco delle opzioni non viene più visualizzato automaticamente per i controlli della casella combinata.
- L'app non smette più di rispondere a causa dell'orientamento dello schermo selezionato nelle impostazioni utente.
- Le immagini dei prodotti vengono ora mostrate negli ambienti self-service. Questa modifica si applica solo alle versioni a bassa risoluzione. Il servizio di gestione dei file non supporta le immagini a grandezza naturale negli ambienti self-service.
- È stato risolto un problema che riguardava il prelievo breve a quantità zero.
- L'app non si interrompe più quando una scheda dei dettagli mostra più campi identici.

### <a name="known-issues-in-version-2060"></a>Problemi noti nella versione 2.0.6.0

In questa versione sono presenti i seguenti problemi noti:

- L'app (in particolare l'elenco di lavoro) diventa più lenta nel tempo.
- **Versione Windows:** Quando si utilizza una pistola USB per la scansione su Windows, i risultati incoerenti causano la confusione dei simboli scansionati.

## <a name="version-2050"></a>Versione 2.0.5.0

Questa versione introduce le seguenti nuove funzionalità, correzioni e miglioramenti:

- Il segreto del client non è più nascosto nella configurazione delle impostazioni di connessione.
- Ora puoi premere a lungo su qualsiasi testo per vederlo completamente.
- Il messaggio di errore quando mancano le autorizzazioni di archiviazione è stato migliorato.
- Sono state aggiunte nuove sequenze di controllo per alcuni flussi.
- Il pulsante di invio non diventa più erroneamente disponibile a causa delle dimensioni della finestra.
- I dispositivi di scorrimento ora possono procedere su schermi più piccoli quando vengono utilizzati pulsanti di dimensioni maggiori.
- La sovrapposizione di quattro pulsanti non viene più tagliata.
- La tastiera ora supporta il pulsante di eliminazione.
- È stato risolto un problema di luminosità che poteva verificarsi quando si preme la tastiera.
- Sono stati risolti vari problemi relativi ai dati demo.
- È stato risolto un problema che riguardava i campi numerici nella pagina dei dettagli.
- La tastiera a schermo non scompare più occasionalmente su alcuni dispositivi.
- Sono stati corretti vari bug dell'interfaccia utente (UI), come i bug che interessavano il colore e il posizionamento dello sfondo.
- L'interfaccia utente in lingua russa è stata migliorata.
- Sono stati risolti vari problemi che causavano il blocco del sistema.
- È stato risolto un problema relativo alla riapertura della calcolatrice.
- **Versione Android:** Un problema che causava l'interruzione di Android 4.4 all'avvio è stato corretto.
- **Versione Android:** Il ridimensionamento minimo è stato ridotto al 50 percento.

## <a name="version-2040"></a>Versione 2.0.4.0

La versione 2.0.4.0 è stata la prima versione generalmente disponibile dell'app per dispositivi mobili Warehouse Management.

### <a name="new-features-fixes-and-improvements-in-version-2040"></a>Nuove funzionalità, correzioni e miglioramenti nella versione 2.0.4.0

Questa versione introduce le seguenti nuove funzionalità, correzioni e miglioramenti che non erano disponibili nella versione di anteprima:

- Se una scheda dettagli include due etichette con dati identici, una delle etichette è nascosta.
- I caratteri speciali ora vengono mostrati per impostazione predefinita e l'opzione per nasconderli è stata rimossa dalle impostazioni utente.
- I pulsanti di invio disabilitati ora vengono mostrati come non disponibili nella visualizzazione compatta dei palmari.
- Una modifica alla logica di sequenza per i controlli garantisce un ridimensionamento più fluido tra i dispositivi. Pertanto, è meno necessario regolare la scala dei caratteri o dei pulsanti.
- Il tema del colore predefinito è stato modificato in *Scuro*.
- L'icona mancante per il pulsante di invio disabilitato è stata aggiunta nella vista della barra multifunzione.
- Le eccezioni di timeout ora aprono la pagina di connessione invece di mostrare un errore in linea.
- Se non è disponibile alcuna azione di invio (come **OK**, **Sì**, **Accetta**, **Fatto**, o **Finito**), il pulsante di invio sarà disabilitato.
- La stabilità dell'app è stata migliorata.
- C'è una correzione per la vulnerabilità della sicurezza [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).
- **Versione Windows:** È stato risolto un problema su Windows, per cui i menu non rispondevano dopo il ridimensionamento della finestra.

### <a name="known-issue-in-version-2040"></a>Problema noto nella versione 2.0.4.0

In questa versione è presente il seguente problema noto:

- Questa versione ha un problema con i dispositivi che utilizzano Android 4.4. Potresti riscontrare problemi quando usi l'app su questa versione di Android.
