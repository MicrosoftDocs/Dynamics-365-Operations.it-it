---
title: 'Creare elementi di costo  '
description: Esistono vari modi per creare gli elementi di costo nella contabilità industriale.
author: kfend
ms.date: 08/29/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
ms.openlocfilehash: 0254f486816e852bcda52f90fe4da65c413c7032
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779691"
---
# <a name="create-cost-elements"></a>Creare elementi di costo   

[!include [banner](../../includes/banner.md)]

Esistono vari modi per creare gli elementi di costo nella contabilità industriale. In questa procedura viene illustrato come creare elementi di costo importando i conti principali tramite un connettore dati. La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura. Questa procedura è per una funzionalità di contabilità industriale che è stata aggiunta in Dynamics 365 for Operations, versione 1611.


## <a name="create-new-cost-elements"></a>Creare nuovi elementi di costo
1. Passare a **Contabilità industriale > Dimensioni > Dimensioni elemento di costo**.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Nome**.
4. Nel campo **Connettore dati per membri di dimensione** immettere o selezionare un valore.
5. Digitare un valore nel campo **Descrizione**
6. Fare clic su **Salva**.

## <a name="configure-the-data-connector"></a>Configurare il connettore dati
1. Fare clic su **Configura provider membro di dimensione**.
2. Nel campo **Piano dei conti** immettere o selezionare un valore.
    * Selezionare **Condiviso** per utilizzare un piano dei conti condiviso.  
3. Fare clic su **Nuovo**.
4. Nell'elenco contrassegnare la riga selezionata.
    * È possibile applicare filtri ai conti per soddisfare i criteri.  
5. Nel campo **Da conto principale**, immettere o selezionare un valore.
6. Nel campo **A conto principale**, immettere o selezionare un valore.
7. Fare clic su **OK**.

## <a name="import-main-accounts"></a>Importa conti principali
1. Fare clic su **Importa membri di dimensione**.
    * I conti principali verranno importati nella contabilità industriale e utilizzati come elementi di costo.  
2. Fare clic su **OK**.

## <a name="view-the-imported-accounts-as-cost-elements"></a>Visualizzare i conti importati come elementi di costo
1. Fare clic su **Visualizza membri di dimensione**.
    * Consente di visualizzare i conti CoGe importati come elementi di costo nell'azienda in cui i costi possono fluire.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
