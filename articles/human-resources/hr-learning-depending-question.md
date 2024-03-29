---
title: Fare una domanda in base alla risposta della domanda precedente
description: Le domande condizionali consentono di specificare la domanda successiva da presentare a un intervistato, in base alla risposta alla domanda precedente.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree, HcmLearningWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b2f7d55b577478f3156a8299fc2f827ab3bb60f1
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686084"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a>Fare una domanda in base alla risposta della domanda precedente


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Le domande condizionali consentono di specificare la domanda successiva da presentare a un intervistato, in base alla risposta alla domanda precedente. Ad esempio, se si chiede "Preferisce caffè o tè?", una domanda successiva logica può essere determinata dalla scelta della risposta caffè o tè da parte dell'intervistato. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="find-the-existing-questionnaire"></a>Individuare il questionario esistente
1. Vai a **Questionario** > **Progettazione** > **Questionari**.
2. Nell'elenco selezionare il questionario WorkFH.

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a>Aggiungere tutte le domande e le domande secondarie al questionario
1. Fai clic su **Domande**.
2. Fare clic su **Nuovo**.
3. Nel campo **Domanda** seleziona il numero di domanda 00016.
4. Nell'elenco trovare e selezionare il record desiderato.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Fare clic su **Salva**.
7. Chiudere la pagina.

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a>Impostare la sequenza del questionario su Condizionale e rendere la domanda dipendente dalla domanda appropriata
1. Fare clic su **Modifica**.
2. Espandere la sezione **Impostazione**.
3. Nel campo **Ordine domande** seleziona "Condizionale".
4. Fai clic sulla domanda **Condizionale**.
5. Nella struttura selezionare "Domande\Spiegare i motivi della risposta precedente".
6. Nel campo **Domanda primaria** il numero di domanda 00009.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Nel campo **Risposta** immetti l'ID della sequenza di risposta dell'opzione di risposta da cui si desidera che la domanda sia dipendente. Ad esempio, immettere 1 per la prima opzione di risposta.
9. Fare clic su **Salva**.
10. Nella struttura selezionare "Domande\Sono pagato equamente per il lavoro che svolgo".
    * Si noti che la struttura delle domande viene aggiornata per visualizzare la dipendenza.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
