---
title: Impostazione dell'integrazione con LinkedIn per Microsoft Dynamics 365 Talent - Attract
description: In questo argomento viene descritto come configurare l'integrazione di LinkedIn per Microsoft Dynamics 365 Talent - Attract in modo da poter pubblicare facilmente posizioni su LinkedIn da Attract, affinché i selezionatori possano sincronizzare le informazioni sull'assunzione con il profilo LinkedIn di un candidato.
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
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 6b86cafdf364f2de051f3d8ceab7413c2c13c3a5
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009972"
---
# <a name="set-up-linkedin-integration"></a>Configurare l'integrazione di LinkedIn

[!include[banner](../includes/banner.md)]

La configurazione dell'integrazione di LinkedIn con Microsoft Dynamics 365 Talent: Attract aiuta i selezionatori e i responsabili assunzioni a trovare i migliori talenti. Attract consente di pubblicare le posizioni direttamente in LinkedIn, che è la più grande rete professionale online.

Le posizioni che si pubblicano in LinkedIn attraverso Attract sono inserzioni limitate e vengono fornite senza costi aggiuntivi per la società. Queste inserzioni sono disponibili solo tra i partner software di LinkedIn come Attract. Non vengono visualizzate nel pannello **Carriere** della pagina di LinkedIn della società, perché in questo pannello appaiono solo le inserzioni a pagamento. Tuttavia, vengono visualizzate quando potenziali candidati visualizzano tutte le posizioni disponibili. Le inserzioni limitate vengono visualizzate anche nelle ricerche di lavoro di LinkedIn.

Attract include due metodi per integrare LinkedIn e aiutare a selezionare candidati dal noto sito professionale:

- Pubblicare posizioni da Attract in LinkedIn
- Selezionare candidati da LinkedIn per Attract.

Entrambe le opzioni devono essere configurate nella scheda **Integrazione di LinkedIn** dell'interfaccia di amministrazione. Per aprire l'interfaccia di amministrazione, accedere a <https://attract.talent.dynamics.com/adminsettings>.

