---
title: Modificare o eliminare un ordine cliente interaziendale originale
description: Questo argomento spiega la modifica e l'eliminazione di una funzionalità dell'ordine cliente originario
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7bd6bdbf65499e9f18bf6bb5e160a5634bc37fba
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548352"
---
# <a name="change-or-delete-an-original-intercompany-sales-order"></a>Modificare o eliminare un ordine cliente interaziendale originale

[!include [banner](../../includes/banner.md)]

Quando si modifica un ordine cliente, le modifiche vengono sincronizzate automaticamente con l'ordine fornitore interaziendale pertinente e con l'ordine cliente interaziendale.

> [!NOTE]
> Le modifiche apportate non hanno alcun effetto sugli ordini fornitore relativi ai fornitori esterni né sulle righe di vendita originali collegate alle righe dell'ordine fornitore relative ai fornitori esterni.

La tabella seguente riepiloga le modifiche che è possibile apportare e i risultati previsti.

| Operazione | Risultato |
|---|---|
| Eliminare&nbsp;un&nbsp;ordine&nbsp;cliente&nbsp;originale. | Vengono eliminati anche l'ordine fornitore interaziendale correlato e l'ordine cliente interaziendale. Se lo stato dell'ordine è impostato su **Distinta di prelievo** o su una fase successiva del processo, non sarà possibile eliminare la riga dell'ordine cliente. |
| Eliminare una riga dell'ordine cliente originario. | Vengono eliminate la riga dell'ordine fornitore interaziendale correlato e la riga dell'ordine cliente interaziendale. Se lo stato dell'ordine è impostato su **Distinta di prelievo** o su una fase successiva del processo, non sarà possibile eliminare la riga dell'ordine cliente. |
| Aggiungere una nuova riga di vendita all'ordine cliente originario. | La nuova riga di vendita viene creata sia nell'ordine fornitore interaziendale sia nell'ordine cliente interaziendale. |
| Modificare la quantità di una riga dell'ordine cliente originario. | La quantità viene sincronizzata con la riga dell'ordine fornitore interaziendale e con la riga dell'ordine cliente interaziendale. L'importo netto viene ricalcolato per tutti gli ordini. |
| Disabilitare la consegna diretta in un ordine cliente originario. | Non è possibile modificare il campo **Consegna diretta** nell'ordine cliente originario se la riga dell'ordine cliente interaziendale ha raggiunto uno stato minimo di **Distinta di prelievo**, **Ordine di uscita** o **Giornale di registrazione distinte di prelievo**. L'indirizzo di consegna dell'ordine fornitore interaziendale viene modificato nell'indirizzo di consegna standard (indirizzo di consegna dell'ordine fornitore standard). Anche le righe dell'ordine dell'ordine fornitore interaziendale vengono modificate nell'indirizzo di consegna standard per le relative righe. Entrambi vengono sincronizzati con l'ordine cliente interaziendale e con le righe. Il tipo di consegna per tutte le righe dell'ordine cliente originario viene modificato in **Nessuno** e il campo viene sincronizzato con le righe dell'ordine fornitore interaziendale. Non vengono modificati né gli ordini fornitore relativi ai fornitori esterni né le righe di vendita originarie collegate alle righe dell'ordine fornitore relative ai fornitori esterni. Vengono aggiornate sia la data di consegna dell'ordine fornitore interaziendale e delle relative righe sia le date di ricevimento/spedizione richieste dell'ordine cliente interaziendale e delle relative righe. |
| Abilitare la consegna diretta in un ordine cliente originario. | Non è possibile modificare il campo **Consegna diretta** nell'ordine cliente originario se la riga dell'ordine cliente interaziendale ha raggiunto uno stato minimo di **Distinta di prelievo**, **Ordine di uscita** o **Giornale di registrazione distinte di prelievo**. L'indirizzo di consegna dell'ordine fornitore interaziendale viene modificato nell'indirizzo di consegna dell'ordine cliente originario e viene sincronizzato con l'ordine cliente interaziendale. Il tipo di consegna per tutte le righe dell'ordine cliente originario viene modificato in **Consegna diretta** e il campo viene sincronizzato con le righe dell'ordine fornitore interaziendale. L'indirizzo di consegna di ciascuna riga dell'ordine cliente originario viene sincronizzata sia con le righe dell'ordine fornitore interaziendale sia con le righe dell'ordine cliente interaziendale. Vengono aggiornate sia la data di consegna dell'ordine fornitore interaziendale e delle relative righe sia le date di ricevimento/spedizione richieste dell'ordine cliente interaziendale e delle relative righe. |
| Aggiungere una nota sia all'intestazione dell'ordine cliente originario sia alle righe. | La nota viene copiata nell'ordine fornitore interaziendale e nell'ordine cliente interaziendale. |
| Modificare o eliminare una nota. | Se una nota viene modificata o eliminata, la nota corrispondente nell'ordine fornitore interaziendale e nell'ordine cliente interaziendale viene modificata o eliminata di conseguenza. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
