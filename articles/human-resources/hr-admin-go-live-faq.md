---
title: Domande frequenti fase operativa
description: Questo argomento elenca le domande frequenti su come passare alla fase operativa con un progetto di implementazione Dynamics 365 Human Resources.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ca6c89f5f6dc4660a77587112526a6516f683f64ce95a9a83f39add119d2ee12
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731397"
---
# <a name="go-live-faq"></a>Domande frequenti fase operativa 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento elenca le domande frequenti su come passare alla fase operativa con un progetto di implementazione Dynamics 365 Human Resources. 

## <a name="when-can-i-configure-and-request-my-production-environment"></a>Quando è possibile configurare e richiedere l'ambiente di produzione? 

In genere, un ambiente di produzione viene distribuito dopo aver soddisfatto i seguenti criteri:

- Tutte le personalizzazioni del codice sono state completate.
- Il test di accettazione dell'utente (UAT) è stato completato.
- Il cliente ha autorizzato la soluzione.
- Non ci sono problemi che bloccano la fase operativa. 

Quando i clienti idonei si trovano in questa fase, il team Microsoft FastTrack lavorerà con il team di progetto per eseguire una valutazione della fase operativa. 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a>Quali sono i prerequisiti per la distribuzione di un ambiente di produzione? 

Per un elenco dei prerequisiti, vedere  [Preparazione per la fase operativa](hr-admin-go-live-prepare.md). 

## <a name="what-is-a-go-live-assessment"></a>Cos'è una valutazione della fase operativa?  

La valutazione della fase operativa fa parte del  [programma Microsoft FastTrack](/dynamics365/fasttrack/). Durante questa revisione, un solution architect valuta se un progetto di implementazione è pronto per il passaggio e la fase operativa di successo. Questa revisione è obbligatoria per ogni progetto di implementazione prima di poter richiedere la fase operativa in un ambiente di produzione. 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a>I nostri ambienti Sandbox vengono distribuiti nel data center degli Stati Uniti centrali. Vogliamo che i nostri ambienti di produzione vengano distribuiti nel data center degli Stati Uniti occidentali. È possibile selezionare Stati Uniti occidentali come data center nella configurazione di produzione? 

LCS non impedisce di selezionare un data center diverso quando si distribuisce un ambiente Human Resources, ma consigliamo vivamente di non selezionare un data center diverso.  

Se si desidera che l'ambiente di produzione si trovi nel data center degli Stati Uniti occidentali, è necessario prima ridistribuire gli ambienti Sandbox nel data center degli Stati Uniti occidentali, testarli e disconnetterli. 

Per informazioni sulla selezione del data center corretto, vedere [Requisiti di rete](../fin-ops-core/fin-ops/get-started/system-requirements.md#network-requirements). 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a>Quale livello di accesso alle risorse di Azure è disponibile per gli ambienti Human Resources?  

L'accesso agli ambienti Human Resources è limitato. Non è possibile accedere alla macchina virtuale (VM) o a Microsoft Internet Information Services (IIS). Inoltre non è possibile accedere al database tramite Microsoft SQL Server Management Studio. 

Sebbene non sia possibile accedere alle risorse di Azure o all'ambiente Dynamics 365 Human Resources direttamente, ci sono funzionalità aggiuntive che è possibile utilizzare per accedere ai dati:

- È possibile distribuire un database SQL di Azure nel proprio tenant di Azure e usare la funzionalità per portare il proprio database (BYOD) per sincronizzare i dati. Per ulteriori informazioni, vedere [Portare il proprio database (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md).

- È possibile usare l'integrazione di Dataverse per sincronizzare le entità selezionate nel database Dataverse. Per ulteriori informazioni, vedi [Tabelle Dataverse](hr-developer-entities.md). 

## <a name="how-often-is-my-production-database-backed-up"></a>Con quale frequenza viene eseguito il backup del database di produzione? 

I database sono protetti da backup automatici con le seguenti frequenze:

| Tipo di backup | Frequenza |
| --- | --- |
| Backup completo del database | Ogni settimana |
| Backup differenziale del database | Ogni 12-24 ore |
| Backup del registro delle transazioni | Ogni 5-10 minuti |

Microsoft conserva backup sufficienti per consentire il ripristino temporizzato (PITR) negli ultimi 14 giorni. 

Per ulteriori informazioni, vedere  [Informazioni sui backup automatici del database SQL](/azure/azure-sql/database/automated-backups-overview?tabs=single-database). 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a>È possibile richiedere una copia del backup del database di produzione? 

N. Tuttavia, è possibile inviare una richiesta di servizio di aggiornamento del database per copiare l'ambiente di produzione nell'ambiente Sandbox. È possibile distribuire un database SQL di Azure nel proprio tenant di Azure e usare la funzionalità BYOD per sincronizzare i dati dall'ambiente di produzione. Per ulteriori informazioni, vedere [Portare il proprio database (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md). 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a>Come è possibile spostare l'ambiente Sandbox in Produzione per la fase operativa? 

Poiché una funzione di copia non è disponibile per spostare l'ambiente da un Sandbox a un ambiente di produzione, è necessario utilizzare i pacchetti di dati per spostare i dati nell'ambiente di produzione.  

Si consiglia di mantenere un elenco chiaro di entità configurate nell'ambiente Sandbox durante tutto il progetto. Quindi testare il processo di passaggio e migrazione di tutti i pacchetti di dati necessari per la fase operativa. È necessario spostare manualmente tutti i pacchetti di dati nell'ambiente di produzione quando si è pronti per la fase operativa. 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a>Cosa fare se l'ambiente di produzione non funziona? 

Per segnalare un'interruzione di produzione, seguire la procedura descritta in  [Segnalare un'interruzione di produzione](../fin-ops-core/dev-itpro/lifecycle-services/report-production-outage.md). 

 ## <a name="see-also"></a>Vedere anche

 [Prepararsi per la fase operativa](hr-admin-go-live-prepare.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]