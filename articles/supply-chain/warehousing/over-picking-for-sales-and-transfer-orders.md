---
title: Prelievo in eccesso per ordini cliente e di trasferimento
description: Questo argomento spiega come abilitare il prelievo in eccesso per gli ordini cliente e gli ordini di trasferimento.
author: GalynaFedorova
ms.date: 07/06/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-06
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 3c6f9d386f79754edce38e4e2cf4c9bfefbce69bdb252e8754f39d909827fa02
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722153"
---
# <a name="over-picking-for-sales-orders-and-transfer-orders"></a>Prelievo in eccesso per ordini cliente e di trasferimento

[!include [banner](../includes/banner.md)]

Questo argomento presenta uno scenario che mostra come consentire a un lavoratore specifico o a tutti i lavoratori di effettuare un prelievo in eccesso. Il processo di prelievo in eccesso consente un prelievo in eccesso controllato durante il lavoro di prelievo.

Il prelievo in eccesso in magazzino è un concetto semplice. Il sistema consente ai lavoratori di prelevare più articoli di quelli specificati per un ordine. Tuttavia, considera ancora il limite di consegna in eccesso impostato a livello di riga per l'ordine di trasferimento o l'ordine cliente. Se tale limite viene superato, l'app Warehouse Management avvisa i lavoratori che stanno superando il limite di consegna in eccesso.

La funzione di prelievo in eccesso aiuta a ridurre al minimo la manutenzione e aiuta anche la tua configurazione a rimanere flessibile. Puoi definire una o più voci di menu del dispositivo mobile e abilitare il prelievo in eccesso solo per alcune di esse. È inoltre possibile evitare che i lavoratori selezionati prelevino in eccesso gli ordini cliente e/o gli ordini di trasferimento senza dover modificare le voci di menu. Puoi disattivare una o entrambe queste funzionalità nelle impostazioni del lavoratore pertinenti.

La funzione di prelievo in eccesso può aiutare i lavoratori a risparmiare tempo e fatica quando prelevano e spediscono gli articoli. Ad esempio, la funzione consente ai lavoratori di eseguire queste attività:

- Compensare la riduzione durante il prelievo o la spedizione.
- Evitare di dover disimballare il materiale di imballaggio durante il processo di prelievo.
- Compensare i danni all'oggetto durante il trasporto.
- Spedire una variazione di quantità o unità di misura.
- Ridurre al minimo l'interruzione delle quantità nelle targhe.
- Evitare lo spreco di materiale e la scarsità di materiali costosi.
- Misurare la quantità prelevata dopo il prelievo (ad esempio, tramite la pesatura del camion).

> [!IMPORTANT]
> La funzione di prelievo in eccesso si applica solo al prelievo e all'elaborazione dell'ordine cliente e dell'ordine di trasferimento. Il rifornimento non supporta il prelievo in eccesso. Quando viene eseguito il lavoro di rifornimento, il sistema non consentirà agli utenti di effettuare un prelievo in eccesso.

Lo scenario in questo argomento mostra come impostare e utilizzare la funzionalità di prelievo in eccesso.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Prerequisito dello scenario: rendere disponibili i dati demo

Lo scenario in questo argomento fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management. Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su *USMF* prima di iniziare.

## <a name="scenario-setup"></a>Impostazione dello scenario

Prima di elaborare lo scenario di esempio, è necessario abilitare il prelievo in eccesso sia per il lavoratore pertinente che per la voce di menu pertinente.

### <a name="set-up-a-worker-to-allow-for-over-picking"></a>Impostare un lavoratore per consentire il prelievo in eccesso

Di seguito è riportata la procedura generale per configurare un lavoratore per abilitare il prelievo in eccesso per ordini cliente e ordini di trasferimento separatamente. Questa configurazione controlla quale addetto al prelievo può eseguire il prelievo in eccesso e se tale lavoratore può eseguire un prelievo in eccesso sia per gli ordini di trasferimento che per gli ordini cliente.

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoratore**.
1. Nel riquadro dell'elenco, seleziona **Julia Funderburk**.
1. Nella scheda dettaglio **Utenti** seleziona la riga con i seguenti valori. Se nessuna riga esistente ha questi valori, creala.

    - **ID utente:** *24*
    - **Nome utente:** *WH 24*
    - **Magazzino predefinito:** *24*
    - **Nome menu:** *Principale*

1. Nella scheda dettaglio **Lavoro** imposta i seguenti valori per l'utente *24* se non sono già impostati:

    - **Consenti prelievo in eccesso per ordini cliente:** *Sì*
    - **Consenti prelievo in eccesso per ordini di trasferimento:** *Sì*

### <a name="set-up-a-mobile-device-menu-item-to-allow-for-over-picking"></a>Impostare una voce di menu del dispositivo mobile per consentire il prelievo in eccesso

Ecco la procedura generale per configurare una voce di menu di un dispositivo mobile per abilitare il prelievo in eccesso. A seconda dei requisiti aziendali per il livello di autorizzazione del lavoratore che utilizzerà il menu del dispositivo mobile, alcuni parametri potrebbero essere attivati o disattivati.

1. Passa a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel riquadro dell'elenco, seleziona il record denominato *Prelievo vendite*. Se nessun record esistente ha questo nome, crealo. Conferma o imposta i seguenti valori per il record:

    - **Nome voce di menu:** *Prelievo vendite*
    - **Titolo:** *Prelievo vendite*
    - **Modalità:** *Lavoro*
    - **Utilizza lavoro esistente:** *Sì*
    - **Diretto da:** *Diretto dall'utente*
    - **Ignora targa destinazione:** *Sì*
    - **Ignora targa durante inserimento:** *Sì*
    - **Mantieni il lavoro bloccato dall'utente:** *Sì*
    - **Consenti prelievo in eccesso:** *Sì*

