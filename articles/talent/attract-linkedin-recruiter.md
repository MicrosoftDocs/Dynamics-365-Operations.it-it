---
title: Selezionare i candidati con LinkedIn Recruiter in Microsoft Dynamics 365 for Talent - Attract
description: Utilizzare l'integrazione di LinkedIn fornita da Microsoft Dynamics 365 for Talent - Attract per selezionare i candidati a una posizione attraverso LinkedIn Recruiter.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 14aba16fa81a8f25d0f88247319254407d428b2a
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739451"
---
# <a name="source-candidates-with-linkedin-recruiter"></a>Selezionare i candidati con LinkedIn Recruiter
[!include[banner](../includes/banner.md)]

LinkedIn è la più grande rete professionale online del mondo, che consente di contattare i migliori talenti al mondo. Microsoft Dynamics 365 for Talent - Attract consente di selezionare i candidati direttamente da LinkedIn. È quindi più semplice che mai trovare i talenti necessari a ricoprire le posizioni aperte. Dopo aver impostato la connessione a LinkedIn tramite Attract, è possibile visualizzare i potenziali candidati di LinkedIn alle posizioni in un'azienda ed esportarne le informazioni in Attract con un semplice clic.

Se la funzionalità non sembra essere disponibile, contattare il proprio amministratore. Prima di poter usufruire dei vantaggi di LinkedIn Recruiter da Attract, l'amministratore deve [impostare l'integrazione con LinkedIn](./attract-admin-linkedin.md). È quindi possibile impostare la connessione con LinkedIn Recruiter e iniziare a cercare i candidati.

## <a name="set-up-your-connection-with-linkedin-recruiter"></a>Impostare la connessione con LinkedIn Recruiter

Prima di iniziare a utilizzare LinkedIn Recruiter attraverso Attract, è necessario impostare la connessione con LinkedIn Recruiter. Per questo passaggio, è necessario creare le proprie credenziali LinkedIn Recruiter.

1. Selezionare il pulsante **Impostazioni** (icona a forma di rotella) nell'angolo in alto a destra della pagina.
2. Selezionare **Impostazioni utente**.
3. Nella scheda **Connessioni** selezionare **Connetti** accanto a **LinkedIn**. Seguire le istruzioni che vengono fornite da LinkedIn.

    ![[Impostare la connessione a LinkedIn Recruiter da Attract](./media/attract-set-up-linkedin-recruiter-connection.png)](./media/attract-set-up-linkedin-recruiter-connection.png)

## <a name="view-linkedin-candidates-in-attract"></a>Visualizzare i candidati di LinkedIn in Attract

Dopo aver eseguito la connessione a LinkedIn Recruiter, è possibile visualizzare i profili LinkedIn dei candidati in Attract.

1. In Attract, selezionare **Posizioni** o **Pool di talenti** a sinistra, quindi selezionare un candidato.

    ![[Visualizzare i candidati di LinkedIn in Attract](./media/attract-view-linkedin-candidates.png)](./media/attract-view-linkedin-candidates.png)

2. Nel profilo del candidato, selezionare la scheda **LinkedIn**. È possibile visualizzare il profilo del candidato, insieme allo storico di InMail e lo storico delle note di LinkedIn.

Da questa posizione, è possibile salvare il candidato a un progetto LinkedIn Recruiter, inviare una inMail, oppure utilizzare Aggiornami per impostare un avviso in LinkedIn Recruiter.

> [!NOTE]
> Il profilo LinkedIn di un candidato viene visualizzato in Attract quando viene trovata corrispondenza tra le informazioni del candidato in Attract e quelle di LinkedIn. Di seguito sono riportate le regole di abbinamento utilizzate:
> 
> 1. Se l'indirizzo e-mail e l'ID membro LinkedIn corrispondono in Attract e LinkedIn, il profilo del candidato viene visualizzato. I candidati possono ancora collegare o non collegare il proprio profilo di LinkedIn da Attract.
> 2. Se l'indirizzo e-mail o l'ID membro LinkedIn non corrisponde, viene visualizzato un elenco di possibili candidati. È possibile quindi selezionare un candidato nell'elenco e collegare il profilo.
> 3. Se non sono presenti corrispondenze adeguate, l'utente riceve una notifica che indica che non è stata rilevata alcuna corrispondenza.

