---
title: Sincronizzare conti direttamente da Sales con clienti in Finance and Operations
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i conti da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: fb694db32638756328623c186594cf5ba2e7d6b8
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="synchronize-accounts-directly-from-sales-to-customers-in-finance-and-operations"></a>Sincronizzare conti direttamente da Sales con clienti in Finance and Operations

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrazione dati di Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i conti direttamente da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations.

## <a name="data-flow-in-prospect-to-cash"></a>Flusso di dati in Prospect to cash

La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Finance and Operations e Sales.  I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Finance and Operations e Sales. La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Finance and Operations e Sales.

[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/dataintegration). Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.

Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare i conti da Sales in Finance and Operations:

- **Nome del modello in Integrazione dati:** Conti (da Sales in Fin and Ops) - Diretto
- **Nome dell'attività del progetto:** Conti - Clienti

Nessuna attività di sincronizzazione è necessaria prima della sincronizzazione Conto/Cliente.

## <a name="entity-set"></a>Insieme di entità

| Vendite    | Finance and Operations |
|----------|------------------------|
| Conti | Clienti V2           |

## <a name="entity-flow"></a>Flusso di entità

I conti vengono gestiti in Sales e sincronizzati in Finance and Operations come clienti. La proprietà **Gestito esternamente** per tali clienti è impostata su **Sì** per tenere traccia dei clienti che hanno origine da Sales. Durante la fatturazione queste informazioni vengono utilizzate per filtrare le fatture che vengono sincronizzate in Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

Il campo **Numero di conto** è disponibile nella pagina **Conto**. È stata generata una chiave naturale e univoca per supportare l'integrazione. Questa funzionalità di chiave naturale della soluzione Customer Relationship Management (CRM) potrebbe influire sui clienti che utilizzano già il campo **Numero di conto**, ma che non utilizzano i valori univoci **Numero di conto** per conto. Attualmente la soluzione di integrazione non supporta questo caso.

Quando un nuovo conto viene creato, se un valore **Numero di conto** non è già presente, viene generato automaticamente utilizzando una sequenza numerica. Il valore consiste di **ACC**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri. Ecco un esempio: **ACC-01000-BVRCPS**

Quando viene applicata la soluzione di integrazione per Sales, uno script di aggiornamento imposta il campo **Numero di conto** per i conti esistenti in Sales. Se non sono presenti valori **Numero di conto**, viene utilizzata la sequenza numerica menzionata in precedenza.

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

- Il mapping **CustomerGroupId** deve essere aggiornato a un valore valido in Finance and Operations. È possibile specificare un valore predefinito oppure è possibile impostare il valore utilizzando una mappa di valori.

    Il valore del modello predefinito è **10**.

- Aggiungendo i seguenti mapping, è possibile consentire una riduzione del numero degli aggiornamenti manuali necessari in Finance and Operations. È possibile utilizzare un valore predefinito o una mappa di valori da, ad esempio, **Paese** o **Città**.

    - **SiteId** - Un sito è obbligatorio per la generazione di offerte e righe di ordine cliente in Finance and Operations. Un sito predefinito può essere preso sia dal prodotto che dall'intestazione ordine del cliente.

        Il valore del modello predefinito è **1**.

    - **WarehouseId** - Un magazzino è obbligatorio per l'elaborazione di offerte e righe di ordine cliente in Finance and Operations. Un sito predefinito può essere preso sia dal prodotto che dall'intestazione ordine del cliente in Finance and Operations.

        Il valore del modello predefinito è **13**.

    - **LanguageId** - Una lingua è obbligatoria per la generazione di offerte e ordini cliente in Finance and Operations. Per impostazione predefinita, viene utilizzata la lingua dell'intestazione ordine del cliente.

        Il valore di modello predefinito è **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

> [!NOTE]
> I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non vengono inclusi nei mapping predefiniti. Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.

Nelle figure seguenti viene illustrato un esempio di mapping di modelli in Integrazione dati. 

> [!NOTE]
> Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Finance and Operations.

![Mapping dei modelli in Integrazione dati](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>Argomenti correlati


[Prospect to cash](prospect-to-cash.md)

[Sincronizzare conti direttamente da Sales con clienti in Finance and Operations](accounts-template-mapping-direct.md)

[Sincronizzare contatti direttamente da Sales con contatti o clienti in Finance and Operations](contacts-template-mapping-direct.md)

[Sincronizzare intestazioni e righe di ordini di vendita direttamente da Finance and Operations in Sales](sales-order-template-mapping-direct-two-ways.md)

[Sincronizzare intestazioni e righe di fatture di vendita direttamente da Finance and Operations in Sales](sales-invoice-template-mapping-direct.md)


