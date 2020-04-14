---
title: Creare un pagamento IVA
description: Il processo di liquidazione e registrazione liquida i saldi IVA nei conti IVA e li registra in contropartita nel conto di liquidazione IVA per un periodo specifico.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99059a8e5d6f4bf125266ad2a98cb73751529e6b
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139925"
---
# <a name="create-a-sales-tax-payment"></a>Creare un pagamento IVA

[!include [banner](../../includes/banner.md)]

Il processo di liquidazione e registrazione liquida i saldi IVA nei conti IVA e li registra in contropartita nel conto di liquidazione IVA per un periodo specifico.

1. Passare a Imposta > Dichiarazioni > IVA > Liquida e registra IVA.
2. Nel campo Periodo di liquidazione fare clic sul pulsante a discesa per aprire la ricerca.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Immettere una data nel campo Dal.
    * Se l'opzione Includi correzioni non è selezionata nella pagina Parametri di contabilità generale, la liquidazione può essere elaborata per versioni diverse. Originale è la prima liquidazione per un intervallo periodico e può essere elaborata una sola volta per un intervallo periodico. Le ultime correzioni sistemeranno le transazioni IVA registrate dopo che la versione originale è stata creata.   
5. Nel campo Data della transazione immettere una data.
6. Fare clic su OK.

