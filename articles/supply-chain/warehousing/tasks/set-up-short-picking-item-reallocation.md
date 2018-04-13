--- 
title: Impostare la riallocazione articolo per prelievo breve
description: "In questa procedura viene illustrato come consentire agli addetti al magazzino di individuare rapidamente le ubicazioni alternative se non è disponibile scorte sufficienti alla'ubicazione a cui sono stati indirizzati."
author: YuyuScheller
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b67965b6c8641b5d91ab3c5b0a7a7fd28a07cba6
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-short-picking-item-reallocation"></a>Impostare la riallocazione articolo per prelievo breve

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come consentire agli addetti al magazzino di individuare rapidamente le ubicazioni alternative se non è disponibile scorte sufficienti alla'ubicazione a cui sono stati indirizzati. È possibile utilizzare un processo di riallocazione automatica, in cui vengono utilizzate le direttive ubicazione per recuperare le merci se sono disponibili in un'altra ubicazione. In alternativa, quando si usa la riallocazione manuale, viene visualizzato un elenco di ubicazioni con la quantità disponibile sul dispositivo mobile, in modo da consentire all'addetto al magazzino di selezionare l'ubicazione da cui utilizzare le scorte. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="set-up-work-exceptions"></a>Imposta eccezioni lavoro
1. Passare a Gestione magazzino > Impostazione > Lavoro > Eccezioni lavoro.
2. Fare clic su Nuovo.
    * È possibile definire più eccezioni lavoro con diversi criteri di riallocazione articolo per consentire all'addetto al magazzino di scegliere uno in base alle esigenze di spedizione in corso di elaborazione.  
3. Nel campo Codice di eccezione lavoro, immettere un valore.
    * Dare all'eccezione lavoro un titolo per indicare per cosa è utilizzata. Ad esempio, Prelievo manuale breve.  
4. Nel campo Descrizione digitare un valore.
5. Nel campo Tipo di eccezione selezionare 'Prelievo in difetto'.
6. Selezionare la casella di controllo Correggi magazzino.
    * Questa opzione indica che l'inventario verrà rettificato automaticamente su 0 all'ubicazione del prelievo breve.  
7. Nel campo Codice tipo correzione predefinito, immettere o selezionare un valore.
    * Ad esempio, in USMF è possibile selezionare 'Remove Res Adj Out'.  
8. Nel campo Riallocazione articolo selezionare 'Manuale'.
    * Se si seleziona Manuale o Automatico e manuale, l'addetto al magazzino deve essere abilitato per utilizzare la riallocazione manuale.  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>Impostare un lavoratore per utilizzare la riallocazione manuale degli articoli
1. Chiudere la pagina.
2. Andare a Gestione magazzino > Impostazioni > Lavoratore.
3. Fare clic su Modifica.
4. Nell'elenco selezionare il lavoratore 24.
5. Espandere la sezione Lavoro.
6. Selezionare Sì nel campo Consenti riallocazione manuale articolo.


