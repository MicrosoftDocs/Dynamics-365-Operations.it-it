---
title: Distribuire e completare un questionario
description: In questo argomento viene descritto come distribuire questionari la pianificazione, in modo che disponibili per la persona o del gruppo di persone che li completeranno.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a76ec0cd86bcc810b42ae3cd8efd8a584e6c4da3
ms.openlocfilehash: 8e09c6b042d557e3b2d608fb5e278169fc3c1d88
ms.lasthandoff: 03/31/2017


---

# <a name="distribute-and-complete-a-questionnaire"></a>Distribuire e completare un questionario

In questo argomento viene descritto come distribuire questionari la pianificazione, in modo che disponibili per la persona o del gruppo di persone che li completeranno. 

Sono disponibili più metodi per distribuire un questionario:

-   Contrassegnare il questionario come attivo. Il questionario è così attivo e disponibile per tutti i dipendenti a meno che un gruppo di questionari non venga impostato per limitare l'accesso al questionario.
-   Assegnare i diritti a un gruppo di questionari. Il questionario è quindi disponibile per tutti i membri del gruppo selezionato.
-   Creare sessioni di risposte pianificate. Il questionario è quindi disponibile solo per una persona specifica.
-   Crea una programmazione. Il questionario può quindi essere disponibile per più persone.

## <a name="marking-a-questionnaire-as-active"></a>Contrassegnare il questionario come attivo
** La attivo ** il campo su Sì ** ** ** questionari ** nella pagina, rendere disponibile il questionario per tutti i dipendenti completare. Gli intervistati possono completare i più volte del questionario. Questa funzionalità è utile se si desidera raccogliere il riscontro continuo durante l'anno. Ad esempio, è possibile effettuare un questionario che i dipendenti utilizzano per fornire un riscontro sul servizio mensa nel self-service.

## <a name="questionnaire-groups"></a>Gruppi di questionari
È possibile impostare gruppi di questionari e quindi includere gli intervistati a cui un questionario deve essere distribuito. 

È possibile creare gruppi di questionari dalle seguenti pagine:

-   **Gruppi di questionari**: solo gli utenti inclusi in un gruppo di questionari possono compilare un questionario selezionato. Ad esempio, se il gruppo di destinatari desiderato è quello dei terzisti, è possibile creare un gruppo di questionari specifico di tali intervistati.
-   **Membri gruppo di questionari**: è possibile aggiungere le persone ai gruppi di questionario.

Per assegnare un gruppo di questionari a un questionario, ** questionari ** alla pagina, fare clic su ** diritti utente **. Dopo che il questionario viene salvato come attivo, i membri del gruppo di questionari possono completare il questionario. Questa funzionalità è utile se si desidera verificare un questionario su un gruppo di persone Seleziona lo stato del rotoliate uscita a un maggiore gruppo, o se si desidera definire un questionario a un lavoratore specifico pubblico.

## <a name="planned-answer-sessions-in-a-questionnaire"></a>Sessioni di risposte pianificate in un questionario
Le sessioni di risposte pianificate sono questionari progettati e selezionati per gli intervistati. 

**Nota:** Prima di impostare le sessioni di risposte pianificate, è necessario progettare un questionario. 

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

Utilizzare la pagina **Tipi di riferimento** per impostare i tipi di riferimento per un questionario. Ogni tipo di riferimento corrisponde a una tabella in Microsoft Dynamics 365 per le operazioni. Quando si creano programmazioni questionari, è possibile specificare i singoli record della tabella o un intervallo di record a cui verrà associato il questionario. 

Ad esempio, se si seleziona la tabella Corsi, è possibile decidere il corso specifico a cui il questionario si riferirà. Se si imposta un riferimento per la tabella Corsi, verranno resi disponibili alcuni campi e pulsanti nel modulo **Corsi**.

### <a name="questionnaire-schedules"></a>Programmazioni questionari

