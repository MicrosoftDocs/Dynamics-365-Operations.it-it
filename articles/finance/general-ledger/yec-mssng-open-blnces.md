---
title: Saldo iniziale mancante nella chiusura di fine anno
description: In questo argomento viene illustrato perché il saldo iniziale potrebbe mancare quando si chiude un anno e come ricostruire il saldo se manca.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4bebf35a8959d4f72d46d4b40e5487f499b2756d
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356654"
---
# <a name="year-end-close-missing-opening-balances"></a>Saldo iniziale mancante nella chiusura di fine anno

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato perché il saldo iniziale potrebbe mancare quando si chiude un anno e come ricostruire il saldo se manca.

### <a name="symptom"></a>Sintomo

Perché non sono presenti i saldi iniziali dopo l'esecuzione della chiusura di fine anno della contabilità generale? 

### <a name="resolution"></a>Risoluzione

Di seguito sono riportate le cose da verificare se è stato chiuso un anno nella contabilità generale e quindi è stato generato un bilancio di verifica che non riporta i saldi iniziali per l'anno fiscale successivo.

Se il campo **Annulla chiusura precedente** è impostato su **Sì**, la chiusura di fine anno precedente per lo stesso anno fiscale viene annullata. Quando si esegue un processo di annullamento della chiusura di fine anno, tutte le voci per il saldo finale e il saldo iniziale vengono eliminate, come se la chiusura di fine anno non fosse mai stata eseguita. Anche i giustificativi vengono eliminati. Il processo di chiusura di fine anno non viene ripetuto automaticamente. È necessario rieseguire il processo, questa volta aggiornando l'opzione **Annulla chiusura precedente** su **No**.

Questo scenario è trattato nell'argomento Domande frequenti sulla chiusura di fine anno. Per ulteriori informazioni, vedere [Domande frequenti sulle attività di fine anno](faq-year-end-activities.md).

### <a name="symptom"></a>Sintomo

È stata eseguita la chiusura di fine anno con l'opzione **Annulla chiusura precedente** impostata su **No** e ancora non sono stati restituiti i saldi iniziali per l'anno fiscale.

### <a name="resolution"></a>Risoluzione

Per prima cosa controllare lo stato del processo batch. La chiusura di un anno include una serie di attività separate, ma il passaggio più critico è l'attività batch con la descrizione dell'attività **Passaggio 5.0.0**. Durante questo passaggio viene eseguita la registrazione delle transazioni di apertura e, facoltativamente, delle transazioni di chiusura nella contabilità generale. 

[![Elenco storico batch.](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)

Se questo passaggio è terminato con esito positivo, ma i saldi iniziali non sono presenti nella pagina **Richiesta informazioni bilancio di verifica** (**Contabilità generale > Richieste informazioni e report > Bilancio di verifica**), rivedere i risultati del processo batch di chiusura di fine anno per verificare se il passaggio per la ricostruzione dei saldi è stato completato correttamente.

[![Risultati del processo batch di chiusura di fine anno.](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)

Se questo passaggio non è riuscito per qualsiasi motivo, è probabile che le transazioni di apertura (e facoltativamente di chiusura) siano state registrate correttamente. È possibile verificare che le transazioni di contabilità generale siano state registrate correttamente utilizzando la pagina **Richiesta informazioni transazioni giustificativo** specificando il numero del giustificativo e la data forniti nella finestra di dialogo di chiusura di fine anno per l'anno che è stato chiuso, (**Contabilità generale > Richieste informazioni e report > Transazioni giustificativo**).

[![Richiesta informazioni transazioni giustificativo.](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)

Se sono presenti i giustificativi di apertura (e facoltativamente di chiusura), non è necessario riavviare la chiusura di fine anno. Fare riferimento alla sezione successiva per informazioni su come procedere.

### <a name="symptom"></a>Sintomo

Il passaggio per la ricostruzione dei saldi nella chiusura di fine anno non è riuscito, occorre rieseguire l'intero processo di chiusura di fine anno?

### <a name="resolution"></a>Risoluzione

Il passaggio della ricostruzione dei saldi aggiorna i saldi di contabilità generale utilizzati quando viene generata la richiesta informazioni bilancio di verifica.  È il passaggio finale del processo di chiusura di fine anno.  Se questo passaggio è l'unico passaggio non riuscito, le transazioni di contabilità generale sono state registrate correttamente.  Non è necessario ripetere la chiusura di fine anno. È possibile eseguire il processo per ricostruire manualmente i saldi utilizzando la pagina **Set di dimensioni finanziarie** (**Contabilità generale > Piano dei conti > Dimensioni > Set di dimensioni finanziarie**).

[![Pulsante Ricostruisci saldi nella pagina Set di dimensioni finanziarie.](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)

Se l'elaborazione di questo passaggio richiede molto tempo, si consiglia di rivedere le procedure consigliate per i set di dimensioni finanziarie come descritto in [Procedure consigliate per l'aggiornamento dei set di dimensioni finanziarie](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets). 

