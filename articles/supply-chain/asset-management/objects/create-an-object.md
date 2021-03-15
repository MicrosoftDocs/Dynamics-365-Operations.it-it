---
title: Creare un cespite
description: Viene descritta la procedura per la creazione di un cespite in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTableCopyStructure, EntAssetObjectTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28c4685c3b6f543324953cd03646d5b15fdb8c59
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019431"
---
# <a name="create-an-asset"></a>Creare un cespite

[!include [banner](../../includes/banner.md)]

 

Viene descritta la procedura per la creazione di un cespite in Gestione cespiti.

1. Fare clic su **Gestione cespiti** > **Comune** > **cespiti** > **Tutti i cespiti** o **Cespiti attivi**.
2. Fare clic sul pulsante **Nuovo**.
3. Nella finestra di dialogo **Crea cespiti**, inserire i dati relativi al **Cespite** (l'ID del cespite) e il nome del cespite. Selezionare la data e l'ora del cespite nel campo **Validità**. A partire da tale data, è possibile installare il cespite in una unità funzionale nonché spostare e sostituire il cespite in una struttura di cespiti.
4. Nel campo **Tipo cespite**, selezionare il tipo per il cespite (campo obbligatorio). Se necessario, selezionare **Produttore cespite** e **Modello cespite** per il cespite. Se un solo prodotto è stato configurato, il prodotto è selezionato automaticamente nel campo **Produttore cespite**. Le opzioni disponibili nei campi **Produttore cespite** e **Modello cespite** dipendono dalla configurazione in [Produttori e modelli di cespiti](../setup-for-objects/product-and-model.md).
5. Nel gruppo **Cespite padre**, il campo **Cespite** è vuoto per impostazione predefinita. Se necessario, è possibile selezionare un cespite padre e quindi tutti i campi del gruppo **Cespite padre** verranno compilati automaticamente.
    >[!NOTE]  
    >Quando si seleziona un cespite padre, due o tre schede sono disponibili: La scheda **Cespiti personali** include i cespiti correlati alle unità funzionali a cui l'addetto alla manutenzione connesso al sistema può essere assegnato. Se non sono impostate unità funzionali per un addetto alla manutenzione nel modulo [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md), la scheda **Cespiti personali** non sarà visibile. La scheda **Cespiti attivi** include un elenco di tutti i cespiti con stato del ciclo di vita del cespite "Attivo". La scheda **Visualizzazione cespiti** mostra una visualizzazione struttura delle unità funzionali e dei cespiti installati nelle unità.

6. L'unità funzionale predefinito impostata verrà suggerita per il cespite nel gruppo **Cespite** > campo **Unità funzionale**. Selezionare un'altra unità funzionale, se necessario.

    >[!NOTE]
    >Dopo aver creato un cespite, è possibile installarlo in un'altra unità funzionale, se necessario. Solo i cespiti di primo livello (cespiti senza un cespite padre corrente) possono essere installati in una unità funzionale. Ciò significa che si imposta il primo livello nonché tutti i cespiti figlio nella unità funzionale selezionata. Ulteriori informazioni sull'installazione in unità funzionali in [Introduzione alle unità funzionali](../functional-locations/introduction-to-functional-locations.md).

7. Fare clic su **OK**.
8. Selezionare il cespite nell'elenco **Tutti i cespiti** e fare clic sul pulsante **Modifica** per aggiungere ulteriori informazioni sul cespite.

## <a name="general-information"></a>Informazioni generali

Unità funzionale a cui il cespite è correlato viene visualizzata nel campo **Unità funzionale**. Se il cespite è un cespite padre, il numero degli eventuali figli correlati al cespite appare nel campo **Figli**. Se il cespite è un cespite secondario di un cespite esistente, l'ID del cespite padre appare nel campo **Padre**.

È possibile modificare le informazioni **Modello cespite** e **Produttore cespite** del cespite, utilizzate per gestire i pezzi di ricambio, pezzi di ricambio alternativi e le impostazioni predefinite del tipo di processo. Fare riferimento a [Produttori e modelli di cespiti](../setup-for-objects/product-and-model.md) per ulteriori informazioni. È inoltre possibile aggiungere le informazioni su **Anno modello** e **Numero di serie**, se necessario.

**Stato del ciclo di vita corrente** viene utilizzato per definire se il cespite è attivo o inattivo. Quando si crea un cespite, la fase è sempre impostata sulla prima fase del gruppo di fasi del cespite. Quando si è pronti per attivare un cespite, scegliere **Aggiorna stato del cespite** e selezionare lo stato del ciclo di vita definito come "cespite attivo" e clic **OK**.

**Nota:** Quando un cespite viene impostato come "inattivo", non sarà più possibile creare ordini di lavoro per il cespite. Inoltre, non è possibile programmare i processi di manutenzione preventiva per un cespite inattivo.

I campi **Livello servizio** e **Criticità** sono relativi agli ordini di lavoro creati per il cespite. I campi mostrano i numeri di **Criticità** e **Livello servizio** calcolati per l'impostazione corrente per il cespite. Fare riferimento a [Livelli di servizio dei cespiti](../setup-for-objects/object-priorities.md) e [Tipi di criticità dei cespiti](../setup-for-objects/object-criticalities.md) per l'impostazione di questi valori.

## <a name="asset"></a>Cespite

È possibile selezionare una **Risorsa** per il cespite. La selezione della risorsa determina quale calendario utilizzare per la programmazione dell'ordine di lavoro. La selezione della risorsa viene utilizzata spesso per i cespiti. Le risorse e i gruppi di risorse sono impostati in **Amministrazione organizzazione** > **Risorse** > **Gruppi di risorse** o **Risorse**.

Nel campo **Numero di cespiti**, è possibile selezionare un cespite da correlare al cespite. Questo campo è rilevante se il cespite è correlato a un progetto di investimento.

- Se il cespite è correlato a un cespite, è possibile creare un tipo di ordine di lavoro da utilizzare per gli ordini di lavoro correlati a un progetto di investimento. 
- Le informazioni sui cespiti per un cespite sono correlate al modulo **Cespiti** in Dynamics 365 Supply Chain Management. Ciò significa che in **Cespiti** > **Cespiti** > **Cespiti**, è possibile ottenere una panoramica dei progetti di Gestione cespiti che possono essere correlati a un cespite selezionando il cespite negli elenchi e visualizzando il contenuto nel riquadro **Informazioni correlate** > sezione **Progetti associati**.


## <a name="details"></a>Dettagli

Nel campo **Attiva dal**, viene mostrata la data in cui è stato aggiornato lo stato del ciclo di vita del cespite a uno stato attivo (vedere [Stati del ciclo di vita del cespite](../setup-for-objects/object-stages.md) sull'impostazione degli stati del ciclo di vita del cespite). Se il cespite non è più attivo e si è aggiornato lo stato del ciclo di vita del cespite allo stato inattivo del ciclo di vita, la data da il quale il cespite è inattivo è mostrata nel campo **Attivo fino a**. Se necessario, queste date può essere modificato manualmente.

Se necessario, è possibile inserire una data prevista per la sostituzione del cespite nel campo **Data di sostituzione**. Valore stimato per la sostituzione del cespite può essere inserito nel campo **Valore di sostituzione**. Esempio: È possibile utilizzare le informazioni di sostituzione per paragonarle ai costi di manutenzione del cespite e successivamente prendere una decisione per l'acquisto di un nuovo cespite se i costi di manutenzione del cespite esistente aumentano rapidamente.

## <a name="notes"></a>Note

È possibile aggiungere note correlate al cespite nella Scheda dettaglio **Note**. Fare clic sul pulsante **Aggiungi timbro data/ora** prima di scrivere la nota, se si desidera aggiungere le informazioni utente e una data/timbro data/ora alla nota.

## <a name="attributes"></a>Attributi

In questa Scheda dettaglio, è possibile impostare i valori degli attributi del cespite. Tali attributi consentono di descrivere le proprietà o caratteristiche relative al cespite, ad esempio, alla dimensione, il peso, o alla configurazione della macchina.

Fare clic **Aggiungi riga** e selezionare il tipo di attributo. Dopo, immettere **Valore** relativo al tipo di attributo e salvare il record.

>[!NOTE] 
>È possibile ottenere una panoramica dei tipi di attributo del cespite e la relativa relazione con i cespiti in **Attributo cespite** **Panoramica attributi cespiti**. Fare riferimento a [Panoramica degli attributi del cespite](../objects/object-specification-overview.md) per ulteriori informazioni.

## <a name="vendor"></a>Fornitore

Nella Scheda dettaglio **Fornitore**, selezionare un conto fornitore per il cespite. Inoltre, se una garanzia del fornitore è stata concessa, è possibile inserire le informazioni di garanzia in questo campo.

## <a name="address"></a>Indirizzo

Nella Scheda dettaglio **Indirizzo**, è possibile inserire l'indirizzo delle attrezzature. Se non è inserito indirizzo nel cespite, il cespite utilizza l'indirizzo di un cespite padre, se il cespite padre dispone di un indirizzo. Se non c'è indirizzo associato al cespite o a un cespite padre nella gerarchia dei cespiti, l'indirizzo dell'unità funzionale in cui il cespite viene installato può essere utilizzato. Se l'unità funzionale non dispone di un indirizzo, l'indirizzo dell'unità funzionale padre viene utilizzato per il cespite.

## <a name="asset-management-plans"></a>Piani di manutenzione cespite

I piani di manutenzione vengono utilizzati per la programmazione dei processi di manutenzione preventiva a intervalli regolari relative al cespite. In questa Scheda dettaglio, è possibile impostare le righe del piano di manutenzione per il cespite selezionato. Cicli di manutenzione possono essere impostati per vari cespiti in cui è necessario eseguire una simile attività a intervalli regolari. Nella scheda **Piani di manutenzione unità funzionale**, si vedono i piani di manutenzione correlati alla unità funzionale in cui il cespite viene installato.

>[!NOTE]
>Se si elimina una riga del piano di manutenzione o un ciclo di manutenzione correlato a un cespite in **Tutti i cespiti**, vengono eliminati automaticamente tutti i programmi di manutenzione con stato "Creato" creati in base a quel piano o ciclo di manutenzione.

## <a name="functional-location-maintenance-plans"></a>Piani di manutenzione unità funzionale

In questa Scheda dettaglio si ottiene una panoramica dei piani di manutenzione correlati alla unità funzionale in cui il cespite viene installato.

## <a name="maintenance-rounds"></a>Cicli di manutenzione

In questa Scheda dettaglio, è possibile aggiungere o rimuovere i cicli di manutenzione relativi al cespite.

## <a name="financial-dimensions"></a>Dimensioni finanziarie

È possibile selezionare dimensioni finanziarie per il cespite.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]