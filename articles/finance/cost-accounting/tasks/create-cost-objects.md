---
title: 'Creare oggetti di costo  '
description: In questa procedura viene illustrato come creare oggetti di costo importando la dimensione finanziaria centro di costo nella contabilità industriale tramite un connettore dati.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1219cb15ecec7c156579c5cf7c3a3511a141e00b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810056"
---
# <a name="create-cost-objects"></a>Creare oggetti di costo   

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come creare oggetti di costo importando la dimensione finanziaria centro di costo nella contabilità industriale tramite un connettore dati. La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura. 


## <a name="create-new-cost-objects"></a>Creare nuovi oggetti di costo
1. Passare a Contabilità industriale > Dimensioni > Dimensioni oggetto di costo.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
4. Nel campo Connettore dati per membri di dimensione immettere o selezionare un valore.
5. Nel campo Descrizione digitare un valore.
6. Fare clic su Salva.

## <a name="configure-the-data-connector"></a>Configurare il connettore dati
1. Fare clic su Configura provider membro di dimensione.
    * Selezionare CostCenter per importare la dimensione CostCenter nella contabilità industriale.  
2. Nel campo Nome dimensione, selezionare Centro di costo.
3. Fare clic su OK.

## <a name="import-cost-centers"></a>Importare i centri di costo
1. Fare clic su Importa membri di dimensione.
2. Fare clic su OK.

## <a name="view-the-imported-cost-centers"></a>Visualizzare i centri di costo importati
1. Fare clic su Visualizza membri di dimensione.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]