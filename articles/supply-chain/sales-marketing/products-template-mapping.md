---
title: Sincronizzare i prodotti da Finance and Operations ai prodotti In Sales
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition a Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 063a20f133a00620bdf389b0a52a90bc61e2f7d4
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a>Sincronizzare i prodotti da Finance and Operations ai prodotti In Sales

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Prima di utilizzare la soluzione Prospect to cash, acquisisci familiarità con [Integrazione dei dati di Microsoft Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition a Microsoft Dynamics 365 for Sales.

## <a name="template-and-task"></a>Modello e attività

I seguenti modelli e le seguenti attività sottostanti vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) a Microsoft Dynamics 365 for Sales (Sales).

-   Nome del modello: Prodotti (Fin and Ops a Sales)

-   Nome dell'attività del progetto: Prodotti

Attività di sincronizzazione richieste prima di sincronizzare i prodotti: nessuna

## <a name="entity-set"></a>Insieme di entità

| **Finance and Operations** | **CDS** | **Vendite**  |
|----------------------------|---------|------------|
| Prodotti rilasciati di vendita | Prodotto | Prodotti   |

## <a name="entity-flow"></a>Flusso di entità

I prodotti vengono gestiti in Finance and Operations e sincronizzati con Sales. L'entità di dati **Prodotti rilasciati di vendita** in Finance and Operations esporta solo i prodotti che sono vendibili, ovvero i prodotti che hanno le informazioni necessarie per essere utilizzati in un ordine cliente. Le stesse regole valgono quando un prodotto viene convalidato con la funzione **Convalida** nella pagina **Prodotto rilasciato**.

Il **Numero prodotto** viene utilizzato come chiave. Ciò significa che le varianti di prodotto vengono sincronizzate in CDS e Sales con **ID prodotto** singoli per **Variante prodotto**.

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

In Sales viene aggiunto un nuovo campo nei prodotti **Gestito esternamente** per indicare che un determinato prodotto viene gestito esternamente. Il valore è impostato su **Sì** per impostazione predefinita durante l'importazione in Sales.

-   **Gestito esternamente = Sì**: il prodotto deriva da Finance and Operations e non sarà modificabile in Sales.

-   **Gestito esternamente = No**: il prodotto viene immesso direttamente in Sales.

-   **Gestito esternamente = vuoto**: il prodotto esisteva in Sales prima di abilitare la soluzione Prospect to cash.

Le informazioni di **Gestito esternamente** vengono utilizzate per garantire che solo **Quote** e **Ordini cliente** con **Prodotti gestiti esternamente** saranno sincronizzati in Finance and Operations.

I **Prodotti gestiti esternamente** vengono aggiunti automaticamente al primo **Listino prezzi** valido con la stessa valuta. Notare che il listino è organizzato alfabeticamente in base al **Nome**, Il prezzo di vendita di un prodotto da Finance and Operations viene utilizzato come prezzo nel **Listino prezzi**. Ciò significa che è necessario disporre di un **Listino prezzi** in Sales per ogni **Valuta di vendita di prodotti** in Finance and Operations. La valuta sui prodotti vendibili rilasciati viene impostata sulla valuta di contabilità nella persona giuridica da cui il prodotto viene esportato.

> [!NOTE]
> La sincronizzazione del prodotto non riuscirà senza un **Listino prezzi** con valuta corrispondente.

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

-   Prima di eseguire la primissima sincronizzazione, è necessario compilare la **Tabella dei prodotti specifici** per i prodotti esistenti in Finance and Operations. I prodotti esistenti non saranno sincronizzati fino al completamento del processo.

    -   In Finance and Operations utilizzare la ricerca per cercare **Compila tabella dei prodotti specifici**.

    -   Fare clic su **Compila tabella dei prodotti specifici** per eseguire il processo. Il processo deve essere eseguito una sola volta.

-   Assicurarsi che la **ValueMap** necessaria per l'**Unità di misura** (UDM) di vendita in Finance and Operations sia presente in **Origine -\> Mapping CDS SalesUnitSymbol/DefaultSellingUnitOfMeasure**.

-   Aggiornare **ID organizzazione CDS Organization_OrganizationId** in **Origine -\> CDS**.

    -   Il valore predefinito del modello è ORG001.

-   Aggiornare **ValueMap** per **Gruppo unità** (**defaultuomscheduleid.name**) in **CDS -\> destinazione** in modo che corrisponda **Gruppi unità** in Sales.

    -   Il valore predefinito del modello è **Unità predefinita**.

-   Assicurarsi che tutte le UDM di vendita dei prodotti da Finance and Operations esistano in Sales con il valore **Distinte di prelievo CDS**.

-   Assicurarsi che **Listini prezzi** sia presente in Sales per ogni valuta di vendita prodotti in Finance and Operations.

-   I prodotti possono essere creati in Sales con stato **Bozza** o **Attivo**. Tale opzione è controllata in **Impostazioni di sistema** in **Sales** in Sales.

    -   I prodotti creati con lo stato di bozza devono essere attivati prima di potere essere aggiunti a **Quota** o **Ordine cliente**.

## <a name="template-mapping-in-data-integrator"></a>Mapping dei modelli nell'integratore di dati

Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.

![Mapping dei modelli nell'integratore di dati](./media/products-template-mapping-data-integrator-1.png)

![Mapping dei modelli per prodotti nell'integratore di dati](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Argomenti correlati

[Sincronizzare conti da Sales a clienti in Finance and Operations](accounts-template-mapping.md)

[Sincronizzare contatti da Sales con contatti o clienti in Finance and Operations](contacts-template-mapping.md)

[Sincronizzare intestazioni e righe di offerte di vendita da Sales in Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizzare intestazioni e righe di ordini di vendita da Finance and Operations in Sales](sales-order-template-mapping.md)

[Sincronizzare intestazioni e righe di fatture di vendita da Finance and Operations in Sales](sales-invoice-template-mapping.md)


