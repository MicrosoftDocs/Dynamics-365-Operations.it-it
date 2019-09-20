---
title: Domande frequenti sull'integrazione di Attract con LinkedIn
description: Questo argomento contiene le risposte alle domande sull'integrazione tra LinkedIn e Microsoft Dynamics 365 for Talent - Attract.
author: hasrivas
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: hasrivas
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c49181fe7e9359fb9d7d43f479273080f90542f4
ms.sourcegitcommit: c62756cb04549b2ff5de9b93d497e964a340335a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2019
ms.locfileid: "1756201"
---
# <a name="linkedin-integration-faq"></a>Domande frequenti sull'integrazione di LinkedIn

[!include [banner](includes/banner.md)]

LinkedIn è la più grande rete professionale online del mondo. Microsoft Dynamics for Talent - Attract si integra con LinkedIn per offrire l'opportunità di accedere ai migliori talenti del mondo. Attract consente di pubblicare posizioni direttamente in LinkedIn e consente inoltre di estrapolare le informazioni sui candidati da LinkedIn in Attract.

## <a name="for-recruiters-and-hiring-managers"></a>Per selezionatori e responsabili assunzioni

Di seguito sono riportate le risposte alle domande frequenti su come utilizzare Attract e LinkedIn insieme.

### <a name="what-linkedin-features-do-i-get-with-attract"></a>Quali funzionalità di LinkedIn possono essere utilizzate con Attract?

L'integrazione di Attract con LinkedIn consente di effettuare le seguenti attività:

