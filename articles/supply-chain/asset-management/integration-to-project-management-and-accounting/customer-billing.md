---
title: Fattura per manutenzione su cespiti di proprietà del cliente
description: In questo articolo viene illustrato come creare, elaborare e fatturare il lavoro di manutenzione eseguito sui cespiti di proprietà dei clienti.
author: johanhoffmann
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjInvoiceTable, ProjProjectsListPage, ProjTable, EntAssetWorkOrderType, EntAssetWorkOrderProjectSetup, EntAssetObjectTable, EntAssetWorkOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c0d067ec4f2110b1c146ef0229b90e309578eaa7
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335077"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a>Fattura per manutenzione su cespiti di proprietà del cliente

[!include [banner](../../includes/banner.md)]

La funzionalità *Fatturazione ordini di lavoro* consente di creare, elaborare e fatturare il lavoro di manutenzione svolto sui cespiti di proprietà dei clienti. Questa funzionalità consente di svolgere le attività seguenti:

- Connetti i clienti ai cespiti di loro proprietà.
- Seleziona un cliente e visualizza i cespiti di cui è proprietario quando crei un ordine di lavoro.
- Configura un progetto padre per ogni cliente.
- Registrare ore, articoli, spese e commissioni a fronte dell'ordine di lavoro, quindi creare una proposta di fatturazione per il cliente in un secondo momento.

Inoltre, fornisce le seguenti funzionalità:

- Il contratto di progetto dal progetto padre di un cliente viene automaticamente copiato nel progetto dell'ordine di lavoro pertinente.
- La gestione dei cespiti può ora utilizzare il tipo di transazione di progetto *commissione* sia nelle previsioni degli ordini di lavoro che nei giornali di registrazione degli ordini di lavoro.

## <a name="turn-on-the-customer-billing-feature"></a>Attivare la funzionalità di fatturazione al cliente

Per poter utilizzare la funzionalità, è necessario attivarla per il sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione progetti e contabilità*
- **Nome funzionalità:** *Fatturazione ordini di lavoro*

## <a name="example-scenario"></a>Scenario di esempio

Per scoprire come funziona questa funzionalità, utilizza il seguente scenario di esempio.

Per elaborare lo scenario utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../../fin-ops-core/fin-ops/get-started/demo-data.md) standard. È necessario selezionare la persona giuridica **USMF** prima di iniziare.

È inoltre possibile utilizzare questo scenario come indicazioni per l'utilizzo di questa funzionalità quando si lavora su un sistema di produzione. Tuttavia, in questo caso, è necessario sostituire i propri valori e potrebbero mancare alcuni tipi di record richiesti forniti dai dati demo standard.

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a>Passaggio 1: creare un nuovo contratto di progetto per il cliente

1. Passare a **Gestione progetti e contabilità \> Progetti \> Contratti di progetto**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Nuovo contratto di progetto**, impostare i seguenti valori:

    - **Nome:** *Pelican Wholesales*
    - **Tipo di finanziamento:** *Cliente*
    - **Fonte di finanziamento:** *US-013* (*Pelican Wholesales*)

1. Selezionare **OK**.

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a>Passaggio 2: creare un nuovo progetto padre per il cliente

Il progetto padre creato qui verrà utilizzato quando vengono creati gli ordini di lavoro per il cliente.

1. Passare a **Gestione progetti e contabilità \> Progetti \> Tutti i progetti**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Nuovo progetto**, imposta i seguenti valori:

    - **Tipo di progetto**: *Tempistica e materiali*
    - **Nome progetto:** *Ordini di lavoro Pelican Wholesales*
    - **Gruppo di progetto**: *TM*
    - **ID contratto di progetto:** *Pelican Wholesales* (il contratto che hai creato in precedenza)
    - **Data di inizio:** selezionare la data odierna.

1. Selezionare **Crea progetto**.
1. Il nuovo progetto è aperto. Prendi nota del valore **ID progetto**. Dovrai inserirlo più tardi.

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a>Passaggio 3: creare un nuovo tipo di ordine di lavoro in Gestione cespiti

1. Passare a **Gestione cespiti \> Impostazione \> Ordini di lavoro \> Tipi di ordine di lavoro**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Un nuovo record viene aggiunto all'elenco. Impostare i seguenti valori per questo record:

    - **Tipo ordine di lavoro:** *Servizio*
    - **Nome:** *Ordini di lavoro di servizio*
    - **Stato del ciclo di vita ordine di lavoro:** *Standard*

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a>Passaggio 4: collegare l'account cliente al progetto padre

È ora necessario collegare l'account cliente al progetto padre nella configurazione del progetto in Gestione cespiti.

1. Passare a **Gestione cespiti \> Imposta \> Ordini di lavoro \> Impostazione progetto**.
1. Sulla scheda **Progetto padre**, seleziona e **Aggiungi** per aggiungere una riga.
1. Nella nuova riga, imposta i seguenti valori:

    - **Account cliente:** *US-013* (*Pelican Wholesales*)
    - **ID progetto:** immetti l'ID progetto della spedizione di cui hai preso nota in precedenza.

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a>Passaggio 5: collegare il tipo e il gruppo di progetto al progetto dell'ordine di lavoro

