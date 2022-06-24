---
title: Certificazione di origine USMCA
description: Questa funzione consente di stampare i documenti di certificazione di origine richiesti dall'United States-Mexico-Canada Agreement (USMCA).
author: Weijiesa
ms.date: 10/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-10-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 2a87e1aa27085f1b4821d27cece782dffbcd2096
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851364"
---
# <a name="usmca-certification-of-origin"></a>Certificazione di origine USMCA

[!include [banner](../includes/banner.md)]

Questa funzione consente di stampare i documenti di certificazione di origine richiesti dall'United States-Mexico-Canada Agreement (USMCA).

Il *documento della certificazione di origine USMCA* contiene gli elementi di dati minimi richiesti per la dichiarazione. Alcuni elementi di dati possono essere precompilati prima della stampa, mentre altri devono essere compilati manualmente dopo la stampa. Per ottenere il trattamento tariffario preferenziale, il documento deve essere compilato e in possesso dell'importatore al momento della dichiarazione. Il documento può essere completato dall'importatore, dall'esportatore o dal produttore.

È possibile stampare il documento per una singola spedizione dalla pagina elenco **Tutte le spedizioni** o dalla pagina **Dettagli spedizione**.

Il documento è accessibile solo quando il paese dell'indirizzo principale della persona giuridica è Stati Uniti.

A seconda della selezione di stampa del documento, il documento può essere precompilato con i dati del sistema. È possibile modificare o aggiungere dati al documento stampato esportando il documento stampato in un formato modificabile, ad esempio Microsoft Word. Dopo l'esportazione, è possibile applicare le modifiche richieste prima che venga effettuata una dichiarazione.

## <a name="turn-on-the-usmca-feature"></a>Attivare la funzionalità USMCA

Prima di poter utilizzare la funzionalità USMCA, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione trasporto*
- **Nome funzionalità:** *Documento certificazione di origine USMCA*

## <a name="document-content"></a>Contenuto del documento

Il documento certificazione di origine USMCA contiene i seguenti elementi di dati:

- Elementi di indirizzo
- Ruolo dell'entità di certificazione
- Spedizione singola
- Fatture
- Periodo di copertura
- Dettagli articoli
- Firma dell'entità di certificazione
- Numero di pagine

Per ulteriori informazioni su ciascuno di questi elementi e su dove si trovano i relativi valori, vedi le sezioni rimanenti in questo articolo.

## <a name="print-a-usmca-certification-of-origin-document"></a>Stampare un documento certificazione di origine USMCA

Per stampare un documento certificazione di origine USMCA per una spedizione, procedere come segue:

1. Effettuare una delle seguenti operazioni:
    - Andare a **Gestione trasporti> Spedizioni> Tutte le spedizioni** e selezionare la spedizione per la quale si desidera stampare il documento.
    - Aprire la pagina **Dettagli spedizione** per la spedizione per la quale si desidera stampare il documento (ci sono diversi modi per arrivarci, anche dalla pagina **Tutte le spedizioni**).
1. Nel riquadro azioni aprire la scheda **Spedizioni** e dal gruppo **Stampa** selezionare **Certificazione di origine USMCA**.
1. Si apre la finestra di dialogo **Certificato o origine**. Effettuare le impostazioni descritte nelle sottosezioni seguenti e quindi selezionare **OK** per generare il documento.
1. Viene visualizzata un'anteprima del documento. Utilizzare i comandi forniti nel riquadro azioni per stampare o esportare il documento secondo necessità.

### <a name="certifying-party"></a>Entità di certificazione

Utilizzare l'elenco a discesa **Entità di certificazione** per identificare il tipo di parte che sta stampando il documento. Specificare se l'entità di certificazione è *Esportatore*, *Esportatore e produttore*, *Produttore* o *Importatore* oppure lasciare il campo vuoto se l'entità di certificazione non è nessuno di questi. L'opzione selezionata determina cosa viene stampato nelle sezioni dell'indirizzo del documento.

