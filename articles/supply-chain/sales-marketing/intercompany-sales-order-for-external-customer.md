---
title: Creare e fatturare un ordine cliente interaziendale per un cliente esterno
description: In questo articolo viene illustrato come creare e fatturare un ordine cliente interaziendale per uso esterno
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: cd42551730ab0123813a3b5a0b5a4b1c334e9d30
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852159"
---
# <a name="create-and-invoice-an-intercompany-sales-order-for-an-external-customer"></a>Creare e fatturare un ordine cliente interaziendale per un cliente esterno

[!include [banner](../../includes/banner.md)]

È possibile utilizzare il commercio interaziendale per registrare la vendita di un prodotto da una persona giuridica a un'altra persona giuridica appartenente alla stessa organizzazione.

Quando si crea l'ordine cliente originario, è possibile creare automaticamente un ordine fornitore interaziendale per il fornitore interaziendale. Un ordine cliente interaziendale viene automaticamente creato nella persona giuridica del fornitore interaziendale.

Nella figura seguente è illustrato il flusso delle transazioni quando si crea un ordine cliente per un cliente esterno, ma il prodotto deve essere ordinato da una persona giuridica diversa dell'organizzazione prima che sia possibile consegnare il prodotto al cliente. In questo caso, un ordine fornitore interaziendale viene creato per il conto fornitore che rappresenta l'altra persona giuridica. A sua volta, un ordine cliente interaziendale viene creato nell'altra persona giuridica per il conto cliente che rappresenta la propria persona giuridica. Quando si emette la fattura di un ordine fornitore interaziendale, viene automaticamente registrata la fattura dell'ordine cliente originario se si tratta di una consegna diretta.

![Processo di vendita esterna interaziendale](media/intercompanyexternalsalesprocess.png)

Se si utilizza la consegna diretta e si seleziona **Documento di trasporto** nel campo **Quantità** della pagina **Registrazione fattura**, la fattura fornitore interaziendale sarà basata sull'entrata prodotti interaziendale registrata in precedenza.

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, assicurarsi che i seguenti prerequisiti siano soddisfatti per registrare e stampare automaticamente le fatture interaziendali.

1. Vai a **Vendite e marketing \> Clienti \> Tutti i clienti**.
1. Nel riquadro azioni, sella scheda **Generale**, selezionare **Interaziendale**.
1. Andare ad **Approvvigionamento \> Fornitori \> Tutti i fornitori**.
1. Nel riquadro azioni, sella scheda **Generale**, selezionare **Interaziendale**.
1. Nella pagina **Interaziendale** per il venditore o il cliente, nell'area **Criteri ordine fornitore**, nel gruppo di campi **Ordine fornitore interaziendale (consegna diretta)**, selezionare la casella di controllo **Registra fattura automaticamente**.
1. Nell'area **Criteri ordine fornitore**, nel gruppo di campi **Ordine cliente originario (consegna diretta)**, selezionare la casella di controllo **Registra fattura automaticamente**. Selezionare questa casella di controllo se si desidera stampare automaticamente la fattura ordine cliente originario quando si registra la fattura fornitore interaziendale.

> [!NOTE]
> Le impostazioni di stampa per la fattura sono determinate dall'impostazione del modulo, del documento o della transazione nella pagina **Impostazione Gestione stampa**.

## <a name="create-an-original-sales-order-for-an-external-customer"></a>Creare un ordine cliente originario per un cliente esterno

Completare questi passaggi nella persona giuridica A. Questa procedura corrisponde alla casella contrassegnata con 1 nell'illustrazione.

1. Andare a **Contabilità clienti \> Ordini cliente \> Tutti gli ordini cliente**.
1. Dalla pagina elenco **Tutti gli ordini cliente**, creare l'ordine cliente originario. I valori dei campi vengono copiati dal conto cliente all'ordine cliente.
1. Nella pagina **Ordine cliente**, selezionare **Visualizzazione intestazione** sul riquadro Azioni.
1. Sulla Scheda dettaglio **Impostazioni interaziendali**, selezionare la casella di controllo **Crea automaticamente ordini interaziendali**.
1. Se si desidera che il fornitore interaziendale consegni l'articolo direttamente al cliente esterno, selezionare la casella di controllo **Consegna diretta**.
1. Al termine dell'immissione dell'ordine cliente, chiudere la pagina **Ordine cliente**.

L'ordine fornitore interaziendale viene creato automaticamente per tutti gli articoli assegnati a un fornitore interaziendale, quindi viene creato l'ordine cliente interaziendale. In un messaggio informativo è indicato che sono stati creati un ordine fornitore interaziendale e un ordine cliente interaziendale e vengono forniti i collegamenti a tali ordini. Se un articolo non è stato trovato, viene visualizzato un avviso rosso che indica che il processo di creazione dell'ordine non è stato completato.

> [!NOTE]
> Se si stanno creando più ordini in persone giuridiche diverse e in una delle persone giuridiche gli articoli non sono stati trovati, il processo di creazione degli ordini viene interrotto anche per le persone giuridiche in grado di completare i propri ordini.

## <a name="invoice-an-intercompany-sales-order"></a>Fatturare un ordine cliente interaziendale

Quando si fattura un ordine cliente interaziendale, l'ordine fornitore interaziendale corrispondente viene fatturato automaticamente. Quindi, se l'ordine cliente originario è un ordine di consegna diretta, l'ordine cliente originario viene automaticamente fatturato.

Completare questi passaggi nella persona giuridica B. Questa procedura corrisponde alla casella contrassegnata con 2 nell'illustrazione.

1. Andare a **Contabilità clienti \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nella pagina elenco **Tutti gli ordini cliente**, selezionare l'ordine cliente interaziendale.
1. Nel riquadro Azioni, selezionare la scheda **Fattura**, quindi selezionare **Fattura**.
1. Selezionare la casella di controllo **Registrazione**.
1. Selezionare l'ordine cliente, quindi selezionare **OK**.

La fattura cliente per l'ordine cliente interaziendale viene registrata automaticamente nella persona giuridica B. La fattura fornitore interaziendale quindi verrà creata automaticamente e registrata nella persona giuridica A. Se l'ordine cliente originario è impostato come consegna diretta, la fattura cliente viene creata per l'ordine cliente originario nella persona giuridica A.

> [!NOTE]
> In precedenza, per gli scenari di vendita interaziendale, se il flusso di lavoro della fattura fornitore era configurato nella società acquirente interaziendale, l'ordine cliente interaziendale non poteva essere fatturato correttamente. Pertanto, è stato necessario disattivare il flusso di lavoro della fattura fornitore per la società acquirente interaziendale. 
> 
> Questa limitazione è stata corretta da una recente funzionalità nella versione 10.0.25. Gli ordini cliente interaziendali ora possono essere fatturati quando il flusso di lavoro della fattura fornitore è configurato nella società acquirente interaziendale.
> 
> Per abilitare questa funzionalità segui la procedura seguente.
>
> 1. Seleziona la persona giuridica di vendite interaziendale.  
> 2. Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**.
> 3. Selezionare il cliente per la società acquirente interaziendale.
> 4. Vai a **Generale\> Imposta \> Interaziendale**.
> 5. Nella scheda **Criteri ordine fornitore**, seleziona il parametro **Ignora flusso di lavoro per le fatture fornitore interaziendali**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