È possibile utilizzare la programmazione del questionario per generare le sessioni di risposte pianificate più per un gruppo utenti, in base a un tipo di riferimento. Consente di programmare ** programmazione del questionario ** nella pagina. Selezionare il tipo di pianificazione per classificare la programmazione e selezionare il tipo di riferimento da utilizzare per eseguire query sul sistema per utenti specifici. Ad esempio, se si imposta il tipo di riferimento ai corsi tabella, è possibile selezionare un corso specifico ** riferimento ** nel campo. 

Fare clic su **Dettagli impostazione** per selezionare il questionario e altri criteri. Ad esempio, specificare il nome dell'istruttore come criterio se il questionario è una valutazione dell'istruttore. Al termine di immettere i dettagli di attrezzaggio, il sistema genera le sessioni di risposte pianificate per gli utenti inclusi nella query. 

Fare clic su **Sessioni di risposte pianificate** per visualizzare le sessioni di risposte per la programmazione. È possibile quindi creare manualmente sessioni di risposte pianificate aggiuntive o eliminare le sessioni di risposte pianificate a cui non sono state fornite risposte. 

Fare clic su Funzioni ** ** &gt; ** inizio ** rendere disponibile il questionario agli utenti le sessioni di risposte pianificate correlate. Fare clic su **Risposte** per visualizzare le risposte completate nel questionario. Si può scegliere di copiare le impostazioni di programmazione questionario, le sessioni di risposte pianificate e le risposte in una nuova programmazione questionario.

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a>Informare gli intervistati dei questionari disponibili
Quando viene distribuito un questionario, è necessario avvisare gli intervistati che i questionari sono disponibili. 

** Nota: ** Gli intervistati devono essere utente in Microsoft Dynamics 365 per le operazioni compilati un questionario.

### <a name="notifying-respondents-about-a-planned-answer-session"></a>Informare gli intervistati su una sessione di risposte pianificata

Se si utilizza una sessione di risposte pianificata, è necessario informare direttamente la persona, ad esempio per telefono o posta elettronica.

### <a name="notifying-respondents-about-a-scheduling"></a>Informare gli intervistati su una programmazione

Utilizzare la pagina **Programmazioni questionari** per preparare e inviare un messaggio di posta elettronica a tutti gli intervistati a cui è stato assegnato il questionario. Immettere il testo del messaggio di posta elettronica nella scheda **Posta elettronica per dipendente self-service**. Una volta completata la programmazione è stata avviata, fare clic su ** funzioni ** &gt; ** inviare messaggi di posta elettronica ** generare e inviare messaggi di posta elettronica agli intervistati. Gli intervistati possono quindi firma nel sito Web e completare il questionario. 

**Nota:** affinché si possa utilizzare la funzionalità di posta elettronica, è necessario che l'amministratore IT immetta le impostazioni di posta elettronica nella pagina **Parametri posta elettronica**.

## <a name="ending-a-scheduled-questionnaire"></a>Completamento di un questionario programmato
È possibile concludere un questionario programmato dopo che tutti gli intervistati hanno completato le sessioni di risposte assegnate. In seguito al completamento di un questionario programmato, non è possibile copiarne le impostazioni in una nuova programmazione. 

**Nota:** Se alcuni intervistati non hanno completato il questionario ma si desidera comunque completare la programmazione, è necessario innanzitutto eliminare gli intervistati in questione dall'elenco presente nella pagina **Sessione di risposte pianificata**. Sarà quindi possibile completare la programmazione.

## <a name="completing-questionnaires"></a>Completamento di questionari
Dopo che è stato progettato e distribuito, un questionario può essere completato dagli intervistati selezionati. È possibile completare i questionari disponibili da due posizioni:

-   Nel riquadro di spostamento, fare clic su ** questionari ** &gt; ** distribuire ** &gt; ** compilare un questionario **.
-   In Dipendente self-service, fare clic su **Questionari da completare**.

I questionari possono essere messi a disposizione di utenti o gruppi di utenti specifici o di tutti gli utenti in una rete.

<a name="see-also"></a>Vedere anche
--------

[Progettazione di questionari](design-questionnaires.md)

[Utilizzo di questionari](questionnaires.md)

[Visualizzazione e valutare i risultati dei questionari evaluate-questionnaire-results.md] ()


