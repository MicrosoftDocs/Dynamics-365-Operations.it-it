---
title: Utilizzare il giornale di registrazione delle scorte di sicurezza per aggiornare la copertura minima per gli articoli
description: Questo argomento descrive come utilizzare le registrazioni delle scorte di sicurezza per aggiornare la quantità delle scorte di sicurezza per gli articoli calcolando le proposte di copertura minima in base alle transazioni storiche.
author: t-benebo
ms.date: 10/28/2021
ms.topic: article
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, ReqItemTableSetup, ReqItemTable, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-10-28
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 391f741ee08eb0624e80f5c297009c527e50c14c
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468554"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage-for-items"></a>Utilizzare il giornale di registrazione delle scorte di sicurezza per aggiornare la copertura minima per gli articoli

[!include [banner](../../includes/banner.md)]

Le scorte di sicurezza indicano una quantità aggiuntiva di un articolo contenuto nel magazzino al fine di ridurre il rischio che l'articolo si esaurisca. Le scorte di sicurezza vengono utilizzate come margine nel caso in cui gli ordini cliente arrivino e il fornitore non sia in grado di soddisfare la data di spedizione richiesta dal cliente.

Questo argomento illustra come utilizzare il giornale di registrazione delle scorte di sicurezza per calcolare le proposte di copertura minima basate sulle transazioni storiche e poi aggiornare la copertura articoli con le proposte.

## <a name="overview-of-minimum-coverage-usage"></a>Panoramica dell'utilizzo della copertura minima

Le scorte di sicurezza vengono configurate nella pagina **Copertura articoli** per ogni articolo. Diversi tipi di rifornimento sono rappresentati da diversi codici di copertura. (Per ulteriori informazioni, vedi [Garantire le scorte di sicurezza per gli articoli](safety-stock-replenishment.md) ). Tuttavia, tutti i codici di copertura utilizzano il valore impostato nel campo **Minimo** della pagina **Copertura articoli** per ogni articolo. Esistono due approcci principali per l'utilizzo del campo **Minimo**:

- **Quantità minima per scopi min/max** – Questo approccio utilizza la quantità minima insieme alla logica min/max. Si applica quando il campo **Codice copertura** è impostato su *Min/Max* per l'articolo o il gruppo di copertura in questione. La quantità **Minima** rappresenta l'utilizzo medio giornaliero moltiplicato per il lead time dell'articolo.
- **Quantità minima ai fini del piano di scorte** – Questo approccio utilizza la quantità minima per rappresentare un piano delle scorte in combinazione con le previsioni della domanda. Si applica quando il campo **Codice copertura** è impostato su *Periodo* o *Fabbisogno* per l'articolo o il gruppo di copertura in questione. La quantità **Minima** rappresenta un piano di scorte che riflette il livello di servizio clienti desiderato per ridurre le scorte esaurite, le spedizioni parziali e i tempi di consegna. La quantità minima riflette una percentuale di accuratezza della previsione per un determinato articolo. Non rappresenta una posizione di inventario desiderata.

Il valore **Minimo** può essere impostato in tre modi:

- Manualmente nella pagina **Copertura articoli**
- Dal framework Gestione dati (entità di dati *Copertura articoli*)
- Dal calcolo delle scorte di sicurezza eseguito dai giornali di registrazione delle scorte di sicurezza

## <a name="calculate-minimum-coverage-based-on-historical-usage"></a>Calcolare la copertura minima in base all'utilizzo storico

I giornali di registrazione delle scorte di sicurezza vengono utilizzati per calcolare una quantità minima proposta in base all'utilizzo storico di un articolo, per scopi min/max o per scopi di piano delle scorte. L'utilizzo storico rappresenta tutte le transazioni in uscita durante un periodo specificato. Queste transazioni in uscita includono le transazioni degli ordini di vendita e le rettifiche di magazzino. I calcoli identificano anche l'impatto della quantità minima proposta sul valore delle scorte e la variazione del valore delle scorte rispetto alle quantità minime attuali.

