---
title: Novità o modifiche in Dynamics 365 Talent (1 ottobre 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4c8392973e7f9c55d425dbe3efb9c8858f71e345
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550161"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-1-2019"></a>Novità o modifiche in Dynamics 365 Talent (1 ottobre 2019)

[!include [banner](includes/banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2509. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="streamlined-employee-entry-and-navigation"></a>Inserimento e navigazione dei dipendenti semplificati

Questa funzionalità è ora disponibile in tutti gli ambienti. Per attivare questa funzionalità, passare ad **Amministrazione sistema > Collegamenti > Impostazioni > Parametri di sistema > Funzionalità di anteprima**. Selezionare **Navigazione e modulo lavoratore avanzati**. In questo modo le modifiche sono valide per tutti gli utenti. È possibile disattivare questa opzione in qualsiasi momento.

Per ulteriori informazioni, vedere [Inserimento e navigazione dei dipendenti semplificati](./streamlined-employee-entry.md). Per guardare un video su queste modifiche, vedere [Panoramica della seconda ondata della versione Dynamics 365 for Talent 2019](https://aka.ms/ROGT19RW2ROV).

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a>È possibile attivare le funzionalità di anteprima negli ambienti Sandbox e di prova

Quando si esegue il provisioning di una nuova istanza di Talent, è possibile specificare se il tipo di istanza è Produzione o Sandbox. Le istanze Sandbox consentono di provare le nuove funzionalità prima dell'utilizzo. Se si desidera aggiornare una delle istanze esistenti al tipo di istanza Sandbox, contattare il supporto tecnico per avviare la richiesta di modifica.

Per ulteriori informazioni su come vengono pubblicate le modifiche, vedere [Eseguire il provisioning di Talent](./provisioning-talent.md).

### <a name="compensation-date-defaults-to-a-different-date-than-the-position-assignment-337694"></a>La data di compensazione viene impostata automaticamente su una data diversa dall'assegnazione della posizione (337694)

Con questa modifica, la data di inizio della compensazione viene impostata automaticamente sulla data di inizio dell'assegnazione della posizione.

### <a name="not-able-to-end-compensation-along-with-its-position-assignment-328993"></a>Impossibile terminare la compensazione insieme alla sua posizione (328993)

Con questa modifica, è possibile terminare la compensazione quando si termina l'assegnazione della posizione utilizzando **Assegnazione di fine** nella pagina **Assegnazioni di posizione del lavoratore** con le azioni del personale attivate.

### <a name="bank-account-validation-requires-routing-and-account-numbers-in-all-locations-340403"></a>La convalida del conto bancario richiede le credenziali e il numero di conto in tutte le ubicazioni (340403)

Con le modifiche di questa settimana, è stata aggiunta una nuova opzione di configurazione per disabilitare **Numero di identificazione bancaria** e **Numero di conto** convalida richiesta. 

### <a name="attachments-are-not-enabled-in-mss-performance-journals-for-performance-feedback-341794"></a>Gli allegati non sono abilitati nei giornali delle prestazioni MSS per il feedback sulle prestazioni (341794)

Con il rilascio di questa settimana, gli allegati sono abilitati per gli elementi di feedback nella pagina del giornale delle prestazioni.

### <a name="leave-request-details-dont-sync-from-common-data-service-to-talent-369608"></a>I dettagli della richiesta di congedo non vengono sincronizzati da Common Data Service a Talent (369608)

Con queste modifiche, i dettagli della richiesta di congedo che vengono aggiornati in Common Data Service vengono nuovamente sincronizzati in Talent.

### <a name="job-description-doesnt-display-for-the-job-in-the-skill-gap-analysis-page-369398"></a>La descrizione del lavoro non viene visualizzata per il lavoro nella pagina Analisi lacuna competenze (369398)

Nella versione di questa settimana, la descrizione verrà visualizzata quando si seleziona il lavoro nella pagina **Analisi lacuna competenze**.

## <a name="coming-soon"></a>Presto disponibili

### <a name="print-performance-reviews"></a>Stampare le valutazioni delle prestazioni

Dipendenti, responsabili e professionisti delle risorse umane potranno stampare la valutazione delle prestazioni di un dipendente.
