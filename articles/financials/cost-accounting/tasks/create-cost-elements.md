---
title: 'Creare elementi di costo  '
description: Esistono vari modi per creare gli elementi di costo nella contabilità industriale.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7cceec1d52e1b5b2a05525c8d96f46dece17363b
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841299"
---
# <a name="create-cost-elements"></a>Creare elementi di costo   

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esistono vari modi per creare gli elementi di costo nella contabilità industriale. In questa procedura viene illustrato come creare elementi di costo importando i conti principali tramite un connettore dati. La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura. Questa procedura è per una funzionalità di contabilità industriale che è stata aggiunta in Dynamics 365 for Operations, versione 1611.


## <a name="create-new-cost-elements"></a>Creare nuovi elementi di costo
1. Passare a Contabilità industriale > Dimensioni > Dimensioni elemento di costo.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
4. Nel campo Connettore dati per membri di dimensione immettere o selezionare un valore.
5. Nel campo Descrizione digitare un valore.
6. Fare clic su Salva.

## <a name="configure-the-data-connector"></a>Configurare il connettore dati
1. Fare clic su Configura provider membro di dimensione.
2. Nel campo Piano dei conti immettere o selezionare un valore.
    * Selezionare Condiviso per utilizzare un piano dei conti condiviso.  
3. Fare clic su Nuovo.
4. Nell'elenco contrassegnare la riga selezionata.
    * È possibile applicare filtri ai conti per soddisfare i criteri.  
5. Nel campo Da conto principale, immettere o selezionare un valore.
6. Nel campo A conto principale, immettere o selezionare un valore.
7. Fare clic su OK.

## <a name="import-main-accounts"></a>Importa conti principali
1. Fare clic su Importa membri di dimensione.
    * I conti principali verranno importati nella contabilità industriale e utilizzati come elementi di costo.  
2. Fare clic su OK.

## <a name="view-the-imported-accounts-as-cost-elements"></a>Visualizzare i conti importati come elementi di costo
1. Fare clic su Visualizza membri di dimensione.
    * Consente di visualizzare i conti CoGe importati come elementi di costo nell'azienda in cui i costi possono fluire.  

