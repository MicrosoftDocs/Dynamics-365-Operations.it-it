---
title: Previsione di cassa (anteprima)
description: Questo argomento descrive la funzionalità di previsione di cassa.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 0df58d3571b124acbd1edbc6d6acdd49479c309e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990591"
---
# <a name="cash-flow-forecast-preview"></a>Previsione di cassa (anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Il flusso di cassa è fondamentale per qualsiasi azienda. Anche le aziende redditizie possono affrontare l'insolvenza se non mantengono il flusso di cassa per soddisfare le esigenze immediate. La funzionalità di previsione di cassa in Finance Insights può aiutare le aziende a monitorare e gestire i propri saldi di cassa in modo efficace. Questa funzionalità utilizza l'apprendimento automatico per aiutare le aziende a prevedere i flussi di cassa in modo più accurato rispetto a prima. Può anche aiutare i responsabili a prendere decisioni che ottimizzano le opportunità nel contesto della loro attuale posizione di cassa. 

Per la maggior parte delle aziende, la gestione del flusso di cassa e l'esecuzione della previsione di cassa è un processo noioso, ripetitivo e manuale. La maggior parte delle aziende fa affidamento alle soluzioni di Microsoft Excel che hanno diversi gradi di complessità. Le sfide della previsione accurata del flusso di cassa includono quanto segue:

- I dati non sono disponibili per i decision maker perché sono dispersi in più posizioni, tra cui: 
  - Sistema di pianificazione delle risorse aziendali o contabilità
  - Software di pianificazione finanziaria
  - Excel
  - Applicazioni software aggiuntive 
- La previsione si basa sulla Knowledge Base interna che risiede in "silo" all'interno di ogni dominio o reparto.
- La misurazione dell'accuratezza della di cassa dopo che i dati finanziari sono stati realizzati è incerta e difficile.
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a>Dettagli sulla funzionalità di previsione di cassa
La funzionalità Previsioni di cassa include le seguenti funzionalità. 

- Semplifica l'integrazione dei dati sul flusso di cassa da sistemi esterni a Dynamics 365 Finance. Le previsioni di cassa possono anche utilizzare il framework di importazione/esportazione dei dati. Questo framework semplifica l'integrazione con Excel OData. È inoltre possibile combinare i dati da più origini per creare una soluzione completa per il flusso di cassa. 

- Introduce una posizione di cassa intelligente. La posizione di cassa viene creata in base al comportamento di pagamento del cliente per prevedere quando un'azienda può aspettarsi l'arrivo di liquidità nei suoi conti. Analizza inoltre i modelli storici di pagamento dei fornitori, per prevedere quando è probabile che le fatture e gli ordini futuri verranno pagati. 

- Introduce la previsione di cassa intelligente per previsioni a lungo termine, utilizzando previsioni di serie temporali attraverso l'integrazione automatizzata con AI Builder.

- Offre la possibilità di salvare posizioni o previsioni specifiche di cassa, modificarle e quindi confrontare e misurare facilmente le prestazioni previste con i dati finanziari effettivi.

- Consente l'analisi what-if attraverso il confronto di snapshot. Ad esempio, è possibile creare più snapshot che rappresentano visualizzazioni ottimistiche, pessimistiche e più realistiche del flusso di cassa, quindi confrontare e visualizzare le differenze.

- Offre la possibilità di visualizzare la previsione di cassa in più valute, tra persone giuridiche e filtrare e visualizzare il flusso di cassa relativo a un conto bancario. 

- Consente di filtrare e visualizzare i conti bancari correlati alle dimensioni finanziarie.

La funzionalità di previsione di cassa in Dynamics 365 Finance consentirà alla tua organizzazione di trasformare la proiezione del flusso di cassa noiose, complesse e ripetitive in un processo semplice e automatizzato. L'automazione degli aspetti più noiosi della previsione di cassa consente di concentrarsi sul processo decisionale critico per ottenere i risultati aziendali desiderati.

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a>Configurazione di dimensioni per la previsione di cassa
Una nuova scheda nella pagina **Configurazione della previsione di cassa** consente di controllare quali dimensioni finanziarie utilizzare per filtrare nell'area di lavoro **Previsione di cassa**. Questa scheda verrà visualizzata solo quando la funzione Previsioni di cassa è abilitata. 

Nella scheda **Dimensioni**, scegli dall'elenco delle dimensioni da utilizzare per i filtri e utilizza i tasti freccia per spostarle nella colonna di destra. È possibile selezionare solo due dimensioni per filtrare i dati di previsione di cassa. 

#### <a name="privacy-notice"></a>Informativa sulla privacy
Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]