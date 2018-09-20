---
title: Pagina dell'elenco transazioni fornitore
description: Questo argomento fornisce informazioni sulla pagina dell'elenco delle transazioni fornitore per Microsoft Dynamics 365 for Finance and Operations.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: 1ef7d97f059801f2fb2c0d451546b57055208f81
ms.contentlocale: it-it
ms.lasthandoff: 08/31/2018

---

# <a name="vendor-transaction-list-page"></a>Pagina dell'elenco transazioni fornitore

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Visualizza liquidazioni

La scheda **Visualizza liquidazioni** del riquadro azioni offre un accesso rapido allo storico delle liquidazioni e altre informazioni sull'intera transazione delle liquidazioni. È inoltre possibile mostrare altre transazioni che sono correlate alla transazione selezionata, perché fanno parte della stessa liquidazione o perché sono pagamenti creati nello stesso giornale di registrazione pagamenti.

1. Selezionare **Contabilità fornitori \> Tutti i fornitori**.
2. Selezionare un fornitore con transazioni e quindi selezionare **Fornitore \> Transazioni**.
3. Selezionare una transazione da cercare.
4. Selezionare la scheda **Visualizza liquidazioni** nel riquadro azioni.

    Viene visualizzata la finestra di dialogo **Visualizza liquidazioni** che mostra la transazione selezionata e tutti i documento che sono stati liquidati ad essa collegati. Questa finestra di dialogo assomiglia alla visualizzazione dello storico delle liquidazioni, ma include tutti i documenti correlati.

5. È possibile eseguire varie attività da questa finestra di dialogo. Selezionare uno o più giustificativi e quindi selezionare uno dei menu seguenti:

   - **Visualizza contabilità** - Vengono visualizzati tutti i giustificativi che sono correlati ai documenti selezionati. Selezionare **Chiudi** per chiudere la finestra di dialogo.
   - **Esporta** - Esportare i giustificativi selezionati in Microsoft Excel.
   - **Visualizza pagamenti correlati** - Vengono visualizzate tutte le transazioni del giornale di registrazione pagamenti che sono state create nel giornale di registrazione pagamenti che è correlato al documento selezionato. Vengono inoltre visualizzate tutte le liquidazioni correlate a tali pagamenti. Anche l'etichetta di questo menu cambia in **Visualizza liquidazioni**. Selezionare **Visualizza liquidazioni** per mostrare solo le transazioni che erano visualizzate la prima volta che è stata aperta la finestra di dialogo **Visualizza liquidazioni**.
    - **Liquida transazioni** - Questo menu viene visualizzato se il documento originale che era selezionato non è stato completamente liquidato. Quando si seleziona questo menu, viene visualizzata la finestra di dialogo **Liquida transazioni**, nella quale è possibile selezionare le transazioni da liquidare.
    - **Annulla liquidazioni** - Questo menu viene visualizzato se il documento originale che era stato selezionato era stato completamente liquidato. Quando si seleziona questo menu, viene visualizzata la finestra di dialogo **Annulla liquidazioni** nella quale è possibile annullare le liquidazioni eseguite per il documento.