> [!IMPORTANT]
> Dopo aver abilitato i parametri rilevanti sia per il lavoratore che per la voce di menu del dispositivo mobile, il prelievo in eccesso può essere elaborato solo tramite il dispositivo mobile.

## <a name="example-scenario"></a>Scenario di esempio

Dopo che i prerequisiti, l'impostazione del lavoratore e l'impostazione della voce di menu sono a posto, sei pronto per lavorare con la funzione.

### <a name="create-a-sales-order-that-allows-for-overdelivery"></a>Creare un ordine cliente che consente il prelievo in eccesso

1. Accedere a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Seleziona **Nuovo** per creare un nuovo ordine cliente.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-001*
    - **Magazzino:** *24*

1. Selezionare **OK**.
1. Viene aperto il nuovo ordine cliente. Nella Scheda dettaglio **Righe ordine cliente**, aggiungere una riga che abbia le seguenti impostazioni:

    - **Numero articolo:** *A0001*
    - **Quantità:** *10*

1. Nella scheda dettaglio **Dettagli riga**, nella scheda **Consegna**, impostare il campo **Limite massimo di fornitura** su *10*.
1. Nella scheda dettaglio **Righe ordine cliente**, selezionare **Scorte \> Prenotazione**.
1. Nella pagina **Prenotazione**, quindi nel riquadro azioni, selezionare **Prenota lotto** per prenotare le scorte.
1. Chiudi la pagina **Prenotazione**.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

Quando il rilascio è completato, verranno ricevuti messaggi informativi che mostrano l'ID ondata e l'ID carico creati.

### <a name="get-the-work-id-and-license-plate-number-for-the-new-order"></a>Ottienere l'ID lavoro e il numero di targa per il nuovo ordine

Quando è stato rilasciato l'ordine cliente al magazzino, il sistema ha creato un nuovo ID lavoro con una riga di prelievo. Segui questi passaggi per trovare l'ID lavoro e l'assegnazione della targa.

1. Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.
1. Nella griglia **Panoramica** cerca la colonna **Numero ordine** per l'ordine cliente appena creato. Prendi nota dell'ID lavoro corrispondente all'ordine cliente.
1. Seleziona la riga per il nuovo ordine cliente per visualizzare le informazioni correlate nella griglia **Righe**. Prendi nota della posizione da cui verrà prelevato ogni articolo.
1. Passare a **Gestione articoli \> Richieste di informazioni e report \> Scorte disponibili**.
1. Nel riquadro azioni selezionare **Dimensioni**.
1. Nella finestra di dialogo **Visualizzazione dimensioni** assicurati che le caselle di controllo **Targa**, **Magazzino**, e **Numero articolo** siano selezionate, quindi seleziona **OK**.
1. Nel riquadro **Filtro** impostare i seguenti filtri:

    - **Numero articolo** – **è uno tra** – *A0001*
    - **Magazzino** - **inizia con** - *24*

1. Selezionare **Applica**.
1. Prendere nota dei valori **Targa** visualizzati.

### <a name="over-pick-the-order-by-using-the-warehouse-management-mobile-app"></a>Prelievo in eccesso dell'ordine utilizzando l'app per dispositivi mobili Warehouse Management

1. Accedi all'app per dispositivi mobili Gestione magazzino come utente nel magazzino *24*.
1. Passare a **In uscita \> Prelievo vendite**.
1. Nel campo **Analizza ID lavoro o targa**, immetti l'ID lavoro creato per l'ordine cliente.
1. Selezionare **OK** (segno di spunta).
1. Seleziona **Prelievo in eccesso**.
1. Imposta il campo **Qtà prelievo** su *14*.
1. Selezionare **OK** (segno di spunta).

    Nella pagina **Prelievo in eccesso** viene visualizzato il seguente messaggio: "Il limite massimo di fornitura della riga è pari al 40,00 percento, mentre quello consentito è solo del 10,00 percento." Questo messaggio indica che la quantità di prelievo immessa supera il limite di massimo di fornitura. Il limite massimo di fornitura per la riga dell'ordine cliente è del 10%. Pertanto, per una quantità specificata di 10, è possibile effettuare un prelievo in eccesso solo di 1, per una quantità di prelievo totale di 11.

1. Imposta il campo **Qtà prelievo** su *11*.
1. Selezionare **OK** (segno di spunta).
1. Nel campo **Targa** inserisci la targa di cui hai preso nota nella sezione precedente.
1. Nel campo **Targa destinazione**, immetti la targa destinazione. Si noti che sono visualizzati l'ubicazione di prelievo (*FLOOR-001*), l'articolo (*A0001*) e la quantità (*11 pezzi*).
1. Selezionare **OK** (segno di spunta).
1. Esaminare le informazioni nella pagina **Ordini cliente - Stoccaggio**. Il campo **Ubicazione** deve indicare che gli articoli prelevati vengono spostati all'ubicazione *PORTELLONE*.
1. Selezionare **OK** (segno di spunta).

Nella pagina **Esegui scansione ID lavoro/ID targa**, viene visualizzato il messaggio "Lavoro completato". Questo messaggio indica che l'ID lavoro dell'ordine cliente è stato completato e che la quantità prelevata in eccesso non supera il limite massimo di fornitura del 10%.
