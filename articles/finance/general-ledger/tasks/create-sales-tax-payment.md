---
title: Creare un pagamento IVA
description: La procedura di liquidazione e registrazione liquida i saldi IVA nei conti IVA e li registra in contropartita nel conto di liquidazione IVA per un periodo specifico.
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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9523ef75953bdca36f509f596c51c08b12b3fdb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254465"
---
# <a name="create-a-sales-tax-payment"></a>Creare un pagamento IVA

[!include [banner](../../includes/banner.md)]

La procedura di liquidazione e registrazione liquida i saldi IVA nei conti IVA e li registra in contropartita nel conto di liquidazione IVA per un periodo specifico.

1. Vaia a **Imposta > Dichiarazioni > IVA > Liquida e registra IVA**.
2. Nel campo **Periodo di liquidazione** fai clic sul pulsante a discesa per aprire la ricerca.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Immettere una data nel campo **Dal**.
    * Se non selezioni l'opzione **Includi correzioni** nella pagina **Parametri di contabilità generale**, la liquidazione può essere elaborata per versioni diverse. Originale è la prima liquidazione per un intervallo periodico e può essere elaborata una sola volta per un intervallo periodico. Le ultime correzioni sistemeranno le transazioni IVA registrate dopo che la versione originale è stata creata.   
5. Nel campo **Data della transazione** immettere una data.
6. Fare clic su **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]