L'**Entità di certificazione** scelta verrà inclusa nel documento stampato.

Il documento può essere stampato sia per le spedizioni in entrata che per quelle in uscita. Selezionare *Importatore* come **Entità di certificazione** solo per le spedizioni in entrata.

La tabella seguente descrive i tipi di informazioni inclusi nel documento in base all'**Entità di certificazione** che si sceglie.

| Entità di&nbsp;certificazione | Descrizione |
|---|---|
| *\[Vuoto\]* | Aggiunge i seguenti dettagli al documento:<ul><li>**Dettagli entità di certificazione**: Utilizza i dettagli dell'indirizzo per il magazzino di spedizione, se disponibile; in caso contrario utilizza l'indirizzo del sito di spedizione, se disponibile; in caso contrario utilizza l'indirizzo della persona giuridica (società) selezionata in Supply Chain Management.</li><li>**Dettagli esportatore**: Vuoto</li><li>**Dettagli produttore**: Vuoto</li><li>**Dettagli importatore**: Vuoto</li><ul>|
| *Esportatore* | Aggiunge i seguenti dettagli al documento:<ul><li>**Dettagli entità di certificazione**: Utilizza i dettagli dell'indirizzo per il magazzino di spedizione, se disponibile; in caso contrario utilizza l'indirizzo del sito di spedizione, se disponibile; in caso contrario utilizza l'indirizzo della persona giuridica (società) selezionata in Supply Chain Management.</li><li>**Dettagli esportatore**: Utilizza i dettagli dell'indirizzo per la persona giuridica.</li><li>**Dettagli produttore**: Vuoto</li><li>**Dettagli importatore**: Utilizza il conto fattura per l'ordine cliente correlato.</li><ul>|
| *Esportatore e produttore* | Aggiunge i seguenti dettagli al documento:<ul><li>**Dettagli entità di certificazione**: Utilizza i dettagli dell'indirizzo per il magazzino di spedizione, se disponibile; in caso contrario utilizza l'indirizzo del sito di spedizione, se disponibile; in caso contrario utilizza l'indirizzo della persona giuridica (società) selezionata in Supply Chain Management.</li><li>**Dettagli esportatore**: Utilizza i dettagli dell'indirizzo per la persona giuridica.</li><li>**Dettagli produttore**: Utilizza i dettagli dell'indirizzo per la persona giuridica.</li><li>**Dettagli importatore**: Utilizza il conto fattura per l'ordine cliente correlato.</li><ul>|
| *Importatore* | Aggiunge i seguenti dettagli al documento:<ul><li>**Dettagli entità di certificazione**: Utilizza i dettagli dell'indirizzo per il magazzino di spedizione, se disponibile; in caso contrario utilizza l'indirizzo del sito di spedizione, se disponibile; in caso contrario utilizza l'indirizzo della persona giuridica (società) selezionata in Supply Chain Management.</li><li>**Dettagli esportatore**: Vuoto</li><li>**Dettagli produttore**: Vuoto</li><li>**Dettagli importatore**: Utilizza i dettagli dell'indirizzo per la persona giuridica.</li><ul>|
| *Produttore* | Aggiunge i seguenti dettagli al documento:<ul><li>**Dettagli entità di certificazione**: Utilizza i dettagli dell'indirizzo per il magazzino di spedizione, se disponibile; in caso contrario utilizza l'indirizzo del sito di spedizione, se disponibile; in caso contrario utilizza l'indirizzo della persona giuridica selezionata in Supply Chain Management.</li><li>**Dettagli esportatore**: Vuoto</li><li>**Dettagli produttore**: Utilizza i dettagli dell'indirizzo per la persona giuridica.</li><li>**Dettagli importatore**: Vuoto</li><ul>|

### <a name="has-various-producers"></a>Ha diversi produttori

L'elenco a discesa **Entità di certificazione** controlla il testo da utilizzare per i dettagli del produttore nel documento. Sono disponibili le seguenti opzioni:

