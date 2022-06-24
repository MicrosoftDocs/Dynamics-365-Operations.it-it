---
title: Creare un budget originale e annullare le voci di budget preliminari nel settore pubblico
description: Questo articolo fornisce informazioni su come creare e stornare una voce di budget originale utilizzando il modello di budget e valori di dimensione con importi di budget preliminari.
author: twheeloc
ms.date: 02/14/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1efb6363be881b0a35f356c2cb2334e5a37e43ae
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848406"
---
# <a name="create-an-original-budget-and-then-reverse-preliminary-budget-entries-in-the-public-sector"></a>Creare un budget originale e annullare le voci di budget preliminari nel settore pubblico

[!include [banner](../../includes/banner.md)]

Quando si crea una voce di budget originale e si utilizzano il modello di budget e i valori di dimensione che contengono gli importi di budget preliminari, gli importi di budget preliminari possono essere annullati. Questa procedura è stata creata utilizzando i dati della società di dati dimostrativi PSUS nella partizione del settore pubblico.

1. Andare a **Impostazione budget > Voci del registro di budget**.
2. Fare clic su **Nuovo**.
3. Nel campo **Modello di budget** fare clic sul pulsante a discesa per aprire la ricerca.
4. Trovare e selezionare il record desiderato nell'elenco.
5. Nel campo **Codice budget** fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco, fare clic su **Budget originale**.
7. Fare clic su **Salva**.
8. Fare clic su **Aggiungi riga**.
9. Facoltativo: se si desidera modificare la data presente nell'intestazione, immettere una nuova data. Questa data determina il periodo fiscale in cui verrà registrato il budget.
10. Nel campo **Struttura dei conti** fare clic sul pulsante a discesa per aprire la ricerca.
11. Trovare e selezionare il record desiderato nell'elenco.
12. Nel campo **Valori di dimensione** specificare i valori desiderati.
13. Nel campo **Importo** immettere un numero.
14. Nel campo **Valuta** fare clic sul pulsante a discesa per aprire la ricerca.
15. Nell'elenco fare clic sul collegamento nella riga selezionata.
16. Fare clic su **Salva**.
17. Fare clic su **Aggiorna saldi budget**.
    * Facoltativo: è possibile selezionare l'opzione per **annullare il budget preliminare**. Si noti che è possibile annullare tutte le voci di budget preliminare o solo le voci di budget preliminare con il codice budget specificato.  
    * Per effettuare selezioni facoltative, fare clic sull'icona **Sblocca** nella parte superiore della pagina.  
18. Fare clic su **Aggiorna**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
