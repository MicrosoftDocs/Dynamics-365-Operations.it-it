---
title: Definire e gestire un piano di benefit
description: Le risorse umane forniscono un set di strumenti che possono essere utilizzati per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un&quot;organizzazione offre o elabora per i propri lavoratori. Questo articolo fornisce le informazioni su come impostare e gestire i benefit.
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 81b5c9056001b26c33b2b42a95711ff5b50243e6
ms.openlocfilehash: 9d00d8f6dfa075f53473af31c257deb57c9efa86
ms.lasthandoff: 03/31/2017


---

# <a name="define-and-manage-a-benefits-program"></a>Definire e gestire un piano di benefit

Le risorse umane forniscono un set di strumenti che possono essere utilizzati per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori. In questo argomento vengono fornite informazioni su come impostare i benefit di una gestione.

<a name="benefit-setup"></a>Impostazione di benefit
-------------

Prima che i lavoratori possano essere iscritti al benefit, è necessario creare gli elementi di ogni benefit. Questi elementi combinano piani di benefit simili e definiscono le impostazioni predefinite, ad esempio le percentuali di detrazione e i dettagli di contabilità. Molte di queste impostazioni possono essere modificate una volta che i lavoratori sono iscritti al benefit. Per ciascun piano di benefit, un'organizzazione può offrire più opzioni di iscrizione oppure un lavoratore può rinunciare all'iscrizione nel piano. 

[flusso di processo di benefit![(]. /media/benefit-process-flow1.png)](. /media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Elementi benefit
Prima di iniziare a creare i benefit e iscrivere i lavoratori, è necessario definire gli elementi che costituiscono un benefit: il tipo, il piano e le opzioni.

-   **Tipo**: una raccolta di piani relativi a un benefit specifico, ad esempio assistenza sanitaria o parcheggio.
-   **Piano**: un benefit specifico che un fornitore offre in base a un contratto.
-   **Opzione**: il livello di copertura, ad esempio per il singolo dipendente o per il dipendente e il coniuge/partner.

Per ogni tipo di benefit, ad esempio visivo o dentistico, un'organizzazione può offrire uno o più piani ai lavoratori. Per ciascun piano, l'organizzazione può offrire opzioni diverse. Ad esempio, i lavoratori possono acquistare la copertura aggiuntiva dell'assicurazione vitalizia in una, due o tre volte la retribuzione annuale. Ogni combinazione di piano e di opzioni diventa un benefit a cui i lavoratori possono iscriversi. 

[pic di benefit![(]. /media/benefit-pic.png)](. /media/benefit-pic.png)

## <a name="eligibility"></a>Idoneità
Molti fattori determinano l'idoneità del lavoratore per diversi tipi di benefit che un datore di lavoro offre. Quando si crea un benefit in Microsoft Dynamics 365 per le operazioni, è possibile impostare il tipo di idoneità applicabile al benefit. 

È possibile rendere disponibile un benefit di tutti i lavoratori. Ad esempio, il parcheggio di offerta di alcune società predefinita a tutti i dipendenti come le indennità extrasalariali. Quando si crea il benefit, impostare l'idoneità su **Tutti i lavoratori sono idonei**. 

Per altri benefit, ad esempio sequestri e i gettito di un'imposta, l'idoneità non sarà applicabile. Il siero di ID creato questi tipi di benefit, dopo aver impostato l'idoneità a ** processo di idoneità di esclusione **. 

Infine, l'idoneità al benefit può essere basata su regole. Ad esempio, una società vengono offerti due tipi di premio assicurative di vita ai dipendenti. I dipendenti esecutivi sono idonee per un piano di assicurazione vitalizia, mentre gli altri dipendenti a tempo pieno sono idonee per un altro piano di assicurazione vitalizia. In Dynamics 365 per le operazioni, è possibile creare una regola di idoneità al benefit trovare tutti i dipendenti esecutivi e un'altra regola trovare tutti gli altri dipendenti a tempo pieno e quindi applicare tali regole al benefit appropriato.

## <a name="enrollment"></a>Iscrizione
Dopo aver creato i benefit che l'organizzazione offre e l'idoneità determinata, è possibile iscrivere i lavoratori al benefit. È possibile iscrivere un singolo lavoratore ai benefit oppure è possibile iscrivere più lavoratori a uno o più benefit durante il singolo processo. 

Talvolta, un'organizzazione smette di offrire determinati benefit. In questo caso, è necessario aggiornare il benefit e dei lavoratori che sono iscritti in. Scadenza di massa dei benefit consente di modificare la data di scadenza sia di un benefit che le registrazioni del lavoratore per il benefit. È inoltre possibile selezionare più lavoratori iscritti a un benefit e modificare la data di fine delle copertura. 

In modo analogo, la proroga di benefit collettiva consente di estendere la data di scadenza sia di un benefit che delle iscrizioni del lavoratore per il benefit, se si decide di offrire un benefit più lungo di quanto originariamente pianificato.

<a name="see-also"></a>Vedere anche
--------

[Benefit eligibility policies](benefit-eligibility-policies.md)


