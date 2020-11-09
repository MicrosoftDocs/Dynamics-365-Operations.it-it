---
title: Preparare per passare alla fase operativa di Human Resources
description: Questa pagina fornisce indicazioni su come prepararsi per la fase operativa con Dynamics 365 Human Resources.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 59d7274c3b40e78209d90960c4514321b736876a
ms.sourcegitcommit: d66fd72342931fad25a696b251c05781280d36c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/14/2020
ms.locfileid: "4011423"
---
# <a name="prepare-for-human-resources-go-live"></a>Preparare per passare alla fase operativa di Human Resources

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
| 5 | Importazioni del pacchetto di dati | Dipende dal progetto | Partner/Cliente | Seguire le istruzioni in [Panoramica della gestione dei dati](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages).|
| 6 | Pronto per la produzione | Dopo che tutti i passaggi precedenti sono stati completati | Partner/Cliente | Il partner/cliente può assumere il controllo dell'ambiente di produzione.|
| 7 | Attività cutover | Dipende dal progetto | Partner/Cliente | |
| 8 | Fase operativa | Dipende dal progetto | Cliente | |

> [!IMPORTANT]
> *I passaggi 3 e 4 vengono completati solo per i clienti idonei per FastTrack.

## <a name="completing-the-lcs-methodology"></a>Completamento della metodologia LCS

Un passaggio fondamentale principale in ogni progetto di implementazione è il passaggio all'ambiente di produzione. 

Per garantire che l'ambiente di produzione venga utilizzato per le operazioni in tempo reale, Microsoft effettua il provisioning dell'istanza di produzione solo quando l'implementazione si avvicina alla fase **operativa** dopo il completamento delle attività richieste nella metodologia LCS. Per ulteriori informazioni sugli ambienti nell'abbonamento, vedere la [Guida alle licenze di Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). 

I clienti devono completare le fasi **Analisi** , **Progetta e sviluppa** e **Test** della metodologia LCS prima che il pulsante  **Configura**  diventa disponibile per la richiesta dell'ambiente di produzione. Per completare una fase in LCS, è necessario prima completare ogni passaggio richiesto in quella fase. Quando tutti i passaggi di una fase sono stati completati, è possibile completare l'intera fase. È sempre possibile riaprire una fase in un secondo momento se è necessario apportare modifiche. Per altre informazioni, vedere  [Lifecycle Services (LCS) per i clienti di app Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs). 

Il processo di completamento di un passaggio ha due parti: 

- Effettuare il lavoro effettivo, come un'analisi degli scostamenti/adeguatezza o un test di accettazione dell'utente (UAT). 
- Contrassegnare il passaggio corrispondente nella metodologia LCS come completato. 

È una buona norma completare i passaggi della metodologia man mano che si procede con l'implementazione. Non aspettare l'ultimo minuto. Non limitare a fare clic su tutti i passaggi in modo da poter ottenere un ambiente di produzione. È nell'interesse del cliente avere un'implementazione solida. 

## <a name="uat-for-your-solution"></a>UAT per la soluzione

Durante la fase UAT, è necessario testare tutti i processi aziendali implementati e le eventuali personalizzazioni apportate in un ambiente Sandbox nel progetto di implementazione. Per garantire un fase operativa di successo, è necessario considerare quanto segue durante il completamento della fase UAT: 

- I test case coprono l'intero ambito dei requisiti. 
- Eseguire il test utilizzando i dati migrati. Questi dati devono includere dati master come lavoratori, mansioni e posizioni. Includere anche i saldi di apertura, come i ratei per congedi e assenze. Infine, includere le transazioni aperte, come le attuali iscrizioni ai benefit. Completare il test con tutti i tipi di dati, anche se il set di dati non è finalizzato. 
- Eseguire il test utilizzando i ruoli di sicurezza corretti (ruoli predefiniti e ruoli personalizzati) assegnati agli utenti. 
- Assicurarsi che la soluzione sia conforme a tutti i requisiti normativi specifici dell'azienda e del settore. 
- Documentare tutte le funzionalità e ottenere l'approvazione dal cliente. 

## <a name="fasttrack-go-live-assessment"></a>Valutazione della fase operativa FastTrack

I clienti che sono idonei per FastTrack e sono impegnati con un FastTrack Solution Architect completeranno una revisione della fase operativa con Microsoft FastTrack. Per ulteriori informazioni, vedere  [Microsoft FastTrack](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview). 

Circa otto settimane prima della fase operativa, il team FastTrack chiederà di compilare un [elenco di controllo per la fase operativa](https://go.microsoft.com/fwlink/?linkid=2146013).

Il project manager o un membro importante del progetto deve completare la lista di controllo della fase operativa durante la fase pre operativa del progetto. In genere, l'elenco di controllo viene completato da quattro a sei settimane prima della data della fase operativa proposta, quando l'UAT è completato o quasi completato. 

Dopo aver completato l'elenco di controllo per la fase operativa, inviarlo tramite e-mail al FastTrack Solution Architect. Includere sempre nell'e-mail una parte interessata importante del cliente e del partner di implementazione. 

Dopo aver inviato l'elenco di controllo, il FastTrack Solution Architect esaminerà il progetto e fornirà una valutazione che descrive i potenziali rischi, le procedure consigliate e le raccomandazioni per una fase operativa di successo del progetto. In alcuni casi, il solution architect potrebbe evidenziare i fattori di rischio e richiedere un piano di mitigazione. 

## <a name="see-also"></a>Vedere anche

[Domande frequenti fase operativa](hr-admin-go-live-faq.md)