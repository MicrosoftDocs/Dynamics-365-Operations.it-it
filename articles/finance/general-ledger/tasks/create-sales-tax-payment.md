---
title: Creare un pagamento IVA
description: La procedura di liquidazione e registrazione liquida i saldi IVA nei conti IVA e li registra in contropartita nel conto di liquidazione IVA per un periodo specifico.
author: twheeloc
ms.date: 01/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c388a8f98cd4581abe2ec13d8922e232321e4039
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735935"
---
# <a name="create-a-sales-tax-payment"></a>Creare un pagamento IVA

[!include [banner](../../includes/banner.md)]

La procedura di liquidazione e registrazione liquida i saldi IVA nei conti IVA e li registra in contropartita nel conto di liquidazione IVA per un periodo specifico.

1. Vaia a **Imposta > Dichiarazioni > IVA > Liquida e registra IVA**.
2. Nel campo **Periodo di liquidazione**, selezionare il pulsante a discesa per aprire la ricerca.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Immettere una data nel campo **Dal**. Se non selezioni l'opzione **Includi correzioni** nella pagina **Parametri di contabilità generale**, la liquidazione può essere elaborata per versioni diverse. **Originale** è la prima liquidazione per un intervallo periodico e può essere elaborata una sola volta per un intervallo periodico. Le ultime correzioni sistemeranno le transazioni IVA che sono state registrate dopo che la versione originale è stata creata.
5. Nel campo **Data della transazione** immettere una data.
6. Seleziona **OK**. Viene stampato il report **Pagamenti IVA** per rivedere le transazioni IVA liquidate nel periodo.

A partire da Finance versione 10.0.24, è possibile omettere che il report **Pagamenti IVA** venga generato direttamente subito dopo che la procedura periodica **Liquida e registra IVA** sia implementatata con la funzionalità **Separa generazione report pagamenti IVA da liquidazione IVA** nell'area di lavoro **Gestione funzionalità**.

Quando la funzionalità è abilitata, una volta completato il processo di liquidazione non viene stampato alcun report di pagamenti IVA. Si riceverà invece il seguente messaggio: "La liquidazione e la registrazione IVA sono state completate. Il giustificativo "xxxx, m/g/aaaa" è stato registrato."

È comunque possibile eseguire il report di pagamenti IVA manualmente andando a **Imposta** > **Richieste di informazioni e report** > **Richieste di informazioni su IVA** > **Pagamenti IVA**.

## <a name="performance-consideration"></a>Considerazioni sulle prestazioni

La procedura di pagamento dell'IVA può richiedere molto tempo per essere completata. I principali fattori che influiscono sull'esecuzione della procedura sono il numero di fatture nel periodo di liquidazione e il numero di registrazioni che devono essere registrate nel giustificativo di liquidazione IVA. Per aiutare a migliorare le prestazioni, puoi scegliere di ignorare alcune funzionalità che non sono richieste nel tuo processo.

### <a name="enable-the-sales-tax-payment-performance-improvement-feature"></a>Abilita la funzione di miglioramento delle prestazioni del pagamento dell'IVA

La funzionalità **Miglioramento delle prestazioni di pagamento dell'IVA** può aiutare a migliorare le prestazioni della procedura di pagamento dell'IVA aggregando, in una riga, l'importo della valuta contabile e l'importo della valuta di dichiarazione sulle righe giustificative del pagamento dell'IVA che hanno lo stesso conto principale, dimensione contabile e valuta.

1. Andare a **Amministrazione sistema** \> **Aree di lavoro** \> **Gestione funzionalità**.
2. Nella scheda **Tutto**, cerca e seleziona **Miglioramento delle prestazioni di pagamento dell'IVA**.
3. Seleziona **Abilita**.

### <a name="prevent-generation-of-offset-tax-transactions"></a>Prevenire la generazione di transazioni fiscali di compensazione

Per impostazione predefinita, il giustificativo di pagamento IVA registra le transazioni IVA di contropartita contro ogni transazione IVA liquidata nella procedura di pagamento IVA. Queste transazioni IVA compensate sono incluse nel report **Riconciliazione IVA/Registro contabile**. Mostrano il saldo delle transazioni IVA non liquidate durante il periodo.

Tuttavia, le transazioni IVA compensate possono aumentare il carico sulla procedura di pagamento dell'IVA. Pertanto, una versione di anteprima che si chiama **TaxReportGenOffsetTaxTransPerRecordSetFlighting** può essere attivata su richiesta. Questa versione di anteprima può aiutare a migliorare le prestazioni della generazione di transazioni fiscali di compensazione per paesi e regioni ad eccezione di Thailandia, Polonia, Ungheria, Lituania, Malesia, India, Italia, Russia, Repubblica Ceca, Estonia e Lettonia.

> [!NOTE]
> Se sono presenti campi personalizzati nella tabella delle transazioni fiscali, il periodo di pubblicazione non può essere attivato.

Poiché il report **Riconciliazione IVA/Registro contabile** viene generalmente utilizzato solo per scopi di controllo interno e non è richiesto in molti regimi fiscali, è possibile scegliere di non generare transazioni IVA di contropartita sul giustificativo di pagamento IVA.

1. Vai a **Imposta** \> **Imposte indirette** \> **IVA** \> **Periodi liquidazione IVA**.
2. Seleziona un periodo di liquidazione.
3. Nella Scheda dettaglio **Generale**, imposta l'opzione **Impedisci generazione transazioni contropartita fiscale** su **Sì**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
