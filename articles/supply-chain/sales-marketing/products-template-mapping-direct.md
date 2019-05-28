---
title: Sincronizzare prodotti direttamente da Finance and Operations con prodotti in Sales
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: feb9fbc066162e2caa9fc5dbaeec2c063ae23060
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572606"
---
# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a>Sincronizzare prodotti direttamente da Finance and Operations con prodotti in Sales

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrare i dati in Common Data Service per le app](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti direttamente da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Flusso di dati in Prospect to cash

La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Finance and Operations e Sales. I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Finance and Operations e Sales. La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Finance and Operations e Sales.

[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/dataintegration). Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.

Il modello e le attività sottostanti seguenti vengono utilizzati per sincronizzare i prodotti da Finance and Operations in Sales.

- **Nome del modello in Integrazione dati:** Prodotti (da Fin and Ops in Sales) - Diretto
- **Nome dell'attività nel progetto di Integrazione dati:** Prodotti

Nessuna attività di sincronizzazione è necessaria prima della sincronizzazione dei prodotti.

## <a name="entity-set"></a>Insieme di entità

| Finance and Operations     | Vendite    |
|----------------------------|----------|
| Prodotti rilasciati di vendita | Prodotti |

## <a name="entity-flow"></a>Flusso di entità

I prodotti vengono gestiti in Finance and Operations e sincronizzati in Sales. L'entità di dati **Prodotti rilasciati di vendita** in Finance and Operations esporta solo prodotti *vendibili*. I prodotti vendibili sono prodotti con le informazioni necessarie per essere utilizzati in un ordine cliente. Le stesse regole valgono quando un prodotto viene convalidato utilizzando la funzione **Convalida** nella pagina **Prodotto rilasciato**.

Il numero di prodotto viene utilizzato come una chiave. Pertanto, quando le varianti di prodotto vengono sincronizzate in Sales, ogni variante prodotto ha un singolo ID prodotto.

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

In Sales, un nuovo campo **Gestito esternamente** è stato aggiunto per i prodotti ad indicare che un determinato prodotto viene gestito esternamente. Per impostazione predefinita, il valore è impostato su **Sì** durante un'importazione in Sales. Sono disponibili i valori seguenti:

- **Sì** - Il prodotto deriva da Finance and Operations e non sarà modificabile in Sales.
- **No** - Il prodotto è stato immesso direttamente in Sales.
- **Vuoto** - Il prodotto esisteva in Sales prima che la soluzione Prospect to cash fosse abilitata.

Il campo **Gestito esternamente** garantisce che solo le offerte e gli ordini cliente con prodotti gestiti esternamente saranno sincronizzati con Finance and Operations.

I prodotti gestiti esternamente vengono aggiunti automaticamente al primo listino prezzi valido con la stessa valuta. I listini prezzi sono organizzati alfabeticamente per nome. Il prezzo di vendita di un prodotto da Finance and Operations viene utilizzato come prezzo nel listino prezzi. Di conseguenza, un listino prezzi deve esistere in Sales per ogni valuta di vendita prodotti in Finance and Operations. La valuta sui prodotti vendibili rilasciati viene impostata sulla valuta di contabilità nella persona giuridica da cui il prodotto viene esportato.

> [!NOTE]
> - La sincronizzazione del prodotto non riuscirà a meno che non sia presente un listino prezzi con una valuta corrispondente.
> - È possibile controllare il listino prezzi con l'integrazione mappando il pricelevelid.name [listino prezzi predefinito (nome)] nel progetto di integrazione dei dati. L'input deve essere in tutte lettere minuscole. Ad esempio, l'impostazione predefinita per un listino prezzi di vendita con il nome "standard" sarebbe: Campo di destinazione: pricelevelid.name [listino prezzi predefinito (nome)] e Tipo mappa: [ { "transformType": "Default", "defaultValue": "standard" } ].

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

- Prima di eseguire la prima sincronizzazione, è necessario compilare la tabella dei prodotti specifici per i prodotti esistenti in Finance and Operations. I prodotti esistenti non saranno sincronizzati fino al completamento del processo.

    1. In Finance and Operations utilizzare la ricerca per cercare **Compila tabella dei prodotti specifici**.
    2. Selezionare **Compila tabella dei prodotti specifici** per eseguire il processo. Questo processo deve essere eseguito una sola volta.

- Assicurarsi che la mappa dei valori richiesti per le unità di misura (UdM) di vendita tra Finance and Operations e Sales sia presente nel mapping di **SalesUnitSymbol** a **DefaultUnit (Name)**.
- Aggiornare la mappa di valori per **Gruppo unità** (**defaultuomscheduleid.name**), di modo che corrisponda a **Gruppi unità** in Sales.

    Il valore di modello predefinito è **Unità predefinita**.

- Assicurarsi che le UDM di vendita per tutti i prodotti da Finance and Operations esistano in Sales.
- Assicurarsi che i listini prezzi esistano in Sales per ogni valuta di vendita prodotti in Finance and Operations.
- Quando i prodotti vengono creati in Sales, possono avere lo stato **Bozza** o **Attivo**. Il comportamento è controllato in **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite** in Sales.

    I prodotti il cui stato è **Bozza** quando vengono creati devono essere attivati per poter essere aggiunti alle offerte o agli ordini cliente.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato un esempio di un modello di mapping in Integrazione dati. 

> [!NOTE]
> Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Finance and Operations.

![Mapping dei modelli nell'integratore di dati](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Argomenti correlati

[Prospect to cash](prospect-to-cash.md)

[Sincronizzare conti direttamente da Sales con clienti in Finance and Operations](accounts-template-mapping-direct.md)

[Sincronizzare contatti direttamente da Sales con contatti o clienti in Finance and Operations](contacts-template-mapping-direct.md)

[Sincronizzare intestazioni e righe di ordini di vendita direttamente da Finance and Operations in Sales](sales-order-template-mapping-direct-two-ways.md)

[Sincronizzare intestazioni e righe di fatture di vendita direttamente da Finance and Operations in Sales](sales-invoice-template-mapping-direct.md)



