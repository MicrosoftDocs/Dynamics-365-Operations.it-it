---
title: Preparare per passare alla fase operativa di Human Resources
description: Questa pagina fornisce indicazioni su come prepararsi per la fase operativa con Dynamics 365 Human Resources.
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
ms.openlocfilehash: dcec7963bdf70f848249bb2ca5e2208e09f49548
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054790"
---
# <a name="prepare-for-human-resources-go-live"></a>Preparare per passare alla fase operativa di Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [banner](../includes/banner.md)]

Questo argomento descrive come prepararsi per la fase operativa con un progetto Dynamics 365 Human Resources utilizzando Microsoft Dynamics Lifecycle Services (LCS). 

Questo grafico mostra le fasi del processo per la fase operativa. 

![Processo per la fase operativa](./media/hr-admin-go-live-prepare-process.png)

La tabella seguente elenca tutti i passaggi del processo, la durata prevista e chi è responsabile dell'azione.

| Fase | Azione | Durata/Quando | Chi | Note |
| --- | --- | --- | --- |--- |
| 1 | Aggiornare la data della fase operativa in LCS | Almeno 2-3 mesi prima | Partner/Cliente | Le date del passaggio fondamentale devono essere mantenute aggiornate su base continuativa. |
| 2 | Completare e inviare la lista di controllo | Dopo il completamento del test di accettazione dell'utente (UAT) | Partner/Cliente | Seguire le istruzioni fornite in [Valutazione della fase operativa di FastTrack](hr-admin-go-live-prepare.md#fasttrack-go-live-assessment). |
| 3 | Valutazione del progetto (FastTrack) | Architetto FastTrack* | L'architetto fornisce la valutazione dopo aver ricevuto la lista di controllo e continua la revisione fino a quando le domande non vengono chiarite e le attenuazioni sono in atto, se applicabile. |
| 4 | Workshop di progetto (FastTrack) | Architetto FastTrack* | |
| 5 | Importazioni del pacchetto di dati | Dipende dal progetto | Partner/Cliente | Seguire le istruzioni in [Panoramica della gestione dei dati](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).|
| 6 | Pronto per la produzione | Dopo che tutti i passaggi precedenti sono stati completati | Partner/Cliente | Il partner/cliente può assumere il controllo dell'ambiente di produzione.|
| 7 | Attività cutover | Dipende dal progetto | Partner/Cliente | |
| 8 | Fase operativa | Dipende dal progetto | Cliente | |

> [!IMPORTANT]
> *I passaggi 3 e 4 vengono completati solo per i clienti idonei per FastTrack.

## <a name="completing-the-lcs-methodology"></a>Completamento della metodologia LCS

Un passaggio fondamentale principale in ogni progetto di implementazione è il passaggio all'ambiente di produzione. Il processo di completamento di un passaggio ha due parti: 

- Effettuare il lavoro effettivo, come un'analisi degli scostamenti/adeguatezza o un test di accettazione dell'utente (UAT). 
- Contrassegnare il passaggio corrispondente nella metodologia LCS come completato. 

È una buona norma completare i passaggi della metodologia man mano che si procede con l'implementazione. Non aspettare l'ultimo minuto. È nell'interesse del cliente avere un'implementazione solida. 

## <a name="uat-for-your-solution"></a>UAT per la soluzione

Durante la fase UAT, è necessario testare tutti i processi aziendali implementati e le eventuali personalizzazioni apportate in un ambiente Sandbox nel progetto di implementazione. Per garantire un fase operativa di successo, è necessario considerare quanto segue durante il completamento della fase UAT: 