Ciascuna riga del giornale di registrazione delle scorte di sicurezza rappresenta un articolo e le relative dimensioni di copertura. Queste righe del giornale di registrazione vengono create e mostrate nella pagina **Righe del giornale di registrazione delle scorte di sicurezza** (**Pianificazione generale \> Pianificazione generale \> Esegui \> Calcolo delle scorte di sicurezza**). Il processo aziendale per l'utilizzo dei giornali di registrazione delle scorte di sicurezza per calcolare le quantità minime proposte è descritto più avanti in questo argomento.

Il responsabile della pianificazione utilizza un giornale di registrazione delle scorte di sicurezza per calcolare le quantità minime proposte per gli articoli selezionati, in base all'utilizzo storico durante i periodi selezionati. I minimi proposti possono essere sovrascritti manualmente come richiesto ed è possibile esaminare il potenziale impatto dei minimi proposti sul valore dell'inventario. Quando il giornale di registrazione viene pubblicato, le quantità minime associate nella copertura articolo vengono aggiornate automaticamente.

### <a name="create-a-new-safety-stock-journal-name"></a>Creare un nuovo nome per il giornale di registrazione delle scorte di sicurezza

È necessario creare almeno un nome per il giornale di registrazione delle scorte di sicurezza prima di poter generare questo tipo di giornale. In genere è possibile utilizzare diversi nomi di giornale di registrazione per aiutare a separare i calcoli delle scorte di sicurezza.

1. Vai a **Pianificazione generale \> Imposta \> Nomi giornali di registrazione scorte di sicurezza**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella nuova riga, impostare i seguenti campi:

    - **Nome** - Immetti un nome breve per il giornale di registrazione.
    - **Descrizione** – Immetti una breve descrizione del giornale di registrazione.
    - **Privato per gruppo di utenti** – Per limitare il gruppo di destinatari per il nome del giornale di registrazione corrente, selezionare un gruppo di utenti.
    - **Elimina le righe dopo la registrazione** – Seleziona questa casella di controllo per ripulire le righe del giornale di registrazione per impostazione predefinita mentre le pubblichi. Cancellalo per mantenere tutte le righe pubblicate.

    Il campo **Tipo giornale di registrazione** è di sola lettura ed è preimpostato su *Scorte di sicurezza*.

1. Chiudi la pagina.

### <a name="create-a-safety-stock-journal-and-lines"></a>Creare le righe e un giornale di registrazione delle scorte di sicurezza

Questo passaggio crea un giornale di registrazione e vi aggiunge automaticamente delle righe. Ogni riga identifica un articolo, le sue dimensioni di copertura e diverse quantità calcolate dalla cronologia di utilizzo. Le quantità calcolate includono le uscite medie per lead time dell'articolo, le uscite medie per mese e lo scarto standard mensile.

#### <a name="automatically-generate-journal-lines"></a>Generare automaticamente righe del giornale di registrazione

Le righe del giornale di registrazione possono essere generate automaticamente solo se non esistono righe per il giornale di registrazione attualmente visualizzato.

Segui questi passaggi per generare automaticamente le righe del giornale di registrazione.

1. Vai a **Pianificazione generale \> Pianificazione generale \> Esegui \> Calcolo scorte di sicurezza**.
1. Nel Riquadro azioni selezionare **Nuovo**. Viene creato un nuovo giornale di registrazione delle scorte di sicurezza.
1. Nella scheda dettaglio **Dettagli intestazione giornale di registrazione**, imposta i seguenti campi:

    - **Nome** – Seleziona il nome del giornale di registrazione delle scorte di sicurezza a cui aggiungere la riga.
    - **Descrizione** – Il valore predefinito è la descrizione del nome del giornale di registrazione selezionato. Tuttavia, è possibile modificare il valore in base alle esigenze.
    - **Elimina le righe dopo la registrazione** – Seleziona questa casella di controllo per ripulire le righe del giornale di registrazione mentre le pubblichi. Cancellalo per mantenere tutte le righe pubblicate. L'impostazione viene ereditata dal nome del giornale di registrazione selezionato.

    Il campo **Giornale di registrazione** è di sola lettura e mostra il numero ID del giornale di registrazione che stai creando e a cui stai aggiungendo righe.

