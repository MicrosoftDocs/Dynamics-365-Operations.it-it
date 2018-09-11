--- 
title: 'Creare oggetti di costo  '
description: "In questa procedura viene illustrato come creare oggetti di costo importando la dimensione finanziaria centro di costo di Dynamics 365 for Finance and Operations, Enterprise edition nella contabilità industriale tramite un connettore dati."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5d43274aed2edbb91fd4e399cb8d45e91646b055
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-cost-objects"></a>Creare oggetti di costo   

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come creare oggetti di costo importando la dimensione finanziaria centro di costo di Dynamics 365 for Finance and Operations, Enterprise edition nella contabilità industriale tramite un connettore dati. La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura. Questa procedura è per una funzionalità di Contabilità industriale che è stata aggiunta in Dynamics 365 for Operations, versione 1611.


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