- Si consiglia di avviare il processo UAT con un ambiente pulito e aggiornato in cui i dati della configurazione GOLD vengono copiati nell'ambiente prima dell'inizio del processo UAT. Si consiglia di utilizzare l'ambiente di produzione come ambiente GOLD fino alla fase operativa, momento in cui l'ambiente diventa di produzione.
- I test case coprono l'intero ambito dei requisiti. 
- Eseguire il test utilizzando i dati migrati. Questi dati devono includere dati come lavoratori, mansioni e posizioni. Includere anche i saldi di apertura, come i ratei per congedi e assenze. Infine, includere le transazioni aperte, come le attuali iscrizioni ai benefit. Completare il test con tutti i tipi di dati, anche se il set di dati non è finalizzato. 
- Eseguire il test utilizzando i ruoli di sicurezza corretti (ruoli predefiniti e ruoli personalizzati) assegnati agli utenti. 
- Assicurarsi che la soluzione sia conforme a tutti i requisiti normativi specifici dell'azienda e del settore. 
- Documentare tutte le funzionalità e ottenere l'approvazione dal cliente. 

## <a name="mock-go-live"></a>Simulazione della fase operativa

Prima della fase operativa, è necessario eseguire la relativa simulazione per testare i passaggi necessari per il passaggio dai sistemi legacy al nuovo sistema. Devi eseguire la simulazione della fase operativa in un ambiente sandbox e includere tutti i passaggi nel piano di passaggio.

- Si consiglia di utilizzare l'ambiente di produzione come ambiente di configurazione GOLD fino alla fase operativa.
- Assicurati di disporre di un solido processo di governance per proteggere l'ambiente di produzione da transazioni o aggiornamenti accidentali prima della fase operativa.
- Quando sei pronto per eseguire l'UAT o la simulazione della fase operativa, aggiorna l'ambiente sandbox dall'ambiente di produzione. Per ulteriori informazioni, vedi [Copiare un'istanza](hr-admin-setup-copy-instance.md).
- Testa ogni passaggio del tuo piano di cutover nell'ambiente sandbox, quindi convalida l'ambiente sandbox eseguendo controlli a campione o eseguendo test dagli script UAT nell'ambiente.
  - I test dovrebbero includere tutte le migrazioni dei dati, comprese le trasformazioni necessarie per la fase operativa.
  - Il processo dovrebbe includere una data limite pratica per tutti i sistemi legacy.
  - Assicurati di includere eventuali passaggi del cutover dell'integrazione o passaggi del sistema esterno nel tuo cutover simulato.
- Se riscontri problemi durante il cutover simulato, potrebbe essere necessario un secondo cutover simulato. Per questo motivo, ti consigliamo di pianificare due tagli simulati nel tuo piano di progetto.

## <a name="fasttrack-go-live-assessment"></a>Valutazione della fase operativa FastTrack

I clienti che sono idonei per FastTrack e sono impegnati con un FastTrack Solution Architect completeranno una revisione della fase operativa con Microsoft FastTrack. Per ulteriori informazioni, vedere  [Microsoft FastTrack](/dynamics365/fasttrack/). 

Circa otto settimane prima della fase operativa, il team FastTrack chiederà di compilare un [elenco di controllo per la fase operativa](https://go.microsoft.com/fwlink/?linkid=2146013).

Il project manager o un membro importante del progetto deve completare la lista di controllo della fase operativa durante la fase pre operativa del progetto. In genere, l'elenco di controllo viene completato da quattro a sei settimane prima della data della fase operativa proposta, quando l'UAT è completato o quasi completato. 

Dopo aver completato l'elenco di controllo per la fase operativa, inviarlo tramite e-mail al FastTrack Solution Architect. Includere sempre nell'e-mail una parte interessata importante del cliente e del partner di implementazione. 

Dopo aver inviato l'elenco di controllo, il FastTrack Solution Architect esaminerà il progetto e fornirà una valutazione che descrive i potenziali rischi, le procedure consigliate e le raccomandazioni per una fase operativa di successo del progetto. In alcuni casi, il solution architect potrebbe evidenziare i fattori di rischio e richiedere un piano di mitigazione. 

## <a name="see-also"></a>Vedere anche

[Domande frequenti fase operativa](hr-admin-go-live-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