- *Vari produttori* - Stampa il testo "Vari" nei dettagli del produttore.
- *Disponibile su richiesta* - Stampa il testo "Disponibile su richiesta delle autorità importazione" nei dettagli del produttore.

Quando l'**entità di certificazione** è impostata su *Esportatore e produttore* o *Produttore*, l'impostazione **Ha vari produttori** viene annullata e i dettagli dell'indirizzo del produttore saranno gli stessi dell'entità di certificazione.

### <a name="blanket-period"></a>Periodo di copertura

Utilizzare le impostazioni **Inizio periodo di copertura** e **Fine periodo di copertura** per stabilire un periodo di copertura, durante il quale il documento coprirà più spedizioni di merci identiche, anche se il documento viene stampato per una sola spedizione. È possibile impostare le date del periodo di copertura senza alcun vincolo e verranno aggiunte al documento. È anche possibile lasciare queste impostazioni vuote o impostarle nel passato.

### <a name="is-single-shipment"></a>Spedizione singola

Nella finestra di dialogo **Certificato di origine** impostare **Spedizione singola** su uno dei seguenti valori:

- *Sì* - Aggiunge "Spedizione singola: Sì" accanto al numero di fattura.
- *No* - Non aggiunge nulla.

## <a name="other-information-included-in-the-document"></a>Altre informazioni incluse nel documento

Oltre agli elementi opzionali che si selezionano utilizzando la finestra di dialogo **Certificato di origine** il documento certificazione di origine USMCA includerà le informazioni e i campi personalizzati riepilogati nelle seguenti sottosezioni. Alcune di queste informazioni devono essere inserite manualmente dopo aver generato il documento.

### <a name="invoice-number"></a>Numero fattura

Gli ID delle fatture di vendita relative alle spedizioni vengono stampati sul documento indipendentemente dal periodo di copertura. I numeri delle fatture vengono stampati indipendentemente dalla selezione di **Spedizione singola**.

### <a name="item-details"></a>Dettagli articoli

Il documento fornisce diverse sezioni che elencano i dettagli di elementi specifici, che sono:

- **Numero SKU**: Stampa il numero di articolo del prodotto rilasciato.

- **Descrizione**: Stampa la descrizione o il nome del prodotto rilasciato. Se esiste una descrizione nella lingua dell'utente, questa viene stampata. Se non esiste questa descrizione, il nome viene stampato nella lingua dell'utente. Se il nome non esiste, viene stampato il nome dell'articolo.

- **Classificazione tariffa sistema armonizzato (SA)**: Stampa il piano tariffario armonizzato associato al prodotto. È possibile impostare questi programmi andando in **Gestione trasporti \> Impostazione \> Standard di trasporto \> Piani tariffari armonizzati**.

- **Criterio di origine:** È necessario immettere manualmente i dati in questa sezione la prima volta che si rilascia il documento.

- **Paese di origine:** Stampa il paese di origine a cui si applica andando in **Gestione informazioni sui prodotti \> Impostazione \> Conformità del prodotto \> Paese di origine** (vedere anche [Paese di origine](../pim/country-of-origin.md)). Il codice ISO per il paese di origine viene stampato in base al paese/area geografica di destinazione nell'indirizzo di consegna della spedizione e nell'articolo. Se non è stato impostato alcun dato sul paese di origine, questo valore torna all'impostazione trovata in **Prodotto rilasciato \> Commercio estero \> Origine**. Se ancora non vengono trovati dati sul paese di origine, è necessario inserire manualmente il paese di origine dopo aver generato il documento.

### <a name="certifier-signature-and-date"></a>Firma e data dell'entità di certificazione

È necessario immetterli manualmente dopo aver generato il documento.

### <a name="consists-of-number-of-pages"></a>Composto dal numero di pagine

L'utente che firma la certificazione deve inserire manualmente il numero di pagine (per la verifica) dopo aver generato il documento.

### <a name="page-numbers"></a>Numeri di pagina

La pagina corrente e il numero di pagine stampate nella parte inferiore del documento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]