> [!NOTE]
> Per utilizzare l'integrazione di LinkedIn Recruiter con Attract, è necessario disporre del [componente aggiuntivo per l'assunzione a livello globale](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring) e di [licenze per LinkedIn Recruiter](https://business.linkedin.com/talent-solutions/cx/17/08/recruiter-demo-fs2-k18). Per ulteriori informazioni, vedere [Quale versione di Attract?](./attract-comprehensive-hiring.md).

In caso di problemi nella pubblicazione delle posizioni su LinkedIn, vedere [Risoluzione dei problemi di integrazione con LinkedIn](./attract-troubleshoot-linkedin.md).

Per informazioni su altri modi di pubblicare posizioni su LinkedIn, vedere [Domande frequenti su LinkedIn](./attract-linkedin-faq.md).

## <a name="configure-job-posting-to-linkedin"></a>Configurare la pubblicazione di posizioni su LinkedIn

Prima di poter pubblicare posizioni da Attract a LinkedIn, è necessario avere un [ID società LinkedIn](https://aka.ms/findID) L'ID società LinkedIn è un codice numerico che identifica in modo univoco la società in LinkedIn. Per ulteriori informazioni, vedere [Associazione dell'ID società di LinkedIn alla bacheca di lavoro di LinkedIn - domande frequenti](https://aka.ms/findID).

Attract invia un feed degli annunci di lavoro a LinkedIn e LinkedIn controlla il feed circa una volta al giorno. La pubblicazione delle posizioni sul sito può richiedere fino a 48 ore.

Le posizioni che vengono pubblicate in LinkedIn vengono visualizzate direttamente nel sito di LinkedIn. LinkedIn non dispone di un ambiente di test per la pubblicazione delle posizioni. Assicurarsi quindi di non pubblicare accidentalmente annunci di prova. 

1. Nel menu **Impostazione** (il simbolo di ingranaggio) nell'angolo superiore destro, selezionare **Interfaccia di amministrazione**. In alternativa, accedere a <https://attract.talent.dynamics.com/adminsettings>.
2. Selezionare la scheda **Integrazione di LinkedIn**.
3. In **Nome società** immettere il nome della società e in **ID società** immettere l'ID società LinkedIn. Verificare che il nome della società corrisponda al nome che appare nella pagina di LinkedIn della società. Per ulteriori informazioni sugli ID società LinkedIn, vedere [Associazione dell'ID società di LinkedIn alla bacheca di lavoro di LinkedIn - domande frequenti](https://www.linkedin.com/help/linkedin/answer/98972).

    Se è necessario modificare le informazioni per l'organizzazione, vedere [Modificare l'indirizzo, il contatto tecnico e altro dell'organizzazione](https://docs.microsoft.com/office365/admin/manage/change-address-contact-and-more). Se si verificano ancora altri problemi, contattare il [Supporto tecnico di LinkedIn](https://www.linkedin.com/help/linkedin).

4. Selezionare **Salva**.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Configurare LinkedIn Recruiter con Attract 

Per consentire ai selezionatori di offrire posizioni attraverso LinkedIn Recruiter, è necessario configurare l'integrazione con LinkedIn Recruiter in Attract. Per completare il processo di configurazione, è necessario collaborare con un utente amministratore sul contratto LinkedIn Recruiter dell'azienda.

1. Nel menu **Impostazione** (il simbolo di ingranaggio) nell'angolo superiore destro, selezionare **Interfaccia di amministrazione**. In alternativa, accedere a <https://attract.talent.dynamics.com/adminsettings>.
2. Selezionare la scheda **Integrazione di LinkedIn**.

    [![Visualizzazione amministratore di Attract per avviare l'integrazione di LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. Selezionare **Connetti** per iniziare l'impostazione. Verranno indicati i passaggi per accedere a LinkedIn.
4. Se si dispone di postazioni in più contratti LinkedIn, selezionare il contratto da connettere al sistema Attract. Se si dispone di una postazione in un solo contratto LinkedIn, è possibile ignorare questo passaggio.
5. In **Recruiter System Connect (RSC)** selezionare **Richiesta**.

    [![Visualizzazione amministratore di Attract per richiedere l'integrazione di LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6. L'impostazione **Recruiter System Connect (RSC)** appare ora come **Pronto per partner**. Se viene visualizzato **Notifica partner** in questa pagina, attendere alcuni secondi, selezionare **Notifica partner**, quindi aggiornare la pagina. L'impostazione deve apparire come **Partner pronto**.

    [![Visualizzazione amministratore di Attract per indicare che il lato Attract delle richieste è stato completato](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

7. Per completare i passaggi successivi, è necessario disporre di privilegi di amministratore per il contratto LinkedIn Recruiter.

    1. Accedere a LinkedIn utilizzando il proprio account di amministratore quindi selezionare **LinkedIn Recruiter** in alto a destra. 
    2. Nel menu **Altro** nella parte superiore della pagina, selezionare **Impostazioni amministratore** e quindi selezionare la scheda **ATS**.
    3. Per abilitare l'esportazione con un clic per un solo contratto, attivare **Accesso livello contratto (per ogni postazione nel contratto)**. Per abilitarla per l'intera azienda, attivare **Accesso livello contratto (per ogni contratto nell'azienda)**.

    [![Attivare l'integrazione di Attract dalla visualizzazione amministratore di LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)

8. Nell'interfaccia di amministrazione di Attract, selezionare la scheda **Integrazione di LinkedIn**. L'impostazione **Recruiter System Connect (RSC)** appare come **Abilitata**.

    [![Integrazione di LinkedIn Recruiter completata](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="set-up-apply-with-linkedin-in-attract"></a>Impostare una domanda con LinkedIn in Attract

È possibile consentire ai candidati di presentare domanda per le posizioni utilizzando i propri profili di LinkedIn. Per ulteriori informazioni sulla presentazione di domande con LinkedIn, vedere [La potenza di LinkedIn: presentare domanda di lavoro con LinkedIn](https://blog.linkedin.com/2011/07/24/apply-with-linkedin).

Questa funzionalità è attualmente in anteprima. Prima di seguire questi passaggi, assicurarsi che l'opzione Fai domanda con LinkedIn sia attivata. Per ulteriori informazioni su come abilitare le funzionalità di anteprima, vedere [Accesso alle funzionalità di anteprima in Talent](./access-preview-feature.md).

1. Nel menu **Impostazione** (il simbolo di ingranaggio) nell'angolo superiore destro, selezionare **Interfaccia di amministrazione**. In alternativa, accedere a <https://attract.talent.dynamics.com/adminsettings>.
2. Selezionare la scheda **Integrazione di LinkedIn**.

    [![Visualizzazione amministratore di Attract per avviare l'integrazione di LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. Accanto a **Fai domanda con LinkedIn**, selezionare **Connetti** per avviare la configurazione. Verranno indicati i passaggi per completare i processo con LinkedIn.

## <a name="see-also"></a>Vedere anche

[Domande frequenti su LinkedIn](./attract-linkedin-faq.md)

[Pubblicare mansioni su siti esterni da Attract](./posting-jobs-external.md)

[Selezionare i candidati con LinkedIn Recruiter](./attract-linkedin-recruiter.md)

[Creare posizioni](./creating-jobs-attract.md)

[Risoluzione dei problemi di integrazione con LinkedIn](./attract-troubleshoot-linkedin.md)
