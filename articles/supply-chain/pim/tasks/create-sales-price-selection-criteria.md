---
title: Creare criteri di selezione di prezzo di vendita
description: In questa procedura viene illustrato come creare un criterio di selezione del prezzo di vendita per i modelli basati sugli attributi.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed7083f289948033782f74dd9ed1b3c2d2a73aea
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568449"
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