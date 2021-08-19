---
title: Creare e gestire un blocco scorte
description: Questo argomento descrive come usare un blocco scorte per impedire che scorte fisiche disponibili vengano prenotate da altri documenti di origine in uscita.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d602abe4491f6cbbd0fce25a566acf97a25f3bf1e6214e95c80fda2638d14dde
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773276"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Creare e gestire un blocco scorte

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come usare un blocco scorte per impedire che scorte fisiche disponibili vengano prenotate da altri documenti di origine in uscita. Prima di iniziare le procedure in questo argomento, è necessario disporre di un articolo con scorte fisiche disponibili.

## <a name="block-inventory"></a>Blocca scorte

Per creare un record di blocco scorte in modo che le scorte siano bloccate, segui questi passaggi.

1. Andare a **Gestione articoli \> Attività periodiche \> Blocco scorte**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'intestazione del nuovo record di blocco, impostare il campo **Numero articolo** sull'articolo che si desidera bloccare e immettere una descrizione.
1. Nella scheda dettaglio **Generale**, nel campo **Quantità** immettere il numero di articoli da bloccare.
1. Nella scheda dettaglio **Dimensioni inventariali**, specificare il sito e il magazzino in cui si trovano attualmente gli articoli che si desidera bloccare.
1. Nel riquadro azioni selezionare **Salva**.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Aggiornare le condizioni del blocco scorte

Per aggiornare un record di blocco scorte, segui questi passaggi.

1. Andare a **Gestione articoli \> Attività periodiche \> Blocco scorte**.
1. Nel riquadro elenco, selezionare il record di blocco pertinente.
1. Modifica il record in base alle esigenze. Ad esempio, potresti modificare il valore del campo **Data prevista** per indicare il momento in cui si prevede che le scorte bloccate diventino disponibili per la prenotazione. Se l'opzione **Entrate previste** è selezionata, la data apparirà sulla transazione prevista. (L'opzione **Entrate previste** è selezionata per impostazione predefinita quando si crea manualmente un record di blocco.)
1. Nel riquadro azioni selezionare **Salva**.

## <a name="unblock-inventory"></a>Sloccare le scorte

Per rimuovere un record di blocco scorte in modo che le scorte siano sbloccate, segui questi passaggi.

1. Andare a **Gestione articoli \> Attività periodiche \> Blocco scorte**.
1. Nel riquadro elenco, selezionare il record di blocco pertinente.
1. Nel riquadro azioni selezionare **Elimina**.
1. Ti viene chiesto di confermare l'operazione. Selezionare **Sì** per continuare.
1. Chiudere la pagina.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
