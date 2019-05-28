---
title: Impostare l'ammortamento straordinario
description: In questa procedura viene illustrato come creare un fondo di ammortamento speciale e associarlo a un libro cespiti.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6bbd6b78d05fcc9d95f6e6409db2619a210ad760
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571709"
---
# <a name="set-up-bonus-depreciation"></a>Impostare l'ammortamento straordinario

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come creare un fondo di ammortamento speciale e associarlo a un libro cespiti. Utilizza il ruolo Ragioniere e i dati dimostrativi della persona giuridica USMF.


## <a name="create-a-special-depreciation-allowance"></a>Creare un fondo di ammortamento speciale
1. Andare a Cespiti > Impostazioni > Fondo di ammortamento speciale.
2. Fare clic su Nuovo.
3. Nel campo Fondo di ammortamento speciale digitare un valore.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Percentuale immettere un numero.
    * Impostare un importo se non è stata indicata una percentuale.  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a>Associare un fondo di ammortamento speciale a un libro gruppo cespite
1. Andare a Cespiti > Impostazioni > Gruppi cespite.
2. Nell'elenco selezionare un gruppo cespite associato al fondo di ammortamento speciale.
3. Fare clic su Libri.
4. Nell'elenco selezionare il libro associato al fondo di ammortamento speciale.
5. Fare clic su Fondo di ammortamento speciale.
6. Fare clic su Nuovo.
7. Nel campo Fondo di ammortamento speciale immettere o selezionare un valore.
    * Il valore predefinito di Percentuale o Importo viene dall'impostazione del fondo di ammortamento speciale.  
8. Nel campo Priorità immettere un numero.

