---
title: "Creare ed elaborare una conformità"
description: "Utilizzare questa procedura per eseguire la gestione di non conformità, in base a un ordine di controllo qualità esistente."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e5187c44aac881273900b2fc0ca91045a65cd838
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-and-process-a-conformance"></a>Creare ed elaborare una conformità

[!include [task guide banner](../../includes/task-guide-banner.md)]

Utilizzare questa procedura per eseguire la gestione di non conformità, in base a un ordine di controllo qualità esistente. È possibile eseguire questa registrazione nella società dimostrativa USMF e utilizzare i valori suggeriti. In genere, questa procedura viene eseguita da un addetto al controllo qualità.  Come prerequisito, eseguire la registrazione attività "Verificare la qualità delle merci". Per elaborare l'approvazione di una non conformità, l'utente che esegue la registrazione attività deve avere un valore "Nome" assegnato alla pagina Utenti. Per utilizzare le note del documento, l'utente deve inoltre avere Gestione documenti attivata nelle opzioni utente.


## <a name="select-a-quality-order"></a>Selezionare un ordine di controllo qualità.
1. Scegliere Ordini di controllo qualità.
2. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare l'ordine di controllo qualità creato tramite la registrazione attività "Verificare la qualità delle merci".  

## <a name="create-a-nonconformance"></a>Creare una non conformità
1. Fare clic su Richieste di informazioni.
2. Fare clic su Non conformità.
3. Fare clic su Nuovo.
4. Nel campo Tipo di problema fare clic sul pulsante a discesa per aprire la ricerca.
    * Selezionare il problema che è stato rilevato durante il processo di ispezione.  
5. Nel campo Tipo di problema fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco trovare e selezionare il record desiderato.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Fare clic su OK.

## <a name="approvereject-a-nonconformance"></a>Approvare/respingere una non conformità
1. Fare clic su Funzioni.
2. Fare clic su Approva non conformità.
    * Per questo esempio, approvare la non conformità. Le non conformità approvate possono essere associate alle operazioni correlate per la registrazione del lavoro che viene eseguito nell'ambito della gestione di non conformità e, come in questa registrazione di attività, l'elaborazione della gestione della correzione.  
3. Fare clic su Sì.

## <a name="create-a-correction-action"></a>Creare un'azione correttiva
1. Fare clic su Correzioni.
2. Fare clic su Nuovo.
3. Nell'elenco contrassegnare la riga selezionata.
4. Nel campo Numero dipendente fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Fare clic su Seleziona.
7. Fare clic su Allega.
    * Creare una nota sulla correzione. Per questo esempio l'azione è di contattare il fornitore per discutere il caso di non conformità.  
8. Fare clic su Nuovo.
9. Fare clic su Nota.
    * A seconda dell'impostazione del report, i tipi di documento possono essere stampati nei report correlati alla gestione di non conformità.  
10. Nel campo Descrizione digitare un valore.
11. Chiudere la pagina.

## <a name="maintain-a-correction"></a>Gestire una correzione
1. Fare clic su Contrassegna come completata.
2. Fare clic su OK.
3. Chiudere la pagina.

## <a name="close-a-nonconformance"></a>Chiudere una non conformità
1. Fare clic su Funzioni.
2. Fare clic su Chiudi non conformità.
3. Fare clic su Sì.
4. Chiudere la pagina.
5. Chiudere la pagina.

