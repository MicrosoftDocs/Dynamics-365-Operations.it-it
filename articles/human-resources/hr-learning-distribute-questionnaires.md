---
title: Distribuire e programmare questionari
description: In questo articolo viene illustrato come distribuire i questionari che si progettano, in modo che siano disponibili per la persona o il gruppo di persone che li completeranno.
author: andreabichsel
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0329b80615eed6efcc22bb0b140970988f5c306a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419259"
---
# <a name="distribute-and-schedule-questionnaires"></a>Distribuire e programmare questionari

In questo articolo viene illustrato come distribuire i questionari che si progettano, in modo che siano disponibili per la persona o il gruppo di persone che li completeranno. 

Sono disponibili più metodi per distribuire un questionario:

-   Contrassegnare il questionario come attivo. Il questionario è così attivo e disponibile per tutti i dipendenti a meno che un gruppo di questionari non venga impostato per limitare l'accesso al questionario.
-   Assegnare i diritti a un gruppo di questionari. Il questionario è quindi disponibile per tutti i membri del gruppo selezionato.
-   Creare sessioni di risposte pianificate. Il questionario è quindi disponibile solo per una persona specifica.
-   Crea una programmazione. Il questionario può quindi essere disponibile per più persone.

## <a name="marking-a-questionnaire-as-active"></a>Contrassegnare il questionario come attivo

Se si imposta il campo **Attivo** su **Sì** nella pagina **Questionari**, si rende il questionario disponibile a tutti i dipendenti. Gli intervistati possono completare il questionario più volte. Questa funzionalità è utile se si desidera raccogliere costantemente commenti nell'arco dell'anno. Ad esempio, è possibile effettuare un questionario che i dipendenti utilizzano per fornire un riscontro sul servizio mensa nel self-service.

## <a name="questionnaire-groups"></a>Gruppi di questionari

È possibile impostare gruppi di questionari e quindi includere gli intervistati a cui un questionario deve essere distribuito. 

È possibile creare gruppi di questionari dalle seguenti pagine:

-   **Gruppi di questionari**: solo gli utenti inclusi in un gruppo di questionari possono compilare un questionario selezionato. Ad esempio, se il gruppo di destinatari desiderato è quello dei terzisti, è possibile creare un gruppo di questionari specifico di tali intervistati.
-   **Membri gruppo di questionari**: è possibile aggiungere le persone ai gruppi di questionario.

Per assegnare un gruppo di questionari a un questionario, nella pagina **Questionari** fare clic su **Diritti dell'utente**. Dopo che il questionario è stato salvato come attivo, i membri del gruppo di questionari possono completarlo. Questa funzionalità è utile se si desidera verificare un questionario su un gruppo di persone prima di distribuirlo a un gruppo più ampio o se si desidera dedicare un questionario a un pubblico molto specifico.

## <a name="planned-answer-sessions-in-a-questionnaire"></a>Sessioni di risposte pianificate in un questionario

Le sessioni di risposte pianificate sono questionari progettati e selezionati per gli intervistati. 

> [!NOTE]
> Prima di impostare le sessioni di risposte pianificate, è necessario progettare un questionario. 

Nella pagina **Sessione di risposte pianificata** è possibile creare una sessione di risposte pianificata per un singolo dipendente. Nell'elenco della pagina sono visualizzati tutti i questionari pianificati. 

Le sessioni di risposte pianificate vengono inoltre utilizzate nella pagina **Programmazioni questionari**, dove è possibile pianificare questionari per più persone:

-   Dipendenti
-   Partecipanti al corso
-   Unità organizzative

Ogni persona può rispondere al questionario una sola volta.

## <a name="scheduling-a-questionnaire"></a>Programmazione di un questionario

Se si desidera è possibile programmare un questionario per più intervistati.

### <a name="planning-types"></a>Tipi di pianificazione

I tipi di pianificazione sono necessari se si desidera programmare le sessioni di risposte pianificate per più intervistati. I tipi di pianificazione vengono utilizzati per classificare le programmazioni del questionario. Ad esempio, è possibile programmare i questionari per i seguenti scopi:

-   Valutazione
-   Rilevamento
-   Test

È possibile specificare i tipi di pianificazione per una programmazione del questionario nella pagina **Programmazioni questionari**.

### <a name="reference-types-for-questionnaire"></a>Tipi di riferimento per questionario

È possibile utilizzare i tipi di riferimento per immettere i criteri per gli intervistati che è possibile selezionare quando si programma un questionario. 

