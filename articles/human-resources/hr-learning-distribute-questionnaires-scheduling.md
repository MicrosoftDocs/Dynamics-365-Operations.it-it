---
title: Distribuire questionari mediante programmazione
description: La programmazione dei questionari consente di pianificare e distribuire i questionari a più intervistati.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0448a7ebe802a961c8c1296ef57d12ea22e4ec27
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009567"
---
# <a name="distribute-questionnaires-using-scheduling"></a>Distribuire questionari mediante programmazione

La programmazione dei questionari consente di pianificare e distribuire i questionari a più intervistati. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.

## <a name="create-a-questionnaire-schedule"></a>Creare una programmazione per il questionario

1. Andare a Questionario > Distribuisci > Programmazioni questionario.

2. Fare clic su Nuovo.

3. Digitare un valore nel campo Programmazione.

4. Nel campo Descrizione digitare un valore.
    * Impostare la programmazione su Anonimo se le risposte devono essere registrate senza nomi associati alla risposta.  
    * L'attivazione dei risultati anonimi deve essere impostata prima nei parametri HR.  

5. Nel campo Tipo selezionare il tipo di pianificazione.  In questo esempio useremo il tipo soddisfazione.

6. Nell'elenco trovare e selezionare il record desiderato.

7. Nell'elenco fare clic sul collegamento nella riga selezionata.

8. Nel campo Data immettere una data.

9. Espandere la sezione Posta elettronica per dipendente self-service.

10. Digitare un valore nel campo Oggetto.

    * Esempio: Questionario disponibile  

11. Nel campo Testo digitare il corpo del messaggio di posta elettronica. Nota, la variabile può essere utilizzata per sostituire valori nel sistema.

    * Esempio: Gentile %P%, effettui l'accesso a Dynamics AX, Dipendente self-service per completare il questionario sulla salute della forza lavoro.  Contoso  

12. Fare clic su Salva.

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a>Utilizzare i Dettagli impostazione per selezionare i questionari a cui rispondere nonché eventuali query da utilizzare per selezionare gli intervistati.

1. Fare clic su Dettagli impostazione.

2. Nell'elenco selezionare una query da utilizzare per cercare nel sistema gli intervistati per il questionario.

    * Esempio: Lavoratori  

3. Fare clic su Visualizza o modifica query per selezionare persone specifiche o modificare la query per cercare le persone che corrispondono ai criteri specifici.

    * Si noti che tutti gli intervistati devono essere utenti nel sistema.  

4. Nell'elenco contrassegnare la riga per Persona

5. Nel campo Criteri immettere o selezionare un valore.

    * Selezionare Julia Funderburk  

6. Nell'elenco, selezionare Julia Funderburk

7. Fare clic su OK.

8. Fare clic sulla scheda Questionari.

9. Nella struttura espandere il nodo per il tipo di questionario sulla soddisfazione.

10. Nella struttura, selezionare 'Workforce Health Assessment'.

11. Fare clic su OK.

12. Fare clic su Sessione di risposte pianificata.

    * Si noti che la Sessione di risposte pianificata è stata creata per ciascun utente selezionato/sottoposto a query.  

13. Chiudere la pagina.

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a>Avviare la programmazione del questionario per rendere disponibile il questionario da completare agli intervistati.

1. Fare clic su Funzioni.

2. Fare clic su Inizia.

3. Fare clic su OK.

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a>Inviare un messaggio di posta elettronica per informare gli intervistati del questionario disponibile.

1. Fare clic su Funzioni.

2. Fare clic su Invia posta elettronica.

3. Scegliere Annulla.

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a>Utilizzare Sessioni di risposte pianificate per monitorare chi deve completare il questionario.

1. Fare clic su Sessione di risposte pianificata.

    * Eliminare qualsiasi sessione di risposte pianificata rimanente quando si è pronti per terminare la sessione programmata.  

2. Fare clic su Elimina.

3. Fare clic su Sì.

4. Chiudere la pagina.

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a>Terminare la programmazione quando tutti gli intervistati hanno completato il questionario e/o le sessioni di risposta pianificate sono state eliminate.

1. Fare clic su Funzioni.
2. Fare clic su Fine.
3. Fare clic su OK.

