---
title: Sperimentazione in Dynamics 365 Commerce
description: La sperimentazione consente la creazione, la modifica e la gestione dei layout di pagina e dei trattamenti di contenuti in Creazione di siti Web. Il supporto per la sperimentazione end-to-end è abilitato per le pagine e le entità di e-commerce in una pagina.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: overview
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1ef877072ba7ffe1b0326cf8d526b512b5ab30b8
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946216"
---
# <a name="experimentation-in-dynamics-365-commerce"></a>Sperimentazione in Dynamics 365 Commerce
Usa la sperimentazione in Dynamics 365 Commerce per convalidare ipotesi sull'efficacia delle pagine di e-commerce e prendere decisioni con fiducia in base ai dati. Commerce supporta i test A/B su pagine, moduli e frammenti e ti consente di misurare l'impatto delle modifiche proposte sul tuo sito web.

È possibile creare, modificare e gestire trattamenti di pagine e contenuti noti come **varianti** in Creazione di siti Web di Commerce. Commerce si integra con servizi di terze parti che puoi utilizzare per creare esperimenti e assegnazioni di trattamenti. I flussi di eventi in tempo reale acquisiti in Commerce abilitano l'analisi che definisce i risultati dell'esperimento nel servizio di terze parti. Puoi quindi utilizzare queste analisi per supportare o confutare la tua ipotesi.

## <a name="set-up-prerequisites"></a> Prerequisiti per l'impostazione

1. **Ottenere la versione corretta di Commerce** - Aggiornare la libreria dei moduli, il kit SDK per l'estendibilità del canale online e Commerce Scale Unit a Commerce versione 10.0.13 o versione successiva.
1. **Configurare un connettore di sperimentazione** - Un connettore di sperimentazione consente a Commerce di connettersi a servizi di terze parti per recuperare l'elenco di esperimenti e determinare quando mostrare un esperimento a un utente. Puoi acquistare un connettore di terze parti in [AppSource](https://appsource.microsoft.com). Segui le istruzioni di configurazione fornite dall'editore. In alternativa, puoi utilizzare il connettore di prova di esempio di Commerce per testare il flusso di lavoro di sperimentazione senza dover configurare un servizio esterno. Per ulteriori informazioni, vedi [Configurare e abilitare i connettori](e-commerce-extensibility/connectors.md). 
1. **Attivare i flag della funzionalità di sperimentazione in Commerce** - Puoi abilitare la sperimentazione a livello di tenant o di sito selezionando rispettivamente **Impostazioni tenant \> Funzionalità**, o **Impostazioni sito \> Funzionalità**. Attiva il flag **Sperimentazione** per iniziare a creare variazioni del modulo. La disabilitazione di questo flag impedisce agli utenti di vedere tutti gli esperimenti e rimuove tutte le funzioni di modifica in Creazione di siti Web.
    
## <a name="experimentation-lifecycle"></a>Ciclo di vita della sperimentazione

L'impostazione di un esperimento, la creazione di varianti e l'esecuzione di un esperimento è un processo iterativo. Il diagramma seguente illustra il ciclo di vita della sperimentazione in Commerce e nel servizio di terze parti. 

[ ![Ciclo di vita della sperimentazione.](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)

Per ulteriori informazioni su ciascun passaggio del processo di sperimentazione, fai riferimento ai seguenti articoli.
- [Identificare un'ipotesi e determina le metriche per un esperimento](experimentation-identify.md)
- [Configurare un esperimento](experimentation-setup.md)
- [Connettere e modificare un esperimento](experimentation-connect-edit.md)
- [Visualizzare in anteprima e pubblicare un esperimento](experimentation-preview-publish.md)
- [Eseguire e monitorare un esperimento](experimentation-run-monitor.md)
- [Promuovere una variazione e completare un esperimento](experimentation-review-complete.md)

> [!NOTE]
> Per sapere dove si trova un esperimento nel ciclo di vita, selezionare **Esperimenti** nel riquadro di spostamento a sinistra in Creazione di siti Web. Viene visualizzato un elenco di esperimenti con lo stato di ogni esperimento sia in Commerce che nel servizio di terze parti. Per ulteriori informazioni, vedi [Esaminare lo stato di un esperimento](experimentation-status.md).

## <a name="next-step"></a>Passaggio successivo
[Identificare un'ipotesi e determinare le metriche per un esperimento](experimentation-identify.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
