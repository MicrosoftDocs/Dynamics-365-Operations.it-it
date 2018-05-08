--- 
title: 'Impostare i registri dei beni ammortizzabili '
description: "Questa guida attività creerà un nuovo registro beni ammortizzabili e lo assocerà a un gruppo cespite."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d06d5f92e91e33dc752bf45ab890c37dfea3888d
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-depreciation-books"></a>Impostare i registri dei beni ammortizzabili  

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa guida attività creerà un nuovo registro beni ammortizzabili e lo assocerà a un gruppo cespite.  Utilizza il ruolo Ragioniere e i dati dimostrativi per la persona giuridica USMF.


## <a name="create-a-depreciation-book"></a>Creare un registro beni ammortizzabili
1. Andare a Cespiti > Impostazioni > Registri beni ammortizzabili.
2. Fare clic su Nuovo.
3. Nel campo Registro beni ammortizzabili digitare un valore.
4. Nel campo Descrizione digitare un valore.
5. Selezionare o deselezionare la casella di controllo Calcola ammortamento.
6. Nel campo Profilo di ammortamento fare clic sul pulsante a discesa per aprire la ricerca.
7. Nell'elenco trovare e selezionare il profilo di ammortamento desiderato.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Nel campo Profilo di ammortamento alternativo fare clic sul pulsante a discesa per aprire la ricerca.
10. Nell'elenco selezionare il profilo di ammortamento desiderato.
11. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Parametri di ammortamento straordinario viene utilizzato per l'ammortamento aggiuntivo di un cespite in circostanze insolite. È ad esempio possibile utilizzare questi parametri per registrare l'ammortamento causato da un disastro naturale.  
12. Selezionare o deselezionare la casella di controllo Crea rettifiche all'ammortamento con rettifiche di base.
13. Nel campo Calendario fare clic sul pulsante a discesa per aprire la ricerca.
14. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a>Consente di associare il registro beni ammortizzabili a un gruppo cespite.
1. Fare clic su Gruppi cespiti.
2. Nel campo Gruppo cespite fare clic sul pulsante a discesa per aprire la ricerca.
3. Trovare e selezionare il record desiderato nell'elenco.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Nel campo Convenzione di ammortamento selezionare un'opzione.
6. Immettere un numero nel campo Vita utile.
    * Si noti che il valore del campo Periodi di ammortamento viene calcolato dopo aver impostato la Vita utile.  


