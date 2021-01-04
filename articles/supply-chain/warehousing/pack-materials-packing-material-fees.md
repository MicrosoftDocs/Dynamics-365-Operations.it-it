---
title: Materiali di imballaggio e addebiti
description: Questo argomento fornisce informazioni sugli addebiti per materiale di imballaggio che vengono effettuati alle società di riciclaggio a intervalli specifici.
author: MarkusFogelberg
manager: tfehr
ms.date: 02/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2020-02-19
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1061f336701461df7a2cf78661788e4c6100c84d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431032"
---
# <a name="packing-materials-and-fees"></a>Materiali di imballaggio e addebiti

[!include [banner](../includes/banner.md)]

Gli addebiti relativi al materiale di imballaggio vengono pagati a una società di riciclaggio a specifici intervalli. Per ciascun materiale di cui si compone un'unità di imballaggio viene pagato un importo per unità di peso. Sebbene questi addebiti vengono calcolati e inclusi in un report, non vengono registrate transazioni contabili in quanto gli addebiti relativi al materiale di imballaggio non sono considerati come imposte da pagare a un ufficio tributario.

I pesi e gli addebiti relativi al materiale di imballaggio vengono calcolati per le righe degli ordini fornitore e cliente.

È possibile definire una o più unità di imballaggio per un singolo articolo, un gruppo di articoli (gruppo di imballaggio) o tutti gli articoli. Un'unità di imballaggio si compone di materiali di imballaggio e dei relativi pesi, oltre che del numero di articoli inclusi nell'unità. Un codice materiale di imballaggio viene assegnato a ciascun tipo di materiale di imballaggio definito. In base al codice materiale di imballaggio, è possibile specificare un prezzo per un periodo specifico. Gli addebiti relativi al materiale di imballaggio vengono calcolati in base a tali informazioni.

> [!NOTE]
> Anche se la società non effettua pagamenti per addebiti relativi al materiale di imballaggio, è possibile utilizzare questa funzionalità per calcolare statistiche relative ai pesi per il materiale di imballaggio.

## <a name="set-up-packing-material-allocation"></a><a name="allocations"></a>Impostare l'allocazione del materiale di imballaggio

Prima di poter calcolare i pesi del materiale di imballaggio, i costi del materiale di imballaggio o entrambi, è necessario attivare il calcolo e definire quali materiali e costi si applicano a quali articoli.

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione articoli e magazzino**.
1. Nella scheda **Generale** della sezione **Materiale di imballaggio**, impostare l'opzione **Calcola addebiti materiale di imballaggio** su **Sì**.
1. Andare a **Gestione inventario \> Impostazione \> Materiale di imballaggio \> Gruppi di imballaggio** e creare tutti i gruppi di imballaggio utilizzati. Tutti gli articoli in un gruppo di imballaggio utilizzeranno la stessa allocazione del materiale di imballaggio. Se non si utilizzano i gruppi di imballaggio, è possibile saltare questo passaggio.

    > [!TIP]
    > Dopo aver creato i gruppi di imballaggio, è possibile assegnare un gruppo a ciascun prodotto come richiesto. Andare a **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**, selezionare un prodotto, quindi nella scheda dettaglio **Gestione articoli**, nel campo **Gruppo di imballaggio**, selezionare il gruppo di imballaggio appropriato.

1. Andare a **Gestione scorte \> Impostazione \> Materiale di imballaggio \> Codici dei materiali di imballaggio**, definire ogni tipo di materiale di imballaggio utilizzato e specificare l'unità in cui il materiale di imballaggio viene utilizzato durante la preparazione delle spedizioni.
1. Andare a **Gestione scorte \> Impostazione \> Materiale di imballaggio \> Addebiti materiale di imballaggio** e impostare un costo per ogni tipo di materiale di imballaggio appena definito. I costi vengono calcolati in base al prezzo per unità utilizzata.
1. Per allocare i materiali di imballaggio agli articoli, andare a **Gestione scorte \> Impostazione \> Materiale di imballaggio \> Allocazione materiale di imballaggio** e creare le allocazioni. È possibile creare il numero di allocazioni ritenuto necessario. È possibile allocare i materiali di imballaggio per singoli articoli, gruppi di articoli (gruppi di imballaggio) o tutti gli articoli, a seconda di quanto dettagliate devono essere le allocazioni.

    Per ciascuna allocazione create, effettuare le operazioni seguenti.

    1. Nella scheda dettaglio **Generale**, impostare i seguenti campi:

        - **Codice articolo** - Selezionare l'ambito dell'allocazione:

            - **Tabella** - Creare un'allocazione per un singolo articolo specifico.
            - **Gruppo** - Creare un'allocazione per tutti gli articoli che appartengono a un gruppo di imballaggio definito nella pagina **Gruppi di imballaggio**.
            - **Tutti** - Creare un'allocazione per tutti gli articoli.

            > [!NOTE]
            > Di solito, tutte le allocazioni sono create allo stesso livello (**Tabella**, **Gruppo** o **Tutti**). Se si utilizza più di un livello, verrà utilizzata l'allocazione specifica più corrispondente per ciascun articolo. (Il livello **Tabella** è prioritario rispetto al livello **Gruppo** ed entrambi i livelli sono prioritari rispetto al livello **Tutti**.)

        - **Relazione articolo** - Se si sta eseguendo l'allocazione per un singolo articolo, selezionare l'articolo. Se si sta eseguendo l'allocazione per un gruppo di articoli, selezionare il gruppo di imballaggio. Se si sta eseguendo l'allocazione per tutti gli articoli, lasciare vuoto questo campo.
        - **Configurazione**, **Dimensioni**, **Colore** e **Stile** - Immettere i valori per queste dimensioni come richiesto, per definire ulteriormente l'articolo per cui si effettua l'allocazione.
        - **Unità di imballaggio** - Selezionare l'unità in cui l'articolo viene imballato quando viene utilizzato il materiale di imballaggio. Questa unità potrebbe differire dall'unità in cui l'articolo è stato acquistato e immagazzinato.
        - **Fattore unità di imballaggio** - Immettere il fattore di conversione utilizzato per convertire dall'unità di magazzino all'unità di imballaggio. (La conversione utilizza la formula *Unità di imballaggio* = *Unità articolo* × *Fattore unità di imballaggio* .)

    1. Nella scheda dettaglio **Materiale di imballaggio**, aggiungere una riga per ogni pezzo di materiale da imballaggio necessario per l'allocazione corrente. Su ogni riga, specificare il tipo di materiale (come definito nella pagina **Codici materiale di imballaggio**) e la quantità di materiale che viene consumata per ogni unità spedita dell'articolo corrente.

