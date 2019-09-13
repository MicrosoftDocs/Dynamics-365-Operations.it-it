---
title: Impostare la riallocazione articolo per prelievo breve
description: In questa procedura viene illustrato come consentire agli addetti al magazzino di individuare rapidamente le ubicazioni alternative se non è disponibile scorte sufficienti alla'ubicazione a cui sono stati indirizzati.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 964302cb7e7835b6e619602ac7165c9e7adbcefb
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916762"
---
# <a name="set-up-short-picking-item-reallocation"></a>Impostare la riallocazione articolo per prelievo breve

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come consentire agli addetti al magazzino di individuare rapidamente le ubicazioni alternative se non è disponibile scorte sufficienti alla'ubicazione a cui sono stati indirizzati. È possibile utilizzare un processo di riallocazione automatica, in cui vengono utilizzate le direttive ubicazione per recuperare le merci se sono disponibili in un'altra ubicazione. In alternativa, quando si usa la riallocazione manuale, viene visualizzato un elenco di ubicazioni con la quantità disponibile sul dispositivo mobile, in modo da consentire all'addetto al magazzino di selezionare l'ubicazione da cui utilizzare le scorte. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="set-up-work-exceptions"></a>Imposta eccezioni lavoro
1. Nel **pannello di navigazione**, andare a **Gestione magazzino > Impostazione > Lavoro > Eccezioni lavoro**.
2. Fare clic su **Nuovo**. È possibile definire più eccezioni lavoro con diversi criteri di riallocazione articolo per consentire all'addetto al magazzino di scegliere uno in base alle esigenze di spedizione in corso di elaborazione.  
3. Nel campo **Codice di eccezione lavoro**, immettere un valore. Dare all'eccezione lavoro un titolo per indicare per cosa è utilizzata. Ad esempio, Prelievo manuale breve.  
4. Digitare un valore nel campo **Descrizione**
5. Nel campo **Tipo di eccezione** selezionare "Prelievo in difetto".
6. Selezionare la casella di controllo **Correggi magazzino**. Questa opzione indica che l'inventario verrà rettificato automaticamente su 0 all'ubicazione del prelievo breve.  
7. Nel campo **Codice tipo correzione predefinito**, immettere o selezionare un valore. Ad esempio, in USMF è possibile selezionare 'Remove Res Adj Out'.  
8. Nel campo **Riallocazione articolo** selezionare "Manuale". Se si seleziona Manuale o Automatico e manuale, l'addetto al magazzino deve essere abilitato per utilizzare la riallocazione manuale.  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>Impostare un lavoratore per utilizzare la riallocazione manuale degli articoli
1. Chiudere la pagina.
2. Nel **pannello di navigazione**, andare a **Gestione magazzino > Impostazione > Lavoro > Lavoratore**.
3. Fare clic su **Modifica**.
4. Nell'elenco selezionare il lavoratore 24.
5. Espandere la Scheda dettaglio **Lavoro**.
6. Selezionare "Sì" nel campo **Consenti riallocazione manuale articolo**.

