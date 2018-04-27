--- 
title: Creare criteri di selezione di prezzo di vendita
description: In questa procedura viene illustrato come creare un criterio di selezione del prezzo di vendita per i modelli basati sugli attributi.
author: YuyuScheller
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 59f6a4131f6a27c0089a1259e3f849f91a47bc87
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-sales-price-selection-criteria"></a>Creare criteri di selezione di prezzo di vendita

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come creare un criterio di selezione del prezzo di vendita per i modelli basati sugli attributi. L'esecuzione di questa procedura richiede almeno un modello di prezzo di vendita disponibile. In questo esempio viene utilizzato il modello di prezzo di vendita della soluzione Speaker nella società di dati dimostrativi USMF. In genere, un responsabile di prodotto usa questa procedura.


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Aggiungere un nuovo criterio per un modello di prezzo di vendita esistente
1. Fare clic su Definizione modello di variante prodotto.
2. Fare clic su Modelli di configurazione prodotto.
3. Nell'elenco, selezionare la riga per il modello prodotto della soluzione Speaker, ma non fare clic sul collegamento corrispondente al nome del modello.
4. Nel riquadro azioni, fare clic su Modello.
5. Fare clic su Criteri modello di prezzo.
6. Fare clic su Nuovo.
7. Nel campo Nome digitare ‘Gruppo clienti 10’.
    * Il nome del criterio per il modello del prezzo viene utilizzato per identificare i criteri di selezione sottostanti.  
8. Nel campo Modello di prezzo immettere o selezionare un valore.
9. Nel campo Tipo di ordine selezionare Ordine cliente.
    * Il tipo di ordine determina i campi di database da rendere disponibili per la query di selezione.  
10. Immettere una data nel campo Data di inizio validità.
11. Nel campo Data scadenza immettere una data.
12. Fare clic su Salva.

## <a name="create-the-query-for-the-selection-criteria"></a>Creare la query per i criteri di selezione
1. Fare clic su Modifica.
2. Selezionare Clienti nel campo Tabella. 
3. Selezionare Gruppo di clienti nel campo Campo.
    * In questo esempio, useremo uno specifico gruppo di clienti per i criteri di selezione.  
4. Nel campo Criteri selezionare Gruppo di clienti 10. 
5. Fare clic su OK.