## <a name="packing-units-on-sales-order-lines"></a>Unità di imballaggio nelle righe ordine cliente

Dopo aver [attivato il calcolo per gli addebiti dei materiali di imballaggio e impostato le allocazioni](#allocations), il sistema verifica che vengano specificate le unità di imballaggio per ciascun articolo aggiunto a un ordine cliente. Quindi calcola eventuali addebiti necessari. Quando un articolo viene aggiunto a un ordine cliente, si verifica una delle seguenti fasi:

- **Se un'allocazione di materiale imballaggio si applica all'articolo:** il sistema aggiorna la riga ordine cliente con l'unità di imballaggio e la quantità di unità di imballaggio specificate. (La quantità di unità di imballaggio viene calcolata in base formula *Quantità unità di imballaggio* = *Quantità ordinata* ÷ *Numero di articoli nell'unità di imballaggio selezionata*.)
- **Se nessuna allocazione di materiale di imballaggio si applica all'articolo:** è possibile immettere manualmente un'unità e una quantità di unità di imballaggio nella riga ordine cliente.

È inoltre possibile modificare l'unità di imballaggio e la quantità di unità di imballaggio quando si registra la riga ordine cliente. Questa capacità è importante se la riga ordine cliente viene consegnata o fatturata solo parzialmente.

Quando si fattura l'ordine cliente, il sistema crea le transazioni per materiale di imballaggio. Le transazioni per materiale di imballaggio contengono i pesi del materiale di imballaggio della riga di vendita. È possibile modificare le transazioni dopo averle fatturate. È possibile quindi creare nuove transazioni.

## <a name="packing-units-on-purchase-order-lines"></a>Unità di imballaggio nelle righe ordine fornitore

Il sistema non crea le transazioni per materiale di imballaggio per le righe ordine fornitore. È necessario creare manualmente le transazioni per le righe ordine fornitore fatturate nella pagina **Transazioni materiale di imballaggio**.

## <a name="set-up-license-numbers-for-customers-that-are-charged-packing-material-fees"></a>Impostare i numeri di licenza per i clienti a cui vengono addebitati i costi del materiale di imballaggio

Se gli ordini cliente per un cliente specifico devono includere gli addebiti per i materiali di imballaggio utilizzati per ciascun ordine, attenersi alla seguente procedura.

1. Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**.
1. Selezionare il cliente a cui devono essere addebitati i materiali di imballaggio.
1. Nella scheda dettaglio **Fattura e consegna**, impostare i seguenti campi:

    - Nella sezione **IVA** nel campo **Numero di licenza imposta sull'imballaggio**, inserire il numero di licenza dell'azienda.
    - Nella sezione **Addebito materiale di imballaggio** nel campo **Numero licenza**, inserire il numero di licenza dell'azienda.

Ora, quando si crea e si fattura un ordine cliente che include uno o più articoli che utilizzano materiali di imballaggio, la fattura mostrerà gli addebiti del materiale di imballaggio.

Per i clienti che non devono pagare i costi del materiale di imballaggio, seguire questi stessi passaggi, ma cancellare i numeri di licenza dai campi **Numero di licenza imposta sull'imballaggio** e **Numero licenza**. Le fatture per i clienti che non pagano i costi del materiale di imballaggio mostrano i pesi dei materiali di imballaggio, ma non gli addebiti.

Per generare un report che mostri tutti gli addebiti del materiale di imballaggio che l'azienda dovrà sostenere per un periodo specifico, andare a **Gestione scorte \> Numero di licenza imposta sull'imballaggio \> Report materiali di imballaggio \> Calcolo addebito materiale di imballaggio**, specificare un intervallo di date, quindi selezionare **OK**.

## <a name="print-packing-material-weights-on-invoices"></a>Stampare i pesi del materiale di imballaggio sulle fatture

È possibile stampare i pesi del materiale di imballaggio su una fattura e indicare chi assolve agli addebiti correlati. I pesi vengono riepilogati per codice di imballaggio.

1. Andare a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.
1. Nella scheda **Aggiornamenti** nella scheda dettaglio **Fattura**, impostare l'opzione **Stampa peso materiale di imballaggio** su **Sì**.