- [Pubblicare posizioni in LinkedIn](./attract-post-jobs-to-linkedin.md) (come Elenchi restrizioni gratuiti).
- [Esportare le informazioni dei candidati da LinkedIn in Attract](./attract-linkedin-recruiter.md#export-linkedin-candidates-to-attract-with-one-click).
- [Consentire ai candidati di fare domanda per posizioni con LinkedIn](./attract-admin-linkedin.md#set-up-apply-with-linkedin-in-attract).

### <a name="what-do-i-need-before-i-can-post-jobs-to-linkedin"></a>Quali informazioni sono necessarie prima di poter pubblicare le posizioni in LinkedIn?

L'amministratore dell'azienda deve [configurare l'integrazione di LinkedIn in Attract](./attract-admin-linkedin.md#configure-job-posting-to-linkedin). A quel punto è possibile iniziare.

### <a name="how-do-i-post-jobs-to-linkedin-from-attract"></a>Come posso pubblicare le posizioni in LinkedIn da Attract?

Dopo aver creato una posizione in Attract, è sufficiente selezionare il pulsante **Pubblica ora** che corrisponde a LinkedIn. Per ulteriori informazioni, vedere [Pubblicare posizioni in LinkedIn da Attract](./attract-post-jobs-to-linkedin.md#post-jobs-to-linkedin).

### <a name="can-i-get-candidate-information-from-linkedin-into-attract"></a>Posso esportare le informazioni dei candidati da LinkedIn in Attract?

Sì. Se in LinkedIn si trova un candidato adatto alla posizione, è possibile esportarne facilmente le informazioni in Attract. Per ulteriori informazioni, vedere [Selezionare i candidati con LinkedIn Recruiter](attract-linkedin-recruiter.md).

### <a name="how-can-i-get-help-accessing-linkedin-from-attract"></a>Come è possibile ottenere informazioni per accedere a LinkedIn da Attract?

Se si verificano problemi nell'accesso o nella pubblicazione di posizioni in LinkedIn da Attract, vedere [Risoluzione dei problemi di integrazione con LinkedIn](./attract-troubleshoot-linkedin.md).

Per altri problemi con Attract, vedere [Ottenere supporto per Talent](./talent-support.md). Per informazioni sull'utilizzo di LinkedIn, vedere la [Pagina del supporto tecnico di LinkedIn](https://www.linkedin.com/help).

## <a name="for-admins-and-developers"></a>Per amministratori e sviluppatori

Di seguito sono riportate le risposte alle domande frequenti su come configurare l'integrazione tra Attract e LinkedIn.

### <a name="how-do-i-configure-attract-so-that-recruiters-and-hiring-managers-can-post-jobs-to-linkedin"></a>Come configuro Attract in modo che i selezionatori e i responsabili assunzioni possano pubblicare posizioni in LinkedIn?

È possibile configurare le opzioni disponibili nella scheda **Integrazione di LinkedIn** dell'interfaccia di amministrazione. Per ulteriori informazioni, vedere [Impostare l'integrazione con LinkedIn](./attract-admin-linkedin.md).

### <a name="can-i-export-candidate-information-from-linkedin"></a>Posso esportare le informazioni dei candidati da LinkedIn?

Sì, ma è necessario prima configurare l'integrazione con LinkedIn Recruiter. Per ulteriori informazioni, vedere [Impostare l'integrazione con LinkedIn](./attract-admin-linkedin.md).

### <a name="how-can-i-post-jobs-to-premium-job-slots-on-linkedin"></a>Come posso pubblicare le posizioni negli slot di lavoro Premium in LinkedIn?

Sebbene Attract fornisca una soluzione potente per la pubblicazione di posizioni in LinkedIn, è possibile che occorra maggiore flessibilità rispetto a quella offerta. Ad esempio, è possibile che si desideri poter pubblicare negli slot di lavoro Premium oltre che nelle Inserzioni limitate gratuite oppure è possibile che si desideri che LinkedIn elabori più volte al giorno le pubblicazioni.

#### <a name="types-of-linkedin-job-posts"></a>Tipi di pubblicazioni di posizioni in LinkedIn

LinkedIn offre i seguenti tipi di pubblicazioni di posizioni:

- **Inserzioni limitate** - Le pubblicazioni di posizioni gratuite che vengono visualizzate nei risultati della ricerca quando i candidati cercano posizioni in LinkedIn e nella pagina di LinkedIn di una società. Le Inserzioni limitate sono mirate ai ricercatori di posizioni attivi. Questo tipo di elenco è il tipo che Attract fornisce a LinkedIn. Non è possibile promuovere posizioni in Inserzioni limitate in LinkedIn. Se si desidera promuovere le inserzioni limitate, è necessario utilizzare LinkedIn per consentire il wrapping di lavoro. Per ulteriori informazioni sul wrapping di lavoro, vedere [Inserzioni limitate e slot di lavoro Premium per il wrapping di lavoro](https://www.linkedin.com/help/recruiter/answer/79049/limited-listings-vs-premium-job-slots-for-job-wrapping) e [Job wrapping Plus - Domande frequenti](https://www.linkedin.com/help/recruiter/answer/79050/job-wrapping-frequently-asked-questions).
- **Slot di lavoro Premium** - Pubblicazioni a pagamento che vengono visualizzate in vari punti in LinkedIn, ad esempio nel feed LinkedIn, nelle e-mail e nell'area **Lavori che potrebbero interessarti**. Gli slot di lavoro Premium sono mirati ai candidati passivi, ma vengono visualizzati anche nelle ricerche di lavoro.

Attract pubblica le posizioni in LinkedIn come inserzioni limitate. Se si desidera utilizzare gli slot di lavoro Premium, è necessario utilizzare il wrapping del lavoro tramite LinkedIn Recruiter. Il wrapping del lavoro prevede un contratto specifico con LinkedIn. Per ulteriori informazioni, vedere [Wrapping del lavoro attraverso LinkedIn Recruiter - Panoramica](https://www.linkedin.com/help/recruiter/answer/79037).

#### <a name="frequency-of-batch-processing-on-linkedin"></a>Frequenza di elaborazione batch in LinkedIn

LinkedIn elabora le pubblicazioni di posizioni in un batch attraverso Attract una volta al giorno. Di conseguenza, la visualizzazione delle posizioni in LinkedIn può richiedere fino a 48 ore dalla pubblicazione tramite Attract. Se occorre che le posizioni appaiano prima di questo tempo in LinkedIn, o se si necessita di ulteriore flessibilità, è possibile utilizzare l'API di Recruiter System Connect da LinkedIn. Per ulteriori informazioni, vedere [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect).

#### <a name="table-of-options-for-job-posting-to-linkedin"></a>Tabella delle opzioni per la pubblicazione di posizioni in LinkedIn

Nella tabella seguente vengono descritte le varie opzioni per la pubblicazione di posizioni in LinkedIn. Include i vantaggi di ciascuna opzione e informazioni aggiuntive.

|  | Attract | Wrapping del lavoro attraverso LinkedIn Recruiter | API di Recruiter System Connect |
|---|---|---|---|
| **Descrizione** | Attract pubblica le posizioni in LinkedIn come feed XML. | La società stipula un contratto con LinkedIn e fornisce un feed XML per la pubblicazione delle posizioni. | Il cliente usa l'API per sincronizzare le informazioni tra Attract e LinkedIn Recruiter. |
| **Che tipo di posizione posso pubblicare?** | Inserzioni limitate | Slot di lavoro Premium o Inserzioni limitate | Inserzioni limitate |
| **Posso promuovere una posizione in LinkedIn?** | Nessuno | Slot di lavoro Premium: sì<br>Inserzioni limitate: no | Nessuno |
| **Con quale frequenza LinkedIn pubblica le posizioni?** | Una volta al giorno | Una volta al giorno | Più volte al giorno, come definito dall'API |
| **Consigliato da LinkedIn?** | Nessuno | Sì | Nessuno |
| **Quali sono i requisiti?** | Acquisto di Attract | Contratto di wrapping del lavoro con LinkedIn e acquisto di slot di lavoro Premium | Accordo di API con LinkedIn | 
| **Dove è possibile trovare ulteriori informazioni?** | [Impostare l'integrazione con LinkedIn](./attract-admin-linkedin.md) | [JWrapping del lavoro attraverso LinkedIn Recruiter - Panoramica](https://www.linkedin.com/help/recruiter/answer/79037) | [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect) |

> [!NOTE]
> Non è necessario disporre di una licenza LinkedIn Recruiter System Connect per pubblicare le posizioni in LinkedIn con Attract.

## <a name="see-also"></a>Vedere anche

[Impostare l'integrazione con LinkedIn](./attract-admin-linkedin.md)

[Pubblicare posizioni in LinkedIn da Attract](./attract-post-jobs-to-linkedin.md)

[Selezionare i candidati con LinkedIn Recruiter](./attract-linkedin-recruiter.md)

[Risoluzione dei problemi di integrazione con LinkedIn](./attract-troubleshoot-linkedin.md)
