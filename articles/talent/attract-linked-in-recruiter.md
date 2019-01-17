---
title: Cercare candidati con LinkedIn Recruiter
description: In questo argomento vengono fornite informazioni sull'uso dell'apprendimento automatico per ottenere suggerimenti su mansioni e candidati.
author: josaw
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: be66d9f95551066bb8bc25445c652d4fa59066d4
ms.openlocfilehash: 9bb323728923ff3b09ff0bfba3849f3c5d84eb34
ms.contentlocale: it-it
ms.lasthandoff: 12/07/2018

---

# <a name="sourcing-with-linkedin-recruiter"></a>Cercare candidati con LinkedIn Recruiter
[!include[banner](../includes/banner.md)]

LinkedIn è il più grande database di talenti del mondo e spesso il sistema primario che utilizzano i selezionatori per trovare e comunicare con i candidati per le posizioni che devono coprire. L'integrazione di LinkedIn Recruiter con Dynamics 365 for Talent: Attract  facilita le assunzioni e il mantenimento della sincronizzazione dei dati tra i due sistemi.

> [!NOTE]
> È necessario disporre del componente aggiuntivo per l'assunzione a livello globale e postazioni di LinkedIn Recruiter per poter utilizzare l'integrazione di LinkedIn Recruiter con Attract.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Impostare LinkedIn Recruiter con Attract 

Prima di utilizzare le funzioni di LinkedIn Recruiter, è necessario configurare l'accesso a livello di contratto o a livello di società con l'istanza di Attract. Per completare il processo di configurazione, è necessario utilizzare l'utente che è l'amministratore nel contratto LinkedIn Recruiter. Completare i passaggi seguenti per configurare LinkedIn Recruiter con Attract.

1.  Accedere ad Attract come amministratore e passare a **Impostazioni di amministrazione**.

2.  Nel riquadro sinistro, fare clic sulla scheda **Integrazione di LinkedIn**.

