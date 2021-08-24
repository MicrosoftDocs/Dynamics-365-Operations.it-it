---
title: Home page di Finance insights (anteprima)
description: Finance insights fornisce modelli configurabili ed estendibili per aiutarti a prevedere in modo accurato e intelligente il flusso di cassa della tua azienda, prevedere quando riceverai il pagamento per i crediti in sospeso e generare una proposta di budget che può accelerare il processo di impostazione budget. Tutte queste funzionalità si basano su modelli di apprendimento automatico intelligenti.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 8c9d5b9857e978eb5e591f4d854d687f33b438025e81fe2c827ab7ecdb2be4e4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768821"
---
# <a name="finance-insights-home-page-preview"></a>Home page di Finance insights (anteprima)

[!include [banner](../includes/banner.md)]

Finance insights fornisce modelli configurabili ed estendibili per aiutarti a prevedere in modo accurato e intelligente il flusso di cassa della tua azienda, prevedere quando riceverai il pagamento per i crediti in sospeso e generare una proposta di budget che può accelerare il processo di impostazione budget. Tutte queste funzionalità si basano su modelli di apprendimento automatico intelligenti. Quando queste nuove funzionalità vengono combinate con l'automazione nei pagamenti e negli incassi dei fornitori, costituiscono un sistema finanziario avanzato e intelligente che guida il processo decisionale e ti aiuta ad agire per rispondere efficacemente alle sfide aziendali attuali e previste.

> [!NOTE]
> È disponibile un'anteprima di Finance insights per la distribuzione negli Stati Uniti, in Canada, nel Regno Unito, in Europa, in Asia Pacifico, in Australia e in Nuova Zelanda. Microsoft sta aggiungendo in modo incrementale il supporto per più aree geografiche. Per abilitare Finance Insights negli ambienti di produzione, è necessario abilitare prima le funzionalità [Esporta in Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md) nell'ambiente di produzione.