Dovresti essere ancora nella pagina **Impostazione progetto** (**Gestione cespiti \> Imposta \> Ordini di lavoro\> Impostazione progetto**).

1. Sulla scheda **Gruppo di progetto**, seleziona e **Aggiungi** per aggiungere una riga.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tipo di ordine di lavoro:** *Servizio* (il tipo di ordine di lavoro che hai creato in precedenza)
    - **Gruppo di progetto**: *TM*

> [!NOTE]
> Il contratto di progetto nel progetto dell'ordine di lavoro viene sempre ereditato dal progetto padre.

### <a name="step-6-link-an-asset-to-the-customer-id"></a>Passaggio 6: collegare un cespite all'ID cliente

1. Andare a **Gestione cespiti \> Cespiti \> Cespiti attivi.**
1. Nel campo **Filtro** campo, immetti *VE-102* e seleziona per filtrare per **Cespite**.
1. Seleziona la risorsa per aprire le sue impostazioni.
1. Nella Scheda dettaglio **Cliente**, imposta il campo **Conto cliente** su *US-013* (*Pelican Wholesales*).

    Il campo **Nome** viene aggiornato automaticamente su *Pelican Wholesales*.

### <a name="step-7-create-a-new-work-order-on-the-asset"></a>Passaggio 7: creare un nuovo ordine a fronte del cespite

1. Passare a **Gestione cespiti \> Ordini di lavoro \> Ordini di lavoro attivi**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine di lavoro**, imposta i seguenti valori:

    - **Tipo ordine di lavoro:** *Servizio*
    - **Descrizione:** *Riparazione camion*
    - **Account cliente:** *US-013* (*Pelican Wholesales*)
    - **Cespite:** *VE-102*

        > [!NOTE]
        > La ricerca mostra solo le risorse collegate all'account cliente selezionato.

    - **Tipo di processo di manutenzione:** *Riparazione*
    - **Commercio:** *Meccanico*
    - **Livello servizio:** *4*

1. Selezionare **OK**.

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a>Passaggio 8: rivedere l'ordine di lavoro e iniziare a lavorarci

In questa sezione lavorerai sull'ordine di lavoro che hai creato nella sezione precedente.

1. Segui questi passaggi per verificare che il progetto padre sia il progetto *Ordine di lavoro Pelican wholesales*:

    1. Nella sezione **Processi di manutenzione dell'ordine di lavoro**, seleziona una riga.
    1. Nella Scheda dettagli **Dettagli riga**, ispezionare il valore **ID progetto**. Dovrebbe essere un numero con trattino nel modulo *\<Parent-Project-ID\>-\<Project-ID\>*. Questo valore è un collegamento.
    1. Selezionare il collegamento ID progetto per aprire una pagina in cui è possibile visualizzare il progetto padre e i nomi del progetto.

1. Nella scheda **Ordine di lavoro** del riquadro azioni, nel gruppo **Stato del ciclo di vita**, selezionare **Aggiorna stato ordine di lavoro**.
1. Nella finestra di dialogo **Aggiorna stato ordine di lavoro**, nella colonna **Seleziona** selezionare la casella di controllo per la riga in cui il campo **Stato del ciclo di vita** è impostato su *In corso*.
1. Selezionare **OK**.
1. Nella finestra di dialogo **Stato del ciclo di vita: InProgress**, selezionare **OK**.

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a>Passaggio 9: registrare le ore impiegate per l'ordine di lavoro e creare una nuova proposta di fattura

In questa sezione continuerai a lavorare sull'ordine di lavoro su cui hai lavorato nella sezione precedente.

1. Nella scheda **Ordine di lavoro** del riquadro azioni, nel gruppo **Progetto** seleziona **Giornali di registrazione**.

    Viene visualizzata la pagina **Giornali di registrazione ordine di lavoro**. Qui puoi registrare il tempo che hai dedicato all'ordine di lavoro.

1. Nella Scheda dettaglio **Ore** selezionare **Aggiungi riga**.
1. Sulla nuova riga, imposta il campo **Ore** su *4*.
1. Nel riquadro azioni selezionare **Registra giornali**.
1. Chiudi la pagina **Giornali di registrazione ordine di lavoro** per tornare all'ordine di lavoro.
1. Nel riquadro azioni, nella scheda **Fatturazione**, selezionare **Nuova proposta di fatturazione**.
1. Nella finestra di dialogo **Crea proposta di fatturazione**, nella sezione **Transazioni di progetto** selezionare la casella di controllo **Seleziona** per ogni riga che si desidera fatturare.
1. Scegliere **OK** per chiudere la finestra di dialogo e visualizzare la nuova proposta di fatturazione.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]