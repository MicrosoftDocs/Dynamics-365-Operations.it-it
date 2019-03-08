---
title: Verificare la qualità delle merci
description: Questa procedura illustra come elaborare un ordine di controllo qualità.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9e9d750f116db62519ac7148f19bf62050430e9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "315431"
---
# <a name="inspect-the-quality-of-goods"></a>Verificare la qualità delle merci

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura illustra come elaborare un ordine di controllo qualità. È possibile eseguire questa guida nella società di dati dimostrativi USMF. Prima di iniziare questa procedura di esempio, è necessario confermare l'ordine fornitore "000016" e registrare un'entrata prodotti. In questo modo verrà automaticamente creato un ordine di controllo qualità. Le ispezioni di controllo qualità sono in genere effettuati da un addetto al controllo qualità.


## <a name="select-a-quality-order"></a>Selezionare un ordine di controllo qualità.
1. Andare a Gestione articoli > Attività periodiche > Gestione qualità > Ordini di controllo qualità.
2. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare l'ordine di controllo qualità creato prima di aver avviato questa procedura.  

## <a name="record-test-results"></a>Registrazione dei risultati dei test
1. Fare clic su Risultati.
2. Fare clic su Modifica.
3. Nel campo Quantità risultante immettere un numero.
4. Nell'elenco contrassegnare la riga selezionata.
5. Nel campo Risultato fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco trovare e selezionare il record desiderato.
    * In questo esempio il risultato è basato su un risultato predefinito. In genere viene registrato un risultato del test più specifico, ad esempio una dimensione o un altro valore simile.  
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Fare clic su Salva.
9. Chiudere la pagina.

## <a name="validate-the-quality-order"></a>Convalida l'ordine di controllo qualità
1. Fare clic su Convalida.
2. Nel campo Convalidato da fare clic sul pulsante a discesa per aprire la ricerca.
    * Selezionare l'utente che esegue l'ispezione.  
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Fare clic su Seleziona.
5. Fare clic su OK.
6. Chiudere la pagina.

