---
title: Sperimentazione in Dynamics 365 Commerce
description: La sperimentazione consente la creazione, la modifica e la gestione dei layout di pagina e dei trattamenti di contenuti in Creazione di siti Web. Il supporto per la sperimentazione end-to-end è abilitato per le pagine e le entità di e-commerce in una pagina.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 8b2e97167d12b8ceecf72af075ee0362101c4fa0
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930231"
---
# <a name="experimentation-in-dynamics-365-commerce"></a>Sperimentazione in Dynamics 365 Commerce
Usa la sperimentazione in Dynamics 365 Commerce per convalidare ipotesi sull'efficacia delle pagine di e-commerce e prendere decisioni con fiducia in base ai dati. Commerce supporta i test A/B su pagine, moduli e frammenti e ti consente di misurare l'impatto delle modifiche proposte sul tuo sito web.

Puoi creare, modificare e gestire trattamenti di pagine e contenuti noti come **varianti** in Creazione di siti Web. Commerce si integra con servizi di terze parti che puoi utilizzare per creare esperimenti e assegnazioni di trattamenti. I flussi di eventi in tempo reale acquisiti in Commerce abilitano l'analisi che definisce i risultati dell'esperimento nel servizio di terze parti. Puoi quindi utilizzare queste analisi per supportare o confutare la tua ipotesi.

## <a name="set-up-prerequisites"></a> Prerequisiti per l'impostazione
1. **Ottenere la versione corretta di Commerce** - Aggiorna la libreria dei moduli, il kit SDK per l'estendibilità del canale online e Commerce Scale Unit a Commerce versione 10.0.13 o versione successiva.
1. **Configurare un connettore di sperimentazione** - Un connettore di sperimentazione consente a Commerce di connettersi a servizi di terze parti per recuperare l'elenco di esperimenti e determinare quando mostrare un esperimento a un utente. Puoi acquistare un connettore di terze parti in [AppSource](https://appsource.microsoft.com). Segui le istruzioni di configurazione fornite dall'editore. In alternativa, puoi utilizzare il connettore di prova di esempio di Commerce per testare il flusso di lavoro di sperimentazione senza dover configurare un servizio esterno. Per ulteriori informazioni, vedi [Configurare e abilitare i connettori](e-commerce-extensibility/connectors.md). 
1. **Attivare i flag della funzionalità di sperimentazione in Commerce** - Puoi abilitare la sperimentazione a livello di tenant o di sito selezionando rispettivamente **Impostazioni tenant > Funzionalità** o **Impostazioni sito > Funzionalità**.
    - Abilita il flag **Sperimentazione** per creare varianti dell'esperimento dei moduli in una pagina senza alterare o copiare altri contenuti che non fanno parte dell'esperimento. Ciò garantisce che gli aggiornamenti in corso dei contenuti al di fuori dell'esperimento rimangano sincronizzati durante il ciclo di vita dell'esperimento. La disabilitazione di questo flag impedisce agli utenti di vedere tutti gli esperimenti e rimuove tutte le funzioni di modifica in Creazione di siti Web.
    - Abilita il flag **Sperimenta su pagine o frammenti** per eseguire esperimenti su una pagina o un frammento. In questo modo, viene creata una copia completa dell'istanza dell'intera pagina o frammento per tutti i moduli nella pagina o nel frammento. Utilizza questa modalità quando desideri testare modifiche complete al contenuto o quando la sincronizzazione delle modifiche in corso al contenuto nelle istanze non è un problema. La disabilitazione di questo flag impedisce la creazione e la modifica di nuovi esperimenti su pagine e frammenti.
    > [!NOTE]
    > Il flag **Sperimentazione** deve essere abilitato anche per la funzionalità **Sperimenta su pagine o frammenti** per funzionare.
    
## <a name="experimentation-lifecycle"></a>Ciclo di vita della sperimentazione
L'impostazione di un esperimento, la creazione di varianti e l'esecuzione di un esperimento è un processo iterativo. Il diagramma seguente illustra il ciclo di vita della sperimentazione in Commerce e nel servizio di terze parti. 

[ ![Ciclo di vita della sperimentazione](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)

Per ulteriori informazioni su ciascun passaggio del processo di sperimentazione, fai riferimento ai seguenti argomenti.
- [Identificare un'ipotesi e determina le metriche per un esperimento](experimentation-identify.md)
- [Configurare un esperimento](experimentation-setup.md)
- [Collegare e modificare un esperimento](experimentation-connect-edit.md)
- [Visualizzare un esperimento in anteprima e pubblicarlo](experimentation-preview-publish.md)
- [Eseguire e monitorare un esperimento](experimentation-run-monitor.md)
- [Promuovere una variante e completare un esperimento](experimentation-review-complete.md)

> [!NOTE]
> Per sapere dove si trova un esperimento nel ciclo di vita, vai alla scheda **Esperimenti** in Creazione di siti Web. Viene visualizzato un elenco di esperimenti con lo stato di ogni esperimento sia in Commerce che nel servizio di terze parti. Per ulteriori informazioni, vedi [Esaminare lo stato di un esperimento](experimentation-status.md).

## <a name="next-step"></a>Passaggio successivo
[Identificare un'ipotesi e determinare le metriche per un esperimento](experimentation-identify.md) 
