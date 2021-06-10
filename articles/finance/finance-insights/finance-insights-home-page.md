---
title: Home page informazioni dettagliate finanziarie (anteprima)
description: Informazioni dettagliate finanziarie fornisce modelli configurabili ed estendibili per aiutarti a prevedere in modo accurato e intelligente il flusso di cassa della tua azienda, prevedere quando riceverai il pagamento per i crediti in sospeso e generare una proposta di budget che può accelerare il processo di impostazione budget. Tutte queste funzionalità si basano su modelli di apprendimento automatico intelligenti.
author: ShivamPandey-msft
ms.date: 07/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 3a78a162469790d797344ce9311c55bfcecd19f4
ms.sourcegitcommit: 273903b7b73ac726d447c50f7086e6d8b0f0f74e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2021
ms.locfileid: "6086991"
---
# <a name="finance-insights-home-page-preview"></a>Home page informazioni dettagliate finanziarie (anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Informazioni dettagliate finanziarie fornisce modelli configurabili ed estendibili per aiutarti a prevedere in modo accurato e intelligente il flusso di cassa della tua azienda, prevedere quando riceverai il pagamento per i crediti in sospeso e generare una proposta di budget che può accelerare il processo di impostazione budget. Tutte queste funzionalità si basano su modelli di apprendimento automatico intelligenti. Quando queste nuove funzionalità vengono combinate con l'automazione nei pagamenti e negli incassi dei fornitori, costituiscono un sistema finanziario avanzato e intelligente che guida il processo decisionale e ti aiuta ad agire per rispondere efficacemente alle sfide aziendali attuali e previste.

È disponibile un'anteprima di Informazioni dettagliate finanziarie per le distribuzioni di valutazione negli Stati Uniti, in Europa e nel Regno Unito. Microsoft sta aggiungendo in modo incrementale il supporto per più aree geografiche.

