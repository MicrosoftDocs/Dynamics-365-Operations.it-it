---
title: Aggiungere un calcolo a un modello di configurazione dei prodotti
description: In questa procedura vengono descritti i passaggi per aggiungere un nuovo calcolo a un modello di configurazione prodotto.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 268baa4b518f6df52d4393f7278a79cbe1733844
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812678"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Aggiungere un calcolo a un modello di configurazione dei prodotti

[!include [banner](../../includes/banner.md)]

In questa procedura vengono descritti i passaggi per aggiungere un nuovo calcolo a un modello di configurazione prodotto. Indica come è possibile creare un'espressione logica utilizzando l'operatore "If" per impostare l'altezza dell'altoparlante a 10 per gli altoparlanti bianchi e a 15 per tutti gli altri colori. La procedura utilizza il componente High end speaker nella società di dati dimostrativi USMF.


## <a name="add-a-calculation"></a>Aggiungere un calcolo

## <a name="create-calculation-expression"></a>Creare un'espressione di calcolo
1. Fare clic su Modifica espressione.
2. Nel campo ConstraintBody, immettere 'If[CabinetFinish=="White", 10, 15]'.
3. Fare clic su Convalida.
4. Fare clic su Chiudi.
5. Fare clic su OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]