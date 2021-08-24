---
title: Importare tassi di cambio valutari
description: In questo argomento vengono fornite informazioni sui requisiti per l'importazione di tassi di cambio estero di riferimento pubblicati dai fornitori di tassi di cambio.
author: EvgenyPopovMBS
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: f96622132be3c8a404f3f4e9c34f3ac5085a4fdc007ecb627d06a95d7c80932b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727326"
---
# <a name="import-currency-exchange-rates"></a>Importare tassi di cambio valutari

[!include [banner](../includes/banner.md)]

Se una persona giuridica ha ricevuto fatture in valuta estera, la valuta estera deve essere convertita in quella locale. Ciò significa che è necessario conoscere i tassi di cambio aggiornati per le diverse valute. In questo argomento viene fornita una panoramica delle impostazioni e dell'elaborazione richieste per importare tassi di cambio estero pubblicati dai provider di tassi di cambio, ad esempio la Banca Centrale Europea e la Banca Centrale di Russia.

Nelle sezioni seguenti viene descritto il flusso di informazioni utilizzato per impostare ed elaborare l'importazione dei tassi di cambio estero.

## <a name="configure-an-exchange-rate-provider"></a>Configurare un provider di tassi di cambio
Prima di poter importare i tassi di cambio, è necessario impostare le informazioni richieste dai provider di tassi di cambio. Utilizzare la pagina **Configura provider di tassi di cambio** per selezionare i provider di tassi di cambio. Alcuni provider di tassi di cambio sono inclusi nei dati dimostrativi in Dynamics 365 Finance. Nella tabella riportata di seguito sono incluse le descrizioni relative ai controlli presenti nella pagina.

| Campo | descrizione                   |
|-----------|-----------------------------------|
| **Nome**  | Nome del provider di tassi di cambio.                                                                                                                                                                                     |
| **Chiave**   | Identificatore univoco per ogni informazione di configurazione richiesta dal provider. Queste informazioni vengono aggiunte automaticamente per ciascun fornitore del tasso di cambio aggiunto. |
| **Value** | Informazioni per ogni chiave. Queste informazioni vengono aggiunte per ciascun fornitore del tasso di cambio aggiunto.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importare tassi di cambio valutari
È possibile importare i tassi di cambio dall'origine dei provider di tassi di cambio e aggiungerli alla pagina **Tassi di cambio valutario**. Utilizzare la pagina **Importa tassi di cambio valutari** per importare i tassi di cambio. Nella tabella seguente vengono descritti i campi necessari per completare correttamente il processo di importazione.

| Campo | descrizione                   |
|-----------|-----------------------------------|
| **Tipo di tasso di cambio**                 | Tipo di tasso di cambio.                                                                                                                                                                                                                                                                                                                                                      |
| **Provider di tassi di cambio**             | Provider di tassi di cambio.                                                                                                                                                                                                                                                                                                                                                  |
| **Data di inizio importazione**                       | Questo parametro determina se eseguire l'importazione alla data corrente o in base a un intervallo di date specifico. Se si desidera utilizzare un intervallo di date, immettere o selezionare le date di inizio e fine.                                                                                                                                                                                                                |
| **Crea coppie di valute necessarie**    | Questa casella di controllo gestisce la creazione automatica di coppie di valuta, se le coppie di valuta importate non esistono. Questa opzione potrebbe non essere disponibile per alcuni provider.                                                                                                                                                                                               |
| **Ignora tassi di cambio esistenti**   | Questa casella di controllo gestisce l'aggiornamento del tasso di cambio esistente di una coppia di valute quando il tasso di cambio per una data specifica è già presente. Se non si seleziona questa casella di controllo, il tasso di cambio per le date specifiche non viene importato se esiste già un altro tasso di cambio.                                                                                       |
| **Impedisci importazione in festa nazionale** | Questa casella di controllo gestisce l'importazione del tasso di cambio per una data che è una festa nazionale. Ad esempio, se si seleziona questa casella di controllo e si utilizza la Banca Centrale Europea come provider di tassi di cambio, il sistema non aggiornerà il tasso di cambio durante la festa nazionale correlata alla persona giuridica corrente. Questa opzione potrebbe non essere disponibile per alcuni provider. |
| **Tasso del giorno precedente** | Questa casella di controllo è disponibile se si abilita la funzionalità **Importazione ECB alla data corrente o precedente** nella pagina **Gestione funzionalità**. Questa casella di controllo è disponibile solo per il provider, *Banca centrale europea*. Selezionare questa casella di controllo per importare il tasso di cambio valuta pubblicato dalla Banca centrale europea il giorno lavorativo precedente alle 16:00 CET circa. Per impostazione predefinita, la casella di controllo è selezionata. Deselezionarla per importare il tasso di cambio valutario pubblicato nello stesso giorno lavorativo.  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]