Le funzionalità di anteprima possono e devono essere attivate solo negli ambienti sandbox di livello 2. I modelli di configurazione e intelligenza artificiale creati in un ambiente sandbox non possono essere migrati in un ambiente di produzione. Per ulteriori informazioni, vedi [Condizioni integrative per le versioni di anteprima di Microsoft Dynamics 365](/dynamics365/legal/supp-dynamics365-preview#:~:text=Supplemental%20Terms%20of%20Use%20for%20Microsoft%20Dynamics%20365,%28governing%20your%20use%20of%20Microsoft%20Dynamics%20365%20Online%29.).

## <a name="prerequisites"></a>Prerequisiti

Questa sezione elenca i requisiti per l'utilizzo di Informazioni finanziarie dettagliate. Ove possibile, vengono forniti collegamenti a fonti di informazioni aggiuntive.

### <a name="legal-requirements"></a>Requisiti legali

Per candidarti al programma di anteprima, compila il [contratto per l'anteprima di Informazioni finanziarie dettagliate per Dynamics 365 Finance](https://forms.office.com/FormsPro/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR56j8lZs0FdAvwT75_WNFyxUM1c0Uzc1RFpaU1RVTEwxVTNWUERPRThUSy4u).

### <a name="system-requirements"></a>Requisiti di sistema

È necessario un ambiente sandbox di livello 2 (multi-box) per visualizzare in anteprima Informazioni finanziarie dettagliate. Per informazioni di background sugli ambienti, vedere [Pianificazione ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

### <a name="version-requirements"></a>Requisiti di versione

Questo documento si applica alla versione 10.0.11 dell'app Finance and Operations (Platform update 35) e versioni successive.

### <a name="historical-data-requirements"></a>Requisiti relativi ai dati storici

È necessario almeno un anno di fatture dei clienti per eseguire correttamente il training del modello di apprendimento automatico utilizzato per la funzione Previsioni di pagamento del cliente.

I dati di esempio sono disponibili per i sistemi demo che dispongono del set di dati demo Contoso.

### <a name="role-and-permission-requirements"></a>Ruolo e requisiti di autorizzazione

Le modifiche verranno apportate a Microsoft Dynamics 365 Finance, Microsoft Dynamics Lifecycle Services (LCS), Power Apps e Azure. Sono necessarie le autorizzazioni corrette in questi ambienti. Ecco alcuni esempi delle modifiche che verranno apportate:

- Verrà creato un nuovo ambiente in Microsoft Power Platform.
- In Azure verranno creati un account di archiviazione, un Key Vault e un'applicazione.
- L'amministratore del tenant di Active Directory dovrà autorizzare l'applicazione AI Builder ad accedere al data lake.
- La funzionalità verrà attivata in Dynamics 365.

La conoscenza del processo di creazione e gestione delle risorse in Azure, Microsoft Dataverse e LCS sarà utile durante il completamento di questo processo.

## <a name="configure-finance-insights"></a>Configurare le informazioni dettagliate finanziarie

È necessario completare alcuni passaggi di configurazione prima di poter utilizzare Informazioni finanziarie dettagliate. Per ulteriori informazioni su come configurare Informazioni finanziarie dettagliate, vedi [Configurazione per Informazioni finanziarie dettagliate](configure-for-fin-insites.md).

## <a name="create-a-data-integrator-project"></a>Creare un progetto di integrazione dei dati

Dovrai creare un progetto di integrazione di dati in modo da creare un flusso di dati generati dal modello di apprendimento automatico in Dynamics 365 Finance. Per i passaggi per creare tale progetto, vedi [Crea un progetto di integrazione dei dati](create-data-integrate-project.md).

## <a name="enable-finance-insights-capabilities"></a>Abilitare le funzionalità di Informazioni finanziarie dettagliate

Dopo aver completato i passaggi di configurazione e configurato i dati demo, è necessario attivare e configurare ogni funzionalità che prevedi di utilizzare: previsioni di pagamento del cliente, previsione di cassa e proposte di budget.

### <a name="enable-customer-payment-predictions"></a>Abilitare le previsioni di pagamento del cliente
Se utilizzi i dati dimostrativi per testare le previsioni di pagamento dei clienti, è consigliabile importare dati dimostrativi aggiuntivi per creare correttamente il tuo modello di intelligenza artificiale. 

Per abilitare le previsioni di pagamento del cliente, è necessario completare una serie di passaggi per creare un modello di apprendimento automatico che utilizza i dati della tua organizzazione per generare previsioni su quando è probabile che i clienti paghino le fatture in sospeso e quando è probabile che vengano pagate fatture specifiche. Per ulteriori informazioni e per i passaggi specifici da completare, vedi [Abilitare le previsioni di pagamento dei clienti](enable-cust-paymnt-prediction.md). 

### <a name="enable-cash-flow-forecasting"></a>Abilitare la previsione di cassa
Per abilitare la previsione di cassa, è necessario completare una serie di passaggi per creare un modello di apprendimento automatico che utilizzi i dati dell'organizzazione per generare previsioni di cassa. Per ulteriori informazioni e per i passaggi specifici da completare, vedi [Abilitare le previsioni di cassa](enable-cash-flow-forecasting.md) 

### <a name="set-up-and-use-cash-flow-forecasting"></a>Configurare e utilizzare la previsione di cassa
Per informazioni su come configurare e utilizzare le previsioni di cassa, vedi [Abilitare la previsione di cassa](enable-cash-flow-forecasting.md). Per ulteriori informazioni su come utilizzare questa funzionalità, vedi [Previsione di cassa](cash-flow-forecast-intro.md).

### <a name="enable-budget-proposals"></a>Abilitare proposte di budget

La funzione Proposte di budget utilizza un modello di apprendimento automatico insieme ai dati storici della tua organizzazione per generare una proposta di budget. La proposta generata può aiutarti a iniziare un processo di definizione del budget più efficace ed efficiente di un processo manuale. Per i passaggi specifici per abilitare questa funzionalità, vedi [Abilitare proposte di budget](enable-budget-proposal.md). 

## <a name="using-finance-insights-features"></a>Utilizzo delle funzionalità di Informazioni finanziarie dettagliate

### <a name="using-customer-payment-predictions"></a>Utilizzo delle previsioni di pagamento del cliente

La previsione di cassa intelligente si basa sulla funzionalità di previsione di cassa esistente in Dynamics 365 Finance. Per rivedere la capacità esistenti, vedi [Previsione di cassa](../cash-bank-management/cash-flow-forecasting.md).

- Per scoprire come le previsioni di pagamento del cliente possono fornire le informazioni necessarie per svolgere proattivamente le attività di riscossione, vedi [Utilizza le previsioni di pagamento del cliente](use-customer-payment-predictions.md).
- Per informazioni che possono aiutare a valutare l'efficacia del modello di previsione dopo aver iniziato a utilizzare la funzionalità, vedi [Valutare il modello di previsione del pagamento del cliente iniziale](evaluate-payment-prediction.md).
- Per informazioni che possono aiutare a regolare i dati utilizzati per costruire la previsione e quindi migliorarne l'efficacia, vedi [Migliorare il modello di previsione](improve-model.md).

Per ulteriori informazioni sui risultati dei modelli di previsione IA, vedi [Risultati dei modelli di apprendimento automatico](confusion-matrix.md).

### <a name="using-cash-flow-forecasts"></a>Utilizzo delle previsioni di cassa

La funzionalità di previsione di cassa può aiutarti a stimare più accuratamente la tua posizione di cassa. 

- Per conoscere le nuove funzionalità nelle previsioni di cassa, vedi [Previsione di cassa](cash-flow-forecast-intro.md).
- Per informazioni sull'importazione di dati esterni da includere nella previsione di cassa qui, vedi [Utilizzare dati esterni nelle previsioni di cassa](external-data-in-cash-flow.md). 
- Per informazioni su come utilizzare un modello di intelligenza artificiale per prevedere il flusso di cassa a lungo termine, vedi [Panoramica delle previsioni di cassa](cash-position.md).
- Per informazioni sul salvataggio delle posizioni dei flussi di cassa e delle previsioni di cassa come snapshot e per confrontare uno snapshot con i valori effettivi, vedi [Panoramica degli snapshot](payment-snapshots.md).

### <a name="using-budget-proposal"></a>Utilizzo delle proposte di budget

Per informazioni su come accelerare la creazione di un budget, vedi [Proposte di budget](budget-proposals.md). 

Dati dimostrativi per una proposta di budget:

## <a name="feedback-and-support"></a>Feedback e supporto

Invia un messaggio e-mail a [Informazioni dettagliate sui pagamenti dei clienti (anteprima)](mailto:fiap@microsoft.com) se sei interessato a fornire feedback o hai bisogno di supporto.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