[![Visualizzazione amministratore di Attract per avviare l'integrazione di LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3.  Scegliere **Connetti** per avviare la configurazione ed essere guidati nel processo di accesso a LinkedIn.

4.  Se si dispone di postazioni in più contratti LinkedIn, selezionare il contratto da connettere al sistema Attract. Se si dispone di una postazione in un solo contratto LinkedIn, questo passaggio non sarà necessario.

5.  Il widget LinkedIn ora si caricherà nelle impostazioni di amministrazione con l'elenco delle integrazioni mostrato. In **Recruiter System Connect**, fare clic su **Richiesta**.

[![Visualizzazione amministratore di Attract per richiedere l'integrazione di LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6.  Dopo che l'integrazione è richiesta da Attract, verrà visualizzato come **Pronto per partner** ed è pronta per essere attivata da **Impostazioni amministratore Recruiter**. Se viene visualizzato **Notifica partner** in questa pagina, attendere alcuni secondi, fare clic su **Notifica partner**, quindi aggiornare la pagina. Deve ora visualizzare **Pronto per partner**.

[![Visualizzazione amministratore di Attract per indicare che il lato Attract delle richieste è stato completato](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

Per completare il passaggio successivo, è necessario disporre di un privilegio di amministrazione per il contratto LinkedIn Recruiter.

7.  Accedere a LinkedIn utilizzando l'account amministratore e passare a LinkedIn Recruiter in alto a destra. 

8. Nel menu **Altro** nella parte superiore della schermata, fare clic su **Impostazioni amministratore** e quindi sulla scheda **ATS**.

Il sistema Attract verrà visualizzato con una coppia di opzioni che è possibile attivare.

9. Se si desidera consentire solo l'esportazione con 1 clic per **Indicatore In-ATS** e **Widget profilo In-ATS**, selezionare **Accesso a livello di società**. Se si desidera abilitare tutte le funzionalità di accesso a livello di società più l'accesso allo storico di InMail, allo storico di Note e al profilo stub di InMail, selezionare **Accesso a livello di società**.

10. Attivare il livello di accesso desiderato dalle impostazioni **Admin-ATS** di LinkedIn Rectuiter.

[![Attivare l'integrazione di Attract dalla visualizzazione amministratore di LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)

12. Tornare alle impostazioni di amministrazione di Attract come AttractAdmin e selezionare la scheda **Integrazione di LinkedIn**. È ora possibile visualizzare il carico del widget LinkedIn che mostra **Abilitato** con il livello selezionato abilitato.

[![Integrazione di LinkedIn Recruiter completata](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="using-linkedin-recruiter-capabilities"></a>Utilizzo delle funzionalità di LinkedIn Recruiter

Dopo che le funzionalità di LinkedIn Recruiter è stato attivato dall'amministratore di Attract, sono disponibili all'accesso da parte dei selezionatori e i responsabili delle assunzioni. Per utilizzare queste funzionalità, connettere l'account LinkedIn in **Impostazioni utenti**. Diverse funzionalità saranno disponibili anche dopo che le impostazioni amministratore e utente sono state connesse.

### <a name="in-ats-profile-widget"></a>Widget del profilo In-ATS

È possibile visualizzare il profilo LinkedIn del candidato in Attract. Il widget LinkedIn visualizzerà il profilo del candidato quando le informazioni ATS corrispondono alle informazioni LinkedIn degli utenti.

Per visualizzare un profilo, andare al profilo del candidato da una posizione lavorativa o un pool di talenti. Nel profilo del candidato, selezionare la scheda **LinkedIn** e il widget del profilo verrà caricato. È inoltre possibile salvare il candidato nei progetti di LinkedIn Recruiter da questa pagina.
1. Se LinkedIn trova la corrispondenza in base all'e-mail e all'ID membro LinkedIn (corrispondenza esatta), il profilo del candidato verrà visualizzato. L'utente ha ancora un'opzione per collegare/scollegare il profilo.

2. Se LinkedIn non trova il candidato in base all'e-mail o all'ID membro, viene visualizzato un elenco di possibili corrispondenze in base al nome del candidato e l'utente può sceglierne uno e collegare il profilo.  

3. Se LinkedIn non trova alcun candidato in base al nome, indicherà che non è stata rilevata alcuna corrispondenza.

### <a name="1-click-export"></a>Esportazione con 1 clic 

Durante la selezione dei candidati in LinkedIn è possibile esportare con 1 clic il candidato nelle mansioni attualmente aperte. Completare i passaggi seguenti per una esportazione con 1 clic. Prima di completare questi passaggi, verificare di disporre del ruolo di responsabile assunzioni o selezionatore per la mansione e che la fase della mansione sia **Candidato**.

1.  Creare la mansione, assegnare i ruoli appropriati e attivare la mansione.

2.  Quando la mansione viene attivato, passare a LinkedIn Recruiter.

3.  Individuare il candidato che si desidera trovare e passare al profilo.

4.  Utilizzando la casella di ricerca mansioni nella scheda contatto, trovare la mansione mediante il titolo o l'ID mansione che è stato attivato in Attract. Se non viene individuata la mansione, fare clic su **Cambia ATS** per individuare la corretta istanza di Attract.

5. Dopo che la mansione è selezionata, fare clic su **Esporta**. Il candidato viene ora recuperato da Attract.

6.  Passare ad Attract e aprire la rispettiva mansione. Il candidato appena esportato si troverà nella fase **Candidato** del processo.

### <a name="in-ats-indicator"></a>Indicatore In-ATS 

Utilizzando LinkedIn Recruiter, è possibile tenere traccia se un candidato ha fatto domanda per altre mansioni nell'organizzazione, vedere le fasi in cui si trova nelle domande di lavoro e visualizzare il riscontro e i commenti da Attract in LinkedIn Recruiter.

1.  Aprire LinkedIn Recruiter e individuare il profilo del candidato richiesto.

2.  Scorrere fino a visualizzare la sezione **In-ATS** del profilo del candidato.

3.  È possibile utilizzare questo widget per visualizzare tutte le informazioni sul candidato che sono presenti in Attract dalla visualizzazione di LinkedIn Recruiter.

4.  Selezionare la scheda **Posizioni e stati** per visualizzare le mansioni di cui fa parte, l'ultimo stato e lo spostamento rispetto a ciascuna mansione.

5.  Selezionare la scheda **Feedback colloquio** per visualizzare i commenti che i responsabili del colloquio hanno inviato in Attract.

6.  Selezionare la scheda **Note** per visualizzare le note che sono state acquisite per il candidato in Attract.

> [!NOTE]
> Il candidato e i dati dell'applicazione non verranno sincronizzati in LinkedIn Recruiter se il candidato non è passato alla fase di prospect.

### <a name="inmail-history"></a>Storico InMail

Lo storico InMail LinkedIn è disponibile con l'accesso a livello di contratto con LinkedIn Recruiter. Quando è abilitato, sarà possibile visualizzare l'intero storico InMail con il candidato. È inoltre possibile visualizzare chi altro dell'organizzazione ha scambiato InMail con il candidato, ma non è possibile visualizzare i messaggi scambiati.

Per visualizzare lo storico di InMail, passare al profilo di un candidato, passare alla scheda **LinkedIn** e scorrere fini alla parte inferiore della pagina per visualizzare lo storico. È possibile visualizzare lo storico di InMail se si è tenuta una discussione con il candidato. I messaggi da InMail vengono sincronizzati con Attract ogni due ore.

### <a name="notes-history"></a>Storico delle note 

Lo storico delle note LinkedIn è disponibile con l'accesso a livello di contratto con LinkedIn Recruiter. Quando è abilitato, è possibile visualizzare le note che sono state acquisite sul candidato dai singoli selezionatori dell'organizzazione.

Per visualizzare lo storico delle note, passare al profilo di un candidato, passare alla scheda **LinkedIn** e scorrere fini alla parte inferiore della pagina per visualizzare lo storico. È possibile visualizzare tutte le note sul candidato da LinkedIn Recruiter.

### <a name="inmail-stub-profile"></a>Profilo stub di InMail

Il profilo stub di InMail è disponibile con l'accesso a livello di contratto con LinkedIn Recruiter. Se i candidati accettano di condividere i propri profili di LinkedIn con qualsiasi utente dell'organizzazione, è possibile tenere traccia dei candidati in Attract e un nuovo record candidato verrà creato per ciascun candidato. È possibile visualizzare l'indirizzo di posta elettronica del candidato se il candidato è già presente nel sistema con un indirizzo di posta elettronica o ha scelto di condividere l'indirizzo con il selezionatore.

Per visualizzare l'elenco dei candidati, andare a **Pool di talenti** per visualizzare un pool di talenti LinkedIn creato dal sistema. Questo pool di talenti contiene l'elenco di candidati e i relativi profili stub come ricevuti da LinkedIn, mostrando il nome e cognome del candidato. L'ID di posta elettronica del candidato viene visualizzato nel caso in cui il candidato ha scelto di condividere il proprio indirizzo di posta elettronica.

