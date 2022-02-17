---
title: Definire e gestire un programma di benefit
description: Le risorse umane forniscono un set di strumenti che possono essere utilizzati per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori. Questo argomento fornisce informazioni su come impostare e gestire i benefit.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 1f2bfa901aa299a091194978ee95ff0e69f2cdbf
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065353"
---
# <a name="define-and-manage-a-benefits-program"></a>Definire e gestire un programma di benefit


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Human Resources fornisce un set di strumenti che possono essere utilizzati per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori. Questo argomento fornisce informazioni su come impostare e gestire i benefit.

## <a name="benefit-setup"></a>Impostazione dei benefit

Prima che i lavoratori possano essere iscritti al benefit, è necessario creare gli elementi di ogni benefit. Questi elementi combinano piani di benefit simili e definiscono le impostazioni predefinite, ad esempio le percentuali di detrazione e i dettagli di contabilità. Molte di queste impostazioni possono essere modificate una volta che i lavoratori sono iscritti al benefit. Per ciascun piano di benefit, un'organizzazione può offrire più opzioni di iscrizione oppure un lavoratore può rinunciare all'iscrizione nel piano. 

[![Flusso di elaborazione benefit.](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Elementi benefit

Prima di iniziare a creare i benefit e iscrivere i lavoratori, è necessario definire gli elementi che costituiscono un benefit: il tipo, il piano e le opzioni.

-   **Tipo**: una raccolta di piani relativi a un benefit specifico, ad esempio assistenza sanitaria o parcheggio.
-   **Piano**: un benefit specifico che un fornitore offre in base a un contratto.
-   **Opzione**: il livello di copertura, ad esempio per il singolo dipendente o per il dipendente e il coniuge/partner.

Per ogni tipo di benefit, ad esempio visivo o dentistico, un'organizzazione può offrire uno o più piani ai lavoratori. Per ciascun piano, l'organizzazione può offrire opzioni diverse. Ad esempio, i lavoratori possono acquistare la copertura aggiuntiva dell'assicurazione vitalizia in una, due o tre volte la retribuzione annuale. Ogni combinazione di piano e di opzioni diventa un benefit a cui i lavoratori possono iscriversi. 

[![immagine benefit.](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>Idoneità
Molti fattori determinano l'idoneità del lavoratore per diversi tipi di benefit che un datore di lavoro offre. Quando si crea un benefit in Dynamics 365 Human Resources, è possibile impostare il tipo di idoneità applicabile al benefit. 

È possibile mettere un benefit a disposizione di tutti i lavoratori. Ad esempio, alcune aziende offrono a tutti i dipendenti il pass per il parcheggio come benefit extrasalariale. Quando si crea il benefit, impostare l'idoneità su **Tutti i lavoratori sono idonei**. 

Per altri benefit, ad esempio i pignoramenti e i gettiti di un'imposta, l'idoneità non è applicabile. Quando si creano questi tipi di benefit, si imposta l'idoneità su **Ignora elaborazione idoneità**. 

Infine, l'idoneità al benefit può essere basata su regole. Ad esempio, un'azienda offe due tipi di premio assicurativo sulla vita ai dipendenti. I dipendenti esecutivi sono idonei a un piano di assicurazione sulla vita, mentre gli altri dipendenti a tempo pieno sono idonei a un altro piano di assicurazione sulla vita. In Human Resources, è possibile creare una regola di idoneità al benefit per individuare tutti i dipendenti esecutivi e un'altra regola per individuare tutti gli altri dipendenti a tempo pieno, quindi applicare tali regole al benefit appropriato.

## <a name="enrollment"></a>Iscrizione
Dopo aver creato i benefit che l'organizzazione offre e l'idoneità determinata, è possibile iscrivere i lavoratori al benefit. È possibile iscrivere un singolo lavoratore ai benefit oppure è possibile iscrivere più lavoratori a uno o più benefit durante il singolo processo. 

Talvolta, un'organizzazione smette di offrire determinati benefit. In questo caso, è necessario aggiornare il benefit e i lavoratori che ne hanno titolo. La scadenza dei benefit di massa consente di modificare contemporaneamente la data di scadenza sia di un benefit sia delle iscrizioni dei lavoratori al benefit. È inoltre possibile selezionare più lavoratori iscritti a un benefit e modificare la data di fine delle copertura. 

In modo analogo, la proroga di benefit collettiva consente di estendere la data di scadenza sia di un benefit che delle iscrizioni del lavoratore per il benefit, se si decide di offrire un benefit più lungo di quanto originariamente pianificato.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
