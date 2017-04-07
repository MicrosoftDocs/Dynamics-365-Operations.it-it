---
title: Importa tassi di cambio valutari
description: "Se una persona giuridica ha ricevuto le fatture in valuta estera, è necessario convertire la valuta estera nella valuta locale. Ciò significa che i tassi di cambio aggiornati per le valute diverse richiesti. In questo argomento viene fornita una panoramica delle impostazioni e richieste di elaborazione per includere i tassi di cambio estero rilasciati su Internet dai fornitori del tasso di cambio, ad esempio la banca centrale europea e la banca centrale in Russia."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf66a1b1c9314b454223274810a21913d54b702d
ms.lasthandoff: 03/31/2017


---

# <a name="import-currency-exchange-rates"></a>Importa tassi di cambio valutari

Se una persona giuridica ha ricevuto le fatture in valuta estera, è necessario convertire la valuta estera nella valuta locale. Ciò significa che i tassi di cambio aggiornati per le valute diverse richiesti. In questo argomento viene fornita una panoramica delle impostazioni e richieste di elaborazione per includere i tassi di cambio estero rilasciati su Internet dai fornitori del tasso di cambio, ad esempio la banca centrale europea e la banca centrale in Russia.

Nelle sezioni seguenti viene descritto il flusso di informazioni utilizzato per l'impostazione e l'elaborazione di importazione dei tassi di cambio estero.

## <a name="configure-an-exchange-rate-provider"></a>Configurare un fornitore del tasso di cambio
Prima di importare i tassi di cambio, è necessario impostare le informazioni richieste dai fornitori con regimi i tassi di cambio. Utilizzare ** configurare i fornitori del tasso di cambio ** la finestra per selezionare i fornitori del tasso di cambio. Alcuni fornitori del tasso di cambio vengono inclusi nei dati dimostrativi in Microsoft Dynamics 365 per le operazioni. Nella tabella seguente vengono fornite le descrizioni relative ai controlli presenti in questa pagina.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field** | **Description**                                                                                                                                                                                                             |
| **Name**  | Nome del provider di tassi di cambio.                                                                                                                                                                                     |
| ** Chiave **   | Identificatore univoco per ogni informazione di configurazione richiesta dal provider. Queste informazioni vengono aggiunte automaticamente per ciascun fornitore del tasso di cambio aggiunti quando si fa clic su ** aggiungere ** il pulsante. |
| **Value** | Informazioni per ogni chiave. Queste informazioni vengono aggiunti per ciascun fornitore del tasso di cambio aggiunti quando si fa clic su ** aggiungere ** il pulsante.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importa tassi di cambio valutari
È possibile importare i tassi di cambio dall'origine dei fornitori del tasso di cambio vengono impostate su ** tassi di cambio ** nella pagina. Utilizzare ** importare i tassi di cambio ** la pagina per includere i tassi di cambio. Nella tabella seguente vengono descritti i campi necessari per completare correttamente il processo di importazione.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field**                              | **Description**                                                                                                                                                                                                                                                                                                                                                             |
| **Exchange rate type**                 | Un tipo di tasso di cambio.                                                                                                                                                                                                                                                                                                                                                      |
| **Exchange rate provider**             | Provider del tasso di cambio.                                                                                                                                                                                                                                                                                                                                                  |
| **Import as of**                       | Questo parametro se si desidera includere gestisce a partire dalla data corrente o per un intervallo di date. Se si desidera utilizzare un intervallo di date, immettere o selezionare le date di inizio e di fine.                                                                                                                                                                                                                |
| **Create necessary currency pairs**    | Questa casella di controllo gestisce la creazione automatica di coppie di valuta, se coppie di valute incluse non sono disponibili. Questa opzione non sia disponibile per i fornitori.                                                                                                                                                                                               |
| **Override existing exchange rates**   | Questa casella di controllo gestisce l'aggiornamento del tasso di cambio corrente di una coppia di valute quando il tasso di cambio per una data specifica è già presente. Se non si seleziona questa casella di controllo, il tasso di cambio per date specifiche non viene incluso se un altro tasso di cambio già esistente.                                                                                       |
| **Prevent import on national holiday** | Questa casella di controllo gestisce l'importazione del tasso di cambio per una data che precede un giorno festivo. Ad esempio, se si seleziona questa casella di controllo e si utilizza la banca centrale europea come fornitore del tasso di cambio, il sistema non aggiornerà il tasso di cambio su un giorno festivo correlata alla persona giuridica corrente. Questa opzione non sia disponibile per i fornitori. |