## <a name="export-linkedin-candidates-to-attract-with-one-click"></a>Esportare i candidati di LinkedIn in Attract con un semplice clic

Quando si esaminano i candidati in LinkedIn Recruiter, è possibile esportarli nelle posizioni correntemente aperte in Attract. Per questo passaggio è necessario disporre delle autorizzazioni di selezionatore o responsabile assunzioni in Attract. Per ulteriori informazioni sui ruoli in Attract, vedere [Gestione della sicurezza e dei ruoli in Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/security-attract).

È inoltre necessario assicurarsi che la posizione abbia una fase di prospect. Per ulteriori informazioni, vedere [Attività di prospect](./activities-attract.md#prospect-activity).

1. In Attract, creare una posizione, assegnare i ruoli appropriati e attivare la posizione.
2. In LinkedIn Recruiter, trovare un candidato idoneo alla posizione e accedere al relativo profilo.
3. Utilizzando la casella di ricerca mansioni nella scheda contatto, trovare la posizione mediante il titolo o l'ID mansione che è stato attivato in Attract. Se non viene individuata la posizione, fare clic su **Cambia ATS** per individuare la corretta istanza di Attract.
4. Selezionare la posizione, quindi selezionare **Esporta**.
5. In Attract, aprire la posizione. Il candidato esportato verrà visualizzato nella scheda **Prospect** della posizione.

## <a name="view-attract-information-in-linkedin-recruiter"></a>Visualizzare le informazioni di Attract in LinkedIn Recruiter

In LinkedIn Recruiter, è possibile monitorare se un candidato ha fatto domanda per altre posizioni nella stessa azienda, vedere in quale fase si trova il candidato nelle domande di lavoro e visualizzare i commenti e i suggerimenti da Attract.

1. Aprire LinkedIn Recruiter e selezionare il profilo di un candidato.
2. Passare il mouse su **In-ATS**.
3. Selezionare una delle seguenti opzioni per visualizzare informazioni sul candidato archiviate in Attract:

    - **Posizioni e stati** - Vedere le posizioni di cui fa parte il candidato, lo stato più recente e in che modo il candidato procede in ogni posizione.
    - **Feedback colloquio** - Visualizzare i commenti che i responsabili del colloquio hanno inviato in Attract.
    - **Note** - Vedere eventuali note immesse sul candidato in Attract.

    ![[Visualizzare le informazioni di Attract da LinkedIn Recruiter](./media/attract-view-information-from-linkedin-recruiter.png)](./media/attract-view-information-from-linkedin-recruiter.png)

> [!NOTE]
> I dati del candidato e della domanda non vengono sincronizzati con LinkedIn Recruiter se il candidato non è passato alla fase di Prospect.

## <a name="view-linkedin-talent-pools"></a>Visualizzare i pool di talent di LinkedIn

Se i candidati accettano di condividere i propri profili di LinkedIn con qualsiasi utente nell'azienda, in Attract viene creato un nuovo record di candidato. Questi candidati vengono visualizzati in un pool di talenti di LinkedIn creato dal sistema.

1. In Attract, selezionare **Pool di talenti** a sinistra.
2. Selezionare il pool di talenti di LinkedIn. Verranno visualizzati un elenco di candidati e i relativi profili stub da LinkedIn. I profili stub contengono il nome e il cognome del candidato, l'indirizzo e-mail e la scelta o meno di condividere tali dati.

## <a name="see-also"></a>Vedere anche

[Domande frequenti su LinkedIn](./attract-linkedin-faq.md)

[Impostare l'integrazione con LinkedIn](./attract-admin-linkedin.md)

[Creare posizioni](./creating-jobs-attract.md)

[Pubblicare posizioni in LinkedIn da Attract](./attract-post-jobs-to-linkedin.md)

[Risoluzione dei problemi di integrazione con LinkedIn](./attract-troubleshoot-linkedin.md)
