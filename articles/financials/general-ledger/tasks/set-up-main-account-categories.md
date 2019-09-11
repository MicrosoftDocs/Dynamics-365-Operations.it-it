---
title: Impostare le categorie di conti principali
description: In questo argomento viene illustrato come impostare le categorie di conti principali in Dynamics 365 for Finance and Operations.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4d37deb0bda225abb111375d8a00ae22d9e0c4fe
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916070"
---
# <a name="set-up-main-account-categories"></a>Impostare le categorie di conti principali

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questo argomento viene illustrato come impostare le categorie di conti principali in Dynamics 365 for Finance and Operations. Le categorie di conti principali sono utilizzate per i report predefiniti nei report finanziari e in Power BI. Le categorie di conti principali create per impostazione predefinita possono essere rinominate ma non eliminate. Categorie di conti aggiuntive possono essere create e utilizzate a fini di report e analisi. In questo argomento viene utilizzata la società dimostrativa USMF.

## <a name="create-a-main-account-category"></a>Creare una categoria di conti principali
1. Nel pannello di navigazione andare a **Moduli > Contabilità generale > Piano dei conti > Conti > Categorie di conti principali**.
2. Selezionare **Nuovo**.
3. Immettere un nome univoco nel campo **Categoria di conti principali**.
4. Nel campo **Descrizione** immettere una descrizione per la categoria di conti principali.
5. Nel campo **Tipo di conto principale** selezionare il tipo di conto principale da collegare alla categoria.

## <a name="link-main-accounts-to-account-category"></a>Collegare conti principali a una categoria di conti
1. Fare clic su **Collega conti principali**.
2. Nell'elenco, selezionare i conti principali da assegnare alla categoria di conti principali selezionando le caselle nella colonna **Collegato**. Assegnare i conti principali a una categoria di conti principali aggregherà i saldi dei conti quando la categoria viene utilizzata per i report finanziari e l'analisi.  
3. Selezionare o deselezionare l'opzione **Collegato** per scegliere i conti principali.
4. Selezionare **OK**.
5. Selezionare **Sì**.