1. Nella Scheda dettaglio **Righe del giornale di registrazione** seleziona **Crea righe** sulla barra degli strumenti.
1. Nella finestra di dialogo **Crea righe giornale di registrazione per livello scorte minime proposto**, imposta i seguenti campi:

    - **Da data** – Selezionare la data di inizio del periodo di cui includere le emissioni nel calcolo.
    - **A data** – Selezionare la data di fine del periodo di cui includere le emissioni nel calcolo. Devono trascorrere almeno due mesi tra la data di inizio e quella di fine.
    - **Calcola deviazione standard** – Imposta questa opzione su *Aì* per calcolare la deviazione standard. Devi impostare questa opzione su *Sì* per utilizzare l'opzione **Usa livello di servizio** quando calcoli la proposta (come descritto più avanti in questo argomento).

1. Sulla scheda dettaglio **Record da includere**, puoi impostare filtri e vincoli per definire quali articoli includere. (Ad esempio, puoi filtrare per il valore **Gruppo di copertura**). Seleziona **Filtra** per aprire una finestra di dialogo dell'editor di query standard, in cui è possibile definire criteri di selezione, criteri di ordinamento e join. I campi funzionano esattamente come per altri tipi di query in Microsoft Dynamics 365 Supply Chain Management.
1. Nella scheda dettaglio **Esegui in background** scegli se eseguire il lavoro in modalità batch e/o impostare una programmazione ricorrente. I campi funzionano esattamente come funzionano per altri tipi di [processi in background](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Supply Chain Management.
1. Seleziona **OK**. Le righe vengono create per le dimensioni che hanno operazioni di magazzino.

#### <a name="manually-add-or-remove-journal-lines"></a>Aggiungi o rimuovi manualmente le righe del giornale di registrazione

È possibile aggiungere e/o rimuovere manualmente le righe del giornale di registrazione in qualsiasi momento (dopo o al posto della generazione automatica delle righe). Utilizza i seguenti pulsanti sulla barra degli strumenti della Scheda dettaglio **Righe giornale di registrazione**:

- **Nuovo** – Aggiungere una nuova riga. Quindi immetti un valore in ogni colonna per definire il prodotto da calcolare e per cui applicare nuovi minimi. Poiché i calcoli minimi proposti non sono disponibili per le righe aggiunte manualmente, nessun nuovo valore **Quantità minima calcolata** viene mostrato per loro. Pertanto, è necessario inserire manualmente i valori **Nuova quantità minima**. Tuttavia, è ancora possibile visualizzare il potenziale impatto del valore **Nuova quantità minima** sul valore di magazzino e la potenziale variazione delle scorte rispetto al minimo attualmente specificato.
- **Elimina** – Elimina la riga selezionata.
- **Elimina righe giornale di registrazione** – Elimina tutte le righe nel giornale di registrazione.

### <a name="calculate-a-proposal"></a>Calcola una proposta

Questo passaggio calcola un minimo proposto per ogni riga del giornale di registrazione e il potenziale impatto della riga sul valore di magazzino. (Il minimo proposto è mostrato come valore **Quantità minima calcolata**). È possibile eseguire il calcolo più volte, come richiesto. Il calcolo aggiorna il valore **Quantità minima calcolata** visualizzato per tutte le righe del giornale di registrazione.

I calcoli mostrati non influiranno sui valori effettivi della quantità minima per ciascun prodotto finché non si seleziona **Registra** nel riquadro azioni. In quel momento, i valori **Nuova quantità minima** verranno applicati a ciascun prodotto.

1. Vai a **Pianificazione generale \> Pianificazione generale \> Esegui \> Calcolo scorte di sicurezza**.
1. Apri il giornale di registrazione per cui calcolare una proposta. In alternativa, crea un nuovo giornale di registrazione come descritto in precedenza in questo argomento.
1. Nella Scheda dettaglio **Righe del giornale di registrazione** seleziona **Calcola proposta** sulla barra degli strumenti. Non è necessario selezionare alcuna riga.
1. Nella finestra di dialogo **Calcola proposta per livello scorte minime**, imposta i seguenti campi:

    - **Utilizza uscita media durante il lead time** – Seleziona questa opzione per generare i valori **Quantità minima calcolata** basati sull'uscita media durante il periodo specificato. Poi, nel campo **Fattore di moltiplicazione**, immetti un valore per regolare il risultato in base alle esigenze. Ad esempio, inserisci *1.0* per utilizzare la media calcolata esatta o *1.1* per aggiungere un buffer aggiuntivo del 10 percento.
    - **Usa livello di servizio** – Seleziona questa opzione per calcolare un minimo proposto in base al livello di servizio desiderato. Poi, nel campo **Livello di servizio**, seleziona il livello di servizio preferito.
    - **Margine di lead time** – Immetti un valore per estendere il normale lead time (ad esempio, per consentire l'amministrazione).
    - **Utilizza la quantità minima calcolata come nuova quantità minima** – Imposta questa opzione su *Sì* per copiare automaticamente i valori dalla colonna **Quantità minima calcolata** alla colonna **Nuova quantità minima** per tutte le righe dopo che il calcolo è stato completato. Se imposti questa opzione su *No*, il valore **Quantità minima attuale** verrà copiato nella colonna **Nuova quantità minima** per tutte le righe. Dovrai quindi modificare manualmente i valori **Nuova quantità minima** come richiesto.

1. Nella scheda dettaglio **Esegui in background** scegli se eseguire il lavoro in modalità batch e/o impostare una programmazione ricorrente. I campi funzionano esattamente come funzionano per altri tipi di [processi in background](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Supply Chain Management.
1. Seleziona **OK**. I risultati del calcolo sono mostrati nella colonna **Quantità minima calcolata** della Scheda dettaglio **Righe del giornale di registrazione**. Per ora, i valori sono solo valori proposti che non sono ancora stati applicati ai tuoi prodotti.

### <a name="update-minimum-quantity"></a>Aggiornare la quantità minima

È possibile selezionare qualsiasi riga in un giornale di registrazione delle scorte di sicurezza e sovrascrivere manualmente il valore del suo campo **Nuova quantità minima**.

1. Vai a **Pianificazione generale \> Pianificazione generale \> Esegui \> Calcolo scorte di sicurezza**.
1. Apri il giornale di registrazione da modificare. In alternativa, crea un nuovo giornale di registrazione come descritto in precedenza.
1. Nella Scheda dettaglio **Righe del giornale di registrazione**, trova la riga da modificare, quindi modifica il valore nella colonna **Nuova quantità minima**. Ad esempio, potresti impostare il valore **Nuova quantità minima** in modo che corrisponda al valore **Quantità minima calcolata**. Se il valore **Quantità minima calcolata** è *0* (zero), puoi immettere il valore futuro desiderato.

### <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Inviare la nuova quantità minima e convalidare il risultato

Segui questi passaggi per registrare la nuova quantità minima e convalidare il risultato.

1. Vai a **Pianificazione generale \> Pianificazione generale \> Esegui \> Calcolo scorte di sicurezza**.
1. Apri il giornale di registrazione per cui registrare nuove quantità minime. In alternativa, crea un nuovo giornale di registrazione come descritto in precedenza.
1. Nel riquadro Azioni selezionare **Registra**.
1. Nella finestra di dialogo **Registra giornale**, imposta il campo **Trasferisci tutti gli errori di registrazione in un nuovo giornale** come richiesto. Seleziona **OK** per registrare il giornale.
1. Se hai modificato il valore **Nuova quantità minima** per una linea nella Scheda dettaglio **Righe del giornale di registrazione**, puoi confermare la modifica seguendo questi passaggi:

    1. Per la riga che hai modificato, seleziona il collegamento nella colonna **Numero articolo**.
    1. Nella finestra di dialogo **Informazioni sul prodotto**, seleziona il collegamento nel campo **Numero articolo** per aprire il relativo record del prodotto rilasciato.
    1. Nella scheda **Pianifica** del riquadro azione, nel gruppo **Copertura**, seleziona **Copertura articoli**.
    1. Notare che il valore **Minimo** per il sito e il magazzino rettificato utilizzando il giornale di registrazione delle scorte di sicurezza registrato è stato aggiornato in modo che corrisponda alla modifica.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Garantire le scorte di sicurezza per gli articoli](safety-stock-replenishment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