Utilizzare la pagina **Tipi di riferimento** per impostare i tipi di riferimento per un questionario. Ogni tipo di riferimento corrisponde a una tabella in Microsoft Dynamics 365 Finance. Quando si creano programmazioni questionari, è possibile specificare i singoli record della tabella o un intervallo di record a cui verrà associato il questionario. 

Ad esempio, se si seleziona la tabella Corsi, è possibile decidere il corso specifico a cui il questionario si riferirà. Se si imposta un riferimento per la tabella Corsi, verranno resi disponibili alcuni campi e pulsanti nel modulo **Corsi**.

### <a name="questionnaire-schedules"></a>Programmazioni questionari

È possibile utilizzare le programmazioni questionari per generare più sessioni di risposte pianificate per un gruppo di utenti, in base a un tipo di riferimento. Creare una programmazione nella pagina **Programmazioni questionari**. Selezionare il tipo di pianificazione per classificare la programmazione e selezionare anche il tipo di riferimento da utilizzare per eseguire query nel sistema su utenti specifici. Ad esempio, se si imposta il tipo di riferimento sulla tabella Corsi, è possibile selezionare un corso specifico nel campo **Riferimento**. 

Fare clic su **Dettagli impostazione** per selezionare il questionario e altri criteri. Specificare, ad esempio, il nome dell'istruttore come criterio se il questionario è una valutazione dell'istruttore. Dopo aver immesso i dettagli di impostazione, il sistema genera sessioni di risposte pianificate per gli utenti che sono inclusi nella query. 

Fare clic su **Sessioni di risposte pianificate** per visualizzare le sessioni di risposte per la programmazione. È possibile quindi creare manualmente sessioni di risposte pianificate aggiuntive o eliminare le sessioni di risposte pianificate a cui non sono state fornite risposte. 

Fare clic su **Funzioni** &gt; **Inizio** per rendere disponibile il questionario agli utenti nelle sessioni di risposte pianificate correlate. Fare clic su **Risposte** per visualizzare le risposte completate nel questionario. Si può scegliere di copiare le impostazioni di programmazione questionario, le sessioni di risposte pianificate e le risposte in una nuova programmazione questionario.

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a>Informare gli intervistati dei questionari disponibili
Quando viene distribuito un questionario, è necessario avvisare gli intervistati che i questionari sono disponibili. 

### <a name="notifying-respondents-about-a-planned-answer-session"></a>Informare gli intervistati su una sessione di risposte pianificata

Se si utilizza una sessione di risposte pianificata, è necessario informare direttamente la persona, ad esempio per telefono o posta elettronica.

### <a name="notifying-respondents-about-a-scheduling"></a>Informare gli intervistati su una programmazione

Utilizzare la pagina **Programmazioni questionari** per preparare e inviare un messaggio di posta elettronica a tutti gli intervistati a cui è stato assegnato il questionario. Immettere il testo del messaggio di posta elettronica nella scheda **Posta elettronica per dipendente self-service**. Dopo che la programmazione è stata avviata, fare clic su **Funzioni** &gt; **Invia posta elettronica** per generare e inviare il messaggio di posta elettronica agli intervistati. Gli intervistati possono quindi accedere al sito Web e completare il questionario. 

> [!NOTE]
> Affinché si possa utilizzare la funzionalità di posta elettronica, è necessario che l'amministratore IT immetta le impostazioni di posta elettronica nella pagina **Parametri posta elettronica**.

## <a name="ending-a-scheduled-questionnaire"></a>Completamento di un questionario programmato

È possibile concludere un questionario programmato dopo che tutti gli intervistati hanno completato le sessioni di risposte assegnate. In seguito al completamento di un questionario programmato, non è possibile copiarne le impostazioni in una nuova programmazione. 

> [!NOTE]
>   Se uno o più intervistati non hanno completato il questionario, ma si desidera comunque completare la programmazione, è necessario innanzitutto eliminare gli intervistati in questione dall'elenco presente nella pagina **Sessione di risposte pianificata**. Sarà quindi possibile completare la programmazione.

## <a name="completing-questionnaires"></a>Completamento di questionari

Dopo che è stato progettato e distribuito, un questionario può essere completato dagli intervistati selezionati. È possibile completare i questionari disponibili da due posizioni:

-   Nel pannello di navigazione fare clic su **Questionari** &gt; **Distribuisci** &gt; **Compilare un questionario**.
-   In Dipendente self-service, fare clic su **Questionari da completare**.

I questionari possono essere messi a disposizione di utenti o gruppi di utenti specifici o di tutti gli utenti in una rete.




[!INCLUDE[footer-include](../includes/footer-banner.md)]