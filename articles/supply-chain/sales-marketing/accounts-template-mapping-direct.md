---
title: Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i conti da Dynamics 365 Sales in Supply Chain Management.
author: Henrikan
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: f6f5662427be92ad57def2af772dd69abd575b81
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566505"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a>Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrare i dati in Microsoft Dataverse per le app](/powerapps/administrator/data-integrator).

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i conti direttamente da Dynamics 365 Sales in Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Flusso di dati in Prospect to cash

La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Supply Chain Management e Sales.  I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Supply Chain Management e Sales. La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Supply Chain Management e Sales.

[![Flusso di dati in Prospect per uno scenario di liquidazione.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di Power Apps](https://preview.admin.powerapps.com/dataintegration). Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.

Il modello e l'attività sottostanti seguenti vengono utilizzati per sincronizzare i conti da Sales in Supply Chain Management.

- **Nome del modello in Integrazione dati:** Conti (da Sales in Fin and Ops) - Diretto
- **Nome dell'attività del progetto:** Conti - Clienti

Nessuna attività di sincronizzazione è necessaria prima della sincronizzazione Conto/Cliente.

## <a name="entity-set"></a>Insieme di entità

| Vendite    | Gestione della supply chain |
|----------|------------------------|
| Account | Clienti V2           |

## <a name="entity-flow"></a>Flusso di entità

I conti vengono gestiti in Sales e sincronizzati in Supply Chain Management come clienti. La proprietà **Gestito esternamente** per tali clienti è impostata su **Sì** per tenere traccia dei clienti che hanno origine da Sales. Durante la fatturazione queste informazioni vengono utilizzate per filtrare le fatture che vengono sincronizzate in Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

La colonna **Numero di conto** è disponibile nella pagina **Conto**. È stata generata una chiave naturale e univoca per supportare l'integrazione. Questa funzionalità di chiave naturale della soluzione Customer Relationship Management (CRM) potrebbe influire sui clienti che utilizzano già la colonna **Numero di conto**, ma che non utilizzano i valori univoci **Numero di conto** per conto. Attualmente la soluzione di integrazione non supporta questo caso.

Quando un nuovo conto viene creato, se un valore **Numero di conto** non è già presente, viene generato automaticamente utilizzando una sequenza numerica. Il valore consiste di **ACC**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri. Ecco un esempio: **ACC-01000-BVRCPS**

Quando viene applicata la soluzione di integrazione per Sales, uno script di aggiornamento imposta la colonna **Numero di conto** per i conti esistenti in Sales. Se non sono presenti valori **Numero di conto**, viene utilizzata la sequenza numerica menzionata in precedenza.

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

- Il mapping **CustomerGroupId** deve essere aggiornato a un valore valido in Supply Chain Management. È possibile specificare un valore predefinito oppure è possibile impostare il valore utilizzando una mappa di valori.

    Il valore del modello predefinito è **10**.

- Aggiungendo i seguenti mapping, è possibile consentire una riduzione del numero degli aggiornamenti manuali necessari in Supply Chain Management. È possibile utilizzare un valore predefinito o una mappa di valori da, ad esempio, **Paese** o **Città**.

    - **SiteId** - Un sito è obbligatorio per la generazione di offerte e righe di ordine cliente in Supply Chain Management. Un sito predefinito può essere preso sia dal prodotto che dall'intestazione ordine del cliente.

        Il valore del modello predefinito è **1**.

    - **WarehouseId** - Un magazzino è obbligatorio per l'elaborazione di offerte e righe di ordine cliente in Supply Chain Management. Un sito predefinito può essere preso sia dal prodotto che dall'intestazione ordine del cliente in Supply Chain Management.

        Il valore del modello predefinito è **13**.

    - **LanguageId** - Una lingua è obbligatoria per la generazione di offerte e ordini cliente in Supply Chain Management. Per impostazione predefinita, viene utilizzata la lingua dell'intestazione ordine del cliente.

        Il valore di modello predefinito è **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

> [!NOTE]
> Le colonne **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non vengono inclusi nei mapping predefiniti. Per mappare queste colonne, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui la tabella viene sincronizzata.

Nelle figure seguenti viene illustrato un esempio di mapping di modelli in Integrazione dati. 

> [!NOTE]
> Il mapping mostra quali informazioni sulle colonne verranno sincronizzate da Sales in Supply Chain Management.

![Mapping modello in Integrazione dati.](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>Argomenti correlati


[Prospect per uno scenario di liquidazione](prospect-to-cash.md)

[Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management](accounts-template-mapping-direct.md)

[Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management](contacts-template-mapping-direct.md)

[Sincronizzazione degli ordini cliente direttamente tra Sales e Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Sincronizzare intestazioni e righe di fatture di vendita direttamente da Supply Chain Management in Sales](sales-invoice-template-mapping-direct.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]