---
title: Aprire i modelli di giornale di registrazione finanziario in Office
description: In questo articolo vengono descritti i problemi che potrebbero verificarsi quando si creano giornali di registrazione finanziari personalizzati utilizzando un modello Microsoft Excel.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a29ab1cb2980ebfed6c6fa6409538bc802849156
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896349"
---
# <a name="open-financial-journal-templates-in-office"></a>Aprire i modelli di giornale di registrazione finanziario in Office

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritti i problemi che potrebbero verificarsi quando si creano giornali di registrazione finanziari personalizzati utilizzando un modello Microsoft Excel.

## <a name="symptom"></a>Sintomo

È stato creato un modello di Excel personalizzato per i giornali di registrazione finanziari, ma non viene visualizzato nel menu **Apri righe in Excel**. In alternativa, è presente nel menu, ma quando lo si seleziona viene aperto un modello diverso.

## <a name="resolution"></a>Risoluzione

La funzionalità predefinita Apri in Excel utilizza l'origine dati radice (tabella) della pagina corrente per determinare quali modelli o entità di dati di Office vengono visualizzati come opzioni nel menu **Apri in Excel**. Questo comportamento non è un'esperienza ideale per i giornali di registrazione finanziari, perché utilizzano le stesse tabelle (LedgerJournalTable e LedgerJournalTrans) come origine dati radice di molti altri tipi di giornali di registrazione.

Per i giornali di registrazione finanziari, la funzionalità Apri righe in Excel ha lo scopo di mostrare i modelli progettati per il giornale di registrazione nel quale si sta attualmente lavorando, come il giornale di registrazione generale o un giornale di registrazione pagamenti. Ad esempio, un modello da utilizzare con un giornale di registrazione pagamenti fornitore è progettato per impostare il conto principale come conto fornitore.

Per promuovere un modello in modo che sia disponibile nei menu **Apri righe in Excel** e **Apri in Excel**, una semplice esperienza per sviluppatori consiste nell'implementare l'interfaccia **LedgerIJournalExcelTemplate** ed estendere la classe **DocuTemplateRegistrationBase**. Molti esempi di questo approccio sono implementati nel sistema. Un esempio da usare come riferimento è l'interfaccia **LedgerDailyJournalExcelTemplate** che è stata creata per il giornale di registrazione generale (o il giornale di registrazione giornaliero).

Quando l'interfaccia **LedgerIJournalExcelTemplate** è implementata per il modello, il menu **Apri righe in Excel** filtra i modelli in base al tipo di giornale di registrazione in uso e mostra solo i modelli disponibili per quel giornale. L'interfaccia fornisce anche un metodo di convalida che garantisce che un modello non possa essere aperto per un giornale di registrazione se non soddisfa i requisiti del tipo di conto. Ad esempio, è possibile specificare che il tipo di conto debba essere di tipo **Fornitore** o **Contabilità generale**.

Per ulteriori informazioni su questa funzionalità, vedere [Aggiungere modelli al menu Apri righe in Excel](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).
