---
title: Impostare i registri beni ammortizzabili (maggio 2016)
description: Questa guida attività creerà un nuovo registro beni ammortizzabili e lo assocerà a un gruppo cespite.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1fd53ea1dff9b116d19c525c5d6967ece0993b6f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "355566"
---
# <a name="set-up-depreciation-books-may-2016"></a>Impostare i registri beni ammortizzabili (maggio 2016)

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

