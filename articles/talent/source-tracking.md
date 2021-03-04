---
title: Tenere traccia delle origini dei candidati in Attract
description: In questo argomento vengono fornite informazioni sulla tracciabilità delle origini delle domande di lavoro e dei profili dei candidati.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 8860f508eebc377042c4e101eeb08a14a737ba0c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461625"
---
# <a name="track-candidate-sources-in-attract"></a>Tenere traccia delle origini dei candidati in Attract

[!include [banner](includes/banner.md)]

> [!NOTE] 
> La funzionalità indicata in questo argomento è disponibile come parte di un rilascio di verifica di anteprima. Il contenuto e la funzionalità sono soggetti a modifiche. Per utilizzare questa funzionalità, chiedere a un amministratore di abilitarla utilizzando **Impostazioni di amministrazione** in Attract. Una versione futura fornirà report di tracciabilità delle origini. Per ulteriori informazioni, vedere [Accesso alle funzionalità di anteprima in Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

Quando i candidati si candidano per una mansione, Attract tiene automaticamente traccia dell'origine delle loro domande di lavoro, fornendo informazioni preziose per migliorare le operazioni di selezione. I selezionatori e i responsabili delle assunzioni possono inoltre selezionare l'origine di una domanda di lavoro quando aggiungono manualmente un candidato a una mansione o a un pool di talenti.

È possibile visualizzare l'origine della domanda di lavoro nei dettagli dell'attività della domanda di lavoro nella scheda **Attività** nonché nello storico delle domande di lavoro disponibile in **Profilo** nei pool di talenti. È possibile trovare l'origine del profilo di un candidato nei dettagli del candidato nella scheda **Profilo** di Domande di lavoro e Pool di talenti.

> [!NOTE] 
> I modelli di processo sono disponibili nel [componente aggiuntivo per l'assunzione a livello globale](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).

## <a name="pre-configured-sources"></a>Origini preconfigurate

L'elenco di origini predefinite contiene origini di domande di lavoro comuni. Alcuni tipi di origini, ad esempio **Bacheca mansioni** e **Social Network**, includono ulteriori informazioni sulle origini. Ad esempio, **Social Network** include Facebook e Twitter. Il tipo di origine **Segnalazione** consente di specificare un dipendente interno come garante. L'elenco di origini predefinite include le seguenti origini preconfigurate:

-   Sito di avanzamento professionale di Attract

-   Agenzia

-   Borsa del lavoro

-   Marketing aziendale

-   Conferenze e fiere campionarie

-   Associazione di professionisti

-   Bacheca delle offerte di lavoro

    -   Indeed

    -   Seek

    -   CareerBuilder

    -   Google Jobs

    -   Xing

    -   Glassdoor

    -   Monster Jobs

-   Riviste e pubblicazioni

-   Social Network

    -   Facebook

    -   Twitter

-   Selezione presso università

-   LinkedIn

-   Annunci

-   Segnalazione

-   Aggiunta dal selezionatore

-   Altro

## <a name="customize-the-source-list"></a>Personalizzare l'elenco di origini 

È possibile estendere l'elenco di origini per includere ulteriori origini di domande di lavoro. Per personalizzare questo elenco, seguire le istruzioni in [Estensione di set di opzioni in Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract). Modificare l'entità **TalentSource** per includere ulteriori origini. 

Per evitare un impatto negativo sull'interfaccia utente, non modificare o eliminare i valori di enumerazione **TalentCategory** (non i nomi) per quanto segue:

- **Segnalazione**
- **LinkedIn**
- **Altro**

È invece possibile estendere l'enumerazione **TalentSource** per aggiungere altri tipi di origini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]