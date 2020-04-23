---
title: Creare criteri di selezione di prezzo di vendita
description: In questa procedura viene illustrato come creare un criterio di selezione del prezzo di vendita per i modelli basati sugli attributi.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6d1385a83da5b6448a9c753d7469979796043b60
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203779"
---
# <a name="create-sales-price-selection-criteria"></a>Creare criteri di selezione di prezzo di vendita

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come creare un criterio di selezione del prezzo di vendita per i modelli basati sugli attributi. L'esecuzione di questa procedura richiede almeno un modello di prezzo di vendita disponibile. In questo esempio viene utilizzato il modello di prezzo di vendita della soluzione Speaker nella società di dati dimostrativi USMF. In genere, un responsabile di prodotto usa questa procedura.


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Aggiungere un nuovo criterio per un modello di prezzo di vendita esistente
1. Fare clic su Definizione modello di variante prodotto.
2. Fare clic su Modelli di configurazione prodotto.
3. Nell'elenco, selezionare la riga per il modello prodotto della soluzione Speaker, ma non fare clic sul collegamento corrispondente al nome del modello.
4. Nel riquadro azioni, fare clic su Modello.
5. Fare clic su Criteri modello di prezzo.
6. Fare clic su Nuovo.
7. Nel campo Nome digitare "Gruppo clienti 10".
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

