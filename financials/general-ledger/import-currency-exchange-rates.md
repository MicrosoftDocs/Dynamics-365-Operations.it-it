---
title: Importa tassi di cambio valutari
description: "Se una persona giuridica ha ricevuto fatture in valuta estera, è necessario convertire la valuta estera in quella locale. Ciò significa che è necessario conoscere i tassi di cambio aggiornati per le diverse valute. In questo argomento viene fornita una panoramica delle impostazioni richieste e dell'elaborazione per importare i tassi di cambio estero pubblicati su Internet dai provider dei tassi di cambio, ad esempio la Banca Centrale Europea e la Banca Centrale di Russia."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 2d0654d6dbed3b4fe56b8918194132787f66af80
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017

---

# <a name="import-currency-exchange-rates"></a>Importa tassi di cambio valutari

[!include[banner](../includes/banner.md)]


Se una persona giuridica ha ricevuto fatture in valuta estera, è necessario convertire la valuta estera in quella locale. Ciò significa che è necessario conoscere i tassi di cambio aggiornati per le diverse valute. In questo argomento viene fornita una panoramica delle impostazioni richieste e dell'elaborazione per importare i tassi di cambio estero pubblicati su Internet dai provider dei tassi di cambio, ad esempio la Banca Centrale Europea e la Banca Centrale di Russia.

Nelle sezioni seguenti viene descritto il flusso di informazioni utilizzato per impostare ed elaborare l'importazione dei tassi di cambio estero.

## <a name="configure-an-exchange-rate-provider"></a>Configurare un provider di tassi di cambio
Prima di poter importare i tassi di cambio, è necessario impostare le informazioni richieste dai provider di tassi di cambio. Utilizzare la pagina **Configura provider di tassi di cambio** per selezionare i provider di tassi di cambio. Alcuni provider di tassi di cambio sono inclusi nei dati dimostrativi in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Nella tabella riportata di seguito sono incluse le descrizioni relative ai controlli presenti nella pagina.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Campo** | **Descrizione**                                                                                                                                                                                                             |
| **Nome**  | Nome del provider di tassi di cambio.                                                                                                                                                                                     |
| **Chiave**   | Identificatore univoco per ogni informazione di configurazione richiesta dal provider. Queste informazioni vengono aggiunte automaticamente per ogni provider di tassi di cambio che si aggiunge quando si fa clic sul pulsante **Aggiungi**. |
| **Valore** | Informazioni per ogni chiave. Queste informazioni vengono aggiunte per ogni provider di tassi di cambio che si aggiunge quando si fa clic sul pulsante **Aggiungi**.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importa tassi di cambio valutari
È possibile importare i tassi di cambio dall'origine dei provider di tassi di cambio e impostarli nella pagina **Tassi di cambio valutario**. Utilizzare la pagina **Importa tassi di cambio valutari** per importare i tassi di cambio. Nella tabella seguente vengono descritti i campi necessari per completare correttamente il processo di importazione.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Campo**                              | **Descrizione**                                                                                                                                                                                                                                                                                                                                                             |
| **Tipo di tasso di cambio**                 | Tipo di tasso di cambio.                                                                                                                                                                                                                                                                                                                                                      |
| **Provider di tassi di cambio**             | Provider di tassi di cambio.                                                                                                                                                                                                                                                                                                                                                  |
| **Data di inizio importazione**                       | Questo parametro determina se eseguire l'importazione alla data attuale o in base a un intervallo di date. Se si desidera utilizzare un intervallo di date, immettere o selezionare le date di inizio e fine.                                                                                                                                                                                                                |
| **Crea coppie di valute necessarie**    | Questa casella di controllo gestisce la creazione automatica di coppie di valuta, se le coppie di valuta importate non esistono. Questa opzione potrebbe non essere disponibile per alcuni provider.                                                                                                                                                                                               |
| **Ignora tassi di cambio esistenti**   | Questa casella di controllo gestisce l'aggiornamento del tasso di cambio esistente di una coppia di valute quando il tasso di cambio per una data specifica è già presente. Se non si seleziona questa casella di controllo, il tasso di cambio per le date specifiche non viene importato se esiste già un altro tasso di cambio.                                                                                       |
| **Impedisci importazione in festa nazionale** | Questa casella di controllo gestisce l'importazione del tasso di cambio per una data che è una festa nazionale. Ad esempio, se si seleziona questa casella di controllo e si utilizza la Banca Centrale Europea come provider di tassi di cambio, il sistema non aggiornerà il tasso di cambio durante la festa nazionale correlata alla persona giuridica corrente. Questa opzione potrebbe non essere disponibile per alcuni provider. |