> [!NOTE]
> Questa funzionalità viene offerta come un set di funzionalità di anteprima. Come funzionalità di anteprima, non dovresti utilizzare i modelli di machine learning risultanti per guidare o influenzare le tue decisioni aziendali o proposte di budget. L'utilizzo di questa funzione è regolato dalle [Condizioni d'uso supplementari](https://go.microsoft.com/fwlink/?linkid=2105274).

## <a name="prerequisites"></a>Prerequisiti

Questa sezione elenca i requisiti per l'utilizzo di Finance insights. Ove possibile, vengono forniti collegamenti a fonti di informazioni aggiuntive.

### <a name="legal-requirements"></a>Requisiti legali

Per candidarti al programma di anteprima, compila il [contratto per l'anteprima di Finance insights per Dynamics 365 Finance](https://forms.office.com/FormsPro/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR56j8lZs0FdAvwT75_WNFyxUM1c0Uzc1RFpaU1RVTEwxVTNWUERPRThUSy4u).

### <a name="system-requirements"></a>Requisiti di sistema

È necessario un ambiente di livello 2 (multi-box) per visualizzare in anteprima Finance Insights. Per informazioni di background sugli ambienti, vedere [Pianificazione ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

### <a name="version-requirements"></a>Requisiti di versione

Questo documento si applica alla versione 10.0.11 dell'app Finance and Operations (Platform update 35) e versioni successive.

### <a name="historical-data-requirements"></a>Requisiti relativi ai dati storici

È necessario almeno un anno di fatture dei clienti per eseguire correttamente il training del modello di apprendimento automatico utilizzato per la funzione Previsioni di pagamento del cliente.

### <a name="role-and-permission-requirements"></a>Ruolo e requisiti di autorizzazione

Le modifiche verranno apportate a Microsoft Dynamics 365 Finance, Microsoft Dynamics Lifecycle Services (LCS), Power Apps e Azure. Sono necessarie le autorizzazioni corrette in questi ambienti. Ecco alcuni esempi delle modifiche che verranno apportate:

- Verrà creato un nuovo ambiente in Microsoft Power Platform.
- In Azure verranno creati un account di archiviazione, un Key Vault e un'applicazione.
- L'amministratore del tenant di Active Directory dovrà autorizzare l'applicazione AI Builder ad accedere al data lake.
- La funzionalità verrà attivata in Dynamics 365.

La conoscenza del processo di creazione e gestione delle risorse in Azure, Microsoft Dataverse e LCS sarà utile durante il completamento di questo processo.

## <a name="configure-finance-insights"></a>Configurare Finance insights

È necessario completare alcuni passaggi di configurazione prima di poter utilizzare Finance insights. Per ulteriori informazioni sulla configurazione di Finance insights, vedere.
  - Per le versioni fino alla 10.0.19: [Configurazione per Finance insights (anteprima) - versioni fino alla 10.0.19](configure-for-fin-insites.md).
  - Per le versioni 10.0.20 e successive: [Configurazione per Finance Insights (anteprima) - versioni 10.0.20 e successive](configure-for-fin-insites-PubPrvw.md).

## <a name="create-a-data-integrator-project"></a>Creare un progetto di integrazione dei dati

Dovrai creare un progetto di integrazione di dati in modo da creare un flusso di dati generati dal modello di apprendimento automatico in Dynamics 365 Finance. Per i passaggi per creare tale progetto, vedi [Crea un progetto di integrazione dei dati](create-data-integrate-project.md).

## <a name="enable-finance-insights-capabilities"></a>Abilitare le funzionalità di Finance insights

Dopo aver completato i passaggi di configurazione e configurato i dati demo, è necessario attivare e configurare ogni funzionalità che prevedi di utilizzare: previsioni di pagamento del cliente, previsione di cassa e proposte di budget.

### <a name="enable-customer-payment-predictions"></a>Abilitare le previsioni di pagamento del cliente
Se utilizzi i dati dimostrativi per testare le previsioni di pagamento dei clienti, è consigliabile importare dati dimostrativi aggiuntivi per creare correttamente il tuo modello di intelligenza artificiale. 

Per abilitare le previsioni di pagamento del cliente, è necessario completare una serie di passaggi per creare un modello di apprendimento automatico che utilizza i dati della tua organizzazione per generare previsioni su quando è probabile che i clienti paghino le fatture in sospeso e quando è probabile che vengano pagate fatture specifiche. Per ulteriori informazioni e per i passaggi specifici da completare, vedi [Abilitare le previsioni di pagamento dei clienti](enable-cust-paymnt-prediction.md). 

### <a name="enable-cash-flow-forecasting"></a>Abilitare la previsione di cassa
Per abilitare la previsione di cassa, è necessario completare una serie di passaggi per creare un modello di apprendimento automatico che utilizzi i dati dell'organizzazione per generare previsioni di cassa. Per ulteriori informazioni e per i passaggi specifici da completare, vedi [Abilitare le previsioni di cassa](enable-cash-flow-forecasting.md).

### <a name="enable-budget-proposals"></a>Abilitare proposte di budget

La funzione Proposte di budget utilizza un modello di apprendimento automatico insieme ai dati storici della tua organizzazione per generare una proposta di budget. La proposta generata può aiutarti a iniziare un processo di definizione del budget più efficace ed efficiente di un processo manuale. Per i passaggi specifici per abilitare questa funzionalità, vedi [Abilitare proposte di budget](enable-budget-proposal.md). 

## <a name="using-finance-insights-features"></a>Utilizzo delle funzionalità di Finance insights

### <a name="using-customer-payment-predictions"></a>Utilizzo delle previsioni di pagamento del cliente

La previsione di cassa intelligente si basa sulla funzionalità di previsione di cassa esistente in Dynamics 365 Finance. Per rivedere la capacità esistenti, vedi [Previsione di cassa](../cash-bank-management/cash-flow-forecasting.md).

- Per scoprire come le previsioni di pagamento del cliente possono fornire le informazioni necessarie per svolgere proattivamente le attività di riscossione, vedi [Utilizza le previsioni di pagamento del cliente](use-customer-payment-predictions.md).
- Per informazioni che possono aiutare a valutare l'efficacia del modello di previsione dopo aver iniziato a utilizzare la funzionalità, vedi [Valutare il modello di previsione del pagamento del cliente iniziale](evaluate-payment-prediction.md).
- Per informazioni che possono aiutare a rettificare i dati utilizzati per costruire la previsione e quindi migliorarne l'efficacia, vedi [Migliorare il modello di previsione](improve-model.md).

Per ulteriori informazioni sui risultati dei modelli di previsione IA, vedi [Risultati dei modelli di apprendimento automatico](confusion-matrix.md).

### <a name="using-cash-flow-forecasts"></a>Utilizzo delle previsioni di cassa

La funzionalità di previsione di cassa può aiutarti a stimare più accuratamente la tua posizione di cassa. 

- Per conoscere le nuove funzionalità nelle previsioni di cassa, vedi [Previsione di cassa](cash-flow-forecast-intro.md).
- Per informazioni sull'importazione di dati esterni da includere nella previsione di cassa qui, vedi [Utilizzare dati esterni nelle previsioni di cassa](external-data-in-cash-flow.md). 
- Per informazioni su come utilizzare un modello di intelligenza artificiale per prevedere il flusso di cassa a breve termine, vedi [Posizione di cassa](cash-position.md).
- Per informazioni sul salvataggio delle posizioni dei flussi di cassa e delle previsioni di cassa come snapshot e per confrontare uno snapshot con i valori effettivi, vedi [Panoramica degli snapshot](payment-snapshots.md).

### <a name="using-budget-proposal"></a>Utilizzo delle proposte di budget

Per informazioni su come accelerare la creazione di un budget, vedi [Proposte di budget](budget-proposals.md). 

## <a name="feedback-and-support"></a>Feedback e supporto

Invia un messaggio e-mail a [Informazioni dettagliate sui pagamenti dei clienti (anteprima)](mailto:fiap@microsoft.com) se sei interessato a fornire feedback o hai bisogno di supporto.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
