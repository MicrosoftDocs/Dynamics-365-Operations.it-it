---
title: Impostare i registri di beni ammortizzabili
description: Questa procedura illustra il processo di creazione di un nuovo registro beni ammortizzabili e di associazione a un gruppo di cespiti.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 03f915fa91e0eeff2f26ab9a60bbd5118317e853
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444856"
---
# <a name="set-up-depreciation-books"></a>Impostare i registri di beni ammortizzabili 

[!include [banner](../../includes/banner.md)]

Questa procedura illustra il processo di creazione di un nuovo registro beni ammortizzabili e di associazione a un gruppo di cespiti. 

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]