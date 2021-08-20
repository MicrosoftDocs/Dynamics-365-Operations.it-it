---
title: Creare criteri di selezione di prezzo di vendita
description: In questa procedura viene illustrato come creare un criterio di selezione del prezzo di vendita per i modelli basati sugli attributi.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 47ea7ea2093c540a88d9fd7249b470009c7595d40e2a727d8fcd3bb4b5d74bac
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750078"
---
# <a name="create-sales-price-selection-criteria"></a>Creare criteri di selezione di prezzo di vendita

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come creare un criterio di selezione del prezzo di vendita per i modelli basati sugli attributi. L'esecuzione di questa procedura richiede almeno un modello di prezzo di vendita disponibile. In questo esempio viene utilizzato il modello di prezzo di vendita della soluzione Speaker nella società di dati dimostrativi USMF. In genere, un responsabile di prodotto usa questa procedura.

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Aggiungere un nuovo criterio per un modello di prezzo di vendita esistente

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.
1. Nell'elenco, selezionare la riga per il modello prodotto della soluzione Speaker, ma non fare clic sul collegamento corrispondente al nome del modello.
1. Nel Riquadro azioni selezionare **Modello**.
1. Selezionare **Criteri modello di prezzo**
1. Selezionare **Nuovo**.
1. Nel campo **Nome** digitare "Gruppo clienti 10".
    * Il nome del criterio per il modello del prezzo viene utilizzato per identificare i criteri di selezione sottostanti.  
1. Nel campo **Modello di prezzo** immettere o selezionare un valore.
1. Nel campo **Tipo di ordine** selezionare *Ordine cliente*.
    * Il tipo di ordine determina i campi di database da rendere disponibili per la query di selezione.  
1. Immettere una data nel campo **Data di inizio validità**.
1. Nel campo **Data scadenza** immettere una data.
1. Selezionare **Salva**.

## <a name="create-the-query-for-the-selection-criteria"></a>Creare la query per i criteri di selezione

1. Seleziona **Modifica**.
2. Selezionare **Clienti** nel campo *Tabella*.
3. Selezionare **Gruppo di clienti** nel campo *Campo*.
    * In questo esempio, useremo uno specifico gruppo di clienti per i criteri di selezione.  
4. Nel campo **Criteri** selezionare *Gruppo di clienti 10*.
5. Selezionare **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]