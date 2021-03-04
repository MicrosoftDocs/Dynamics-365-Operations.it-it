---
title: Creare ed elaborare una conformità
description: In questo argomento viene descritto come eseguire la gestione di non conformità, in base a un ordine di controllo qualità esistente.
author: perlynne
manager: tfehr
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8bf20ed737707b7cf99023e3c78489caf4a68eab
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431412"
---
# <a name="create-and-process-a-conformance"></a>Creare ed elaborare una conformità

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come eseguire la gestione di non conformità, in base a un ordine di controllo qualità esistente. È possibile eseguire questa registrazione nella società dimostrativa USMF e utilizzare i valori suggeriti. In genere, questa procedura viene eseguita da un addetto al controllo qualità.  Come prerequisito, completare le istruzioni in [Verificare la qualità delle merci](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md). Per elaborare l'approvazione di una non conformità, l'utente che esegue la registrazione attività deve avere un valore "Nome" assegnato nella pagina Utenti. Per utilizzare le note del documento, l'utente deve inoltre avere Gestione documenti attivata nelle opzioni utente.


## <a name="select-a-quality-order"></a>Selezionare un ordine di controllo qualità.
1. Nel pannello di navigazione andare a **Moduli > Gestione articoli > Attività periodiche > Gestione qualità > Ordini di controllo qualità**.
2. Nell'elenco, selezionare l'ordine di controllo qualità creato in [Verificare la qualità delle merci](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).  

## <a name="create-a-nonconformance"></a>Creare una non conformità
1. Nel riquadro azioni, seleziona **Informazioni**.
2. Selezionare **Non conformità**.
3. Selezionare **Nuovo**.
4. Nel menu a discesa del campo **Tipi di problema**, selezionare il problema individuato durante il processo di ispezione.  
5. Selezionare **OK**.

## <a name="approvereject-a-nonconformance"></a>Approvare/respingere una non conformità
1. Selezionare **Funzioni**.
2. Selezionare **Approva non conformità**. Per questo esempio, approvare la non conformità. Le non conformità approvate possono essere associate alle operazioni correlate per la registrazione del lavoro che viene eseguito nell'ambito della gestione di non conformità e, come in questo argomento, l'elaborazione della gestione della correzione.  
3. Selezionare **Sì**.

## <a name="create-a-correction-action"></a>Creare un'azione correttiva
1. Selezionare **Correzioni**.
2. Selezionare **Nuovo**.
3. Nel campo **Numero dipendente** della nuova riga, selezionare il record desiderato dal menu a discesa.
4. Fare clic su **Seleziona**.
5. Selezionare **Allega**. Creare una nota sulla correzione. Per questo esempio l'azione è di contattare il fornitore per discutere il caso di non conformità.  
6. Selezionare **Nuovo**.
7. Selezionare **Nota**. A seconda dell'impostazione del report, i tipi di documento possono essere stampati nei report correlati alla gestione di non conformità.  
8. Digitare un valore nel campo **Descrizione**
9. Chiudere la pagina.

## <a name="maintain-a-correction"></a>Gestire una correzione
1. Selezionare **Contrassegna come completata**.
2. Selezionare **OK**.
3. Chiudere la pagina.

## <a name="close-a-nonconformance"></a>Chiudere una non conformità
1. Selezionare **Funzioni**.
2. Selezionare **Chiudi non conformità**.
3. Selezionare **Sì**.
4. Chiudere le pagine.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]