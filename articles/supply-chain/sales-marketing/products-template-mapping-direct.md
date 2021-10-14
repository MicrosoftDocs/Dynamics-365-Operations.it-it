---
title: Sincronizzare prodotti direttamente da Supply Chain Management con prodotti in Sales
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti direttamente da Dynamics 365 Supply Chain Management in Dynamics 365 Sales.
author: Henrikan
ms.date: 06/10/2019
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
ms.openlocfilehash: d7aa4eddf8d6a18b8203785ddd3dca6ff8537067
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573443"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a>Sincronizzare prodotti direttamente da Supply Chain Management con prodotti in Sales

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrare i dati in Microsoft Dataverse per le app](/powerapps/administrator/data-integrator).

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti direttamente da Dynamics 365 Supply Chain Management in Dynamics 365 Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Flusso di dati in Prospect to cash

La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Supply Chain Management e Sales. I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Supply Chain Management e Sales. La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Supply Chain Management e Sales.

[![Flusso di dati in Prospect per uno scenario di liquidazione.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di Power Apps](https://admin.powerapps.com/dataintegration). Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.

Il modello e le attività sottostanti seguenti vengono utilizzati per sincronizzare i prodotti da Supply Chain Management in Sales.

- **Nome del modello in Integrazione dati:** Prodotti (da Supply Chain Management in Sales) - Diretto
- **Nome dell'attività nel progetto di Integrazione dati:** Prodotti

Nessuna attività di sincronizzazione è necessaria prima della sincronizzazione dei prodotti.

## <a name="entity-set"></a>Insieme di entità

| Gestione della supply chain    | Vendite    |
|----------------------------|----------|
| Prodotti rilasciati di vendita | Prodotti |

## <a name="entity-flow"></a>Flusso di entità

I prodotti vengono gestiti in Supply Chain Management e sincronizzati in Sales. L'entità di dati **Prodotti rilasciati di vendita** in Supply Chain Management esporta solo prodotti *vendibili*. I prodotti vendibili sono prodotti con le informazioni necessarie per essere utilizzati in un ordine cliente. Le stesse regole valgono quando un prodotto viene convalidato utilizzando la funzione **Convalida** nella pagina **Prodotto rilasciato**.

Il numero di prodotto viene utilizzato come una chiave. Pertanto, quando le varianti di prodotto vengono sincronizzate in Sales, ogni variante prodotto ha un singolo ID prodotto.

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

In Sales, un nuovo campo **Gestito esternamente** è stato aggiunto per i prodotti ad indicare che un determinato prodotto viene gestito esternamente. Per impostazione predefinita, il valore è impostato su **Sì** durante un'importazione in Sales. Sono disponibili i valori seguenti:

- **Sì** - Il prodotto deriva da Supply Chain Management e non sarà modificabile in Sales.
- **No** - Il prodotto è stato immesso direttamente in Sales.
- **Vuoto** - Il prodotto esisteva in Sales prima che la soluzione Prospect to cash fosse abilitata.

Il campo **Gestito esternamente** garantisce che solo le offerte e gli ordini cliente con prodotti gestiti esternamente saranno sincronizzati con Supply Chain Management.

I prodotti gestiti esternamente vengono aggiunti automaticamente al primo listino prezzi valido con la stessa valuta. I listini prezzi sono organizzati alfabeticamente per nome. Il prezzo di vendita di un prodotto da Supply Chain Management viene utilizzato come prezzo nel listino prezzi. Di conseguenza, un listino prezzi deve esistere in Sales per ogni valuta di vendita prodotti in Supply Chain Management. La valuta sui prodotti vendibili rilasciati viene impostata sulla valuta di contabilità nella persona giuridica da cui il prodotto viene esportato.

> [!NOTE]
> - La sincronizzazione del prodotto non riuscirà a meno che non sia presente un listino prezzi con una valuta corrispondente.
> - È possibile controllare il listino prezzi con l'integrazione mappando il pricelevelid.name [listino prezzi predefinito (nome)] nel progetto di integrazione dei dati. L'input deve essere in tutte lettere minuscole. Ad esempio, l'impostazione predefinita per un listino prezzi di vendita con il nome "standard" sarebbe: Campo di destinazione: pricelevelid.name [listino prezzi predefinito (nome)] e Tipo mappa: [ { "transformType": "Default", "defaultValue": "standard" } ].

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

- Prima di eseguire la prima sincronizzazione, è necessario compilare la tabella dei prodotti specifici per i prodotti esistenti in Supply Chain Management. I prodotti esistenti non saranno sincronizzati fino al completamento del processo.

    1. In Supply Chain Management utilizzare la ricerca per cercare **Compila tabella dei prodotti specifici**.
    2. Selezionare **Compila tabella dei prodotti specifici** per eseguire il processo. Questo processo deve essere eseguito una sola volta.

- Assicurarsi che la mappa dei valori richiesti per le unità di misura (UdM) di vendita tra Supply Chain Management e Sales sia presente nel mapping di **SalesUnitSymbol** a **DefaultUnit (Name)**.
- Aggiornare la mappa di valori per **Gruppo unità** (**defaultuomscheduleid.name**), di modo che corrisponda a **Gruppi unità** in Sales.

    Il valore di modello predefinito è **Unità predefinita**.

- Assicurarsi che le UDM di vendita per tutti i prodotti da Supply Chain Management esistano in Sales.
- Assicurarsi che i listini prezzi esistano in Sales per ogni valuta di vendita prodotti in Supply Chain Management.
- Quando i prodotti vengono creati in Sales, possono avere lo stato **Bozza** o **Attivo**. Il comportamento è controllato in **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite** in Sales.

    I prodotti il cui stato è **Bozza** quando vengono creati devono essere attivati per poter essere aggiunti alle offerte o agli ordini cliente.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato un esempio di un modello di mapping in Integrazione dati. 

> [!NOTE]
> Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Supply Chain Management.

![Mapping dei modelli nell'integratore di dati.](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Argomenti correlati

[Prospect per uno scenario di liquidazione](prospect-to-cash.md)

[Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management](accounts-template-mapping-direct.md)

[Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management](contacts-template-mapping-direct.md)

[Sincronizzazione degli ordini cliente direttamente tra Sales e Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Sincronizzare intestazioni e righe di fatture di vendita direttamente da Supply Chain Management in Sales](sales-invoice-template-mapping-direct.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]