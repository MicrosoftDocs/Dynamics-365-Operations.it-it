---
title: Riutilizzare le configurazioni prodotto
description: È possibile specificare che si desidera automaticamente riutilizzare una configurazione esistente per un prodotto. Quindi quando l'utente termina una sessione di configurazione, il sistema verifica se è già presente una configurazione corrispondente alle selezioni dell'utente. Se viene rilevata una configurazione corrispondente, vengono riutilizzati l'ID di configurazione, la distinta base (DBA) corrispondente e il ciclo di lavorazione.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 21dc25b878ff65b57b060fe3d74b5d120fa4b5cd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260601"
---
# <a name="reuse-product-configurations"></a>Riutilizzare le configurazioni prodotto

[!include [banner](../includes/banner.md)]

È possibile specificare che si desidera automaticamente riutilizzare una configurazione esistente per un prodotto. Quindi quando l'utente termina una sessione di configurazione, il sistema verifica se è già presente una configurazione corrispondente alle selezioni dell'utente. Se viene rilevata una configurazione corrispondente, vengono riutilizzati l'ID di configurazione, la distinta base (DBA) corrispondente e il ciclo di lavorazione.

<a name="requirements-for-reusing-configurations"></a>Requisiti per il riutilizzo delle configurazioni
---------------------------------------

Per abilitare il riutilizzo delle configurazioni, è necessario specificare le seguenti informazioni per i componenti e gli attributi nella pagina **Dettagli modello configurazione prodotto**:

-   **Componenti e sottocomponenti** - Nella Scheda dettaglio **Generale**, campo **Riutilizza configurazioni**, selezionare **Sì**.
-   **Attributi** - Nella scheda dettaglio **Attributi**, selezionare l'opzione **Includi in riutilizzo**. Questa opzione viene visualizzata solo se il componente correlato è abilitato per il riutilizzo. Se non si seleziona alcun attributo per il riutilizzo, la configurazione verrà sempre riutilizzata, indipendentemente dalle selezioni dell'utente durante una sessione di configurazione. I valori degli attributi della configurazione esistente devono corrispondere alle selezioni dell'utente. Ad esempio, se l'utente seleziona il colore **Blu** come colore durante una sessione di configurazione, il sistema verifica se una configurazione esistente del componente presenta il colore blu.

## <a name="resetting-configuration-reuse"></a>Reimpostazione del riutilizzo configurazioni
Quando si reimposta il riutilizzo delle configurazioni, le configurazioni create in precedenza non sono più considerate. È possibile reimpostare il riutilizzo configurazioni se la DBA o il ciclo di lavorazione è stato modificato, ma nessun attributo correlato è stato modificato. È possibile reimpostare il riutilizzo configurazioni nella scheda dettaglio **Generale** del componente.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]