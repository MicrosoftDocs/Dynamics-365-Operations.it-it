---
title: Suggerimenti intelligenti in Attract
description: In questo articolo viene descritto come l'apprendimento automatico può essere utilizzato per fornire suggerimenti per mansioni e candidati a mansioni in Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 05/16/2019
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
ms.openlocfilehash: fa06821c98e42dcd8590a764db9beb4a5c33fca2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461592"
---
# <a name="intelligent-recommendations-in-attract"></a>Suggerimenti intelligenti in Attract

[!include [banner](includes/banner.md)]

L'apprendimento automatico può aiutare i selezionatori e i responsabili assunzioni a identificare i candidati migliori per una posizione. Può anche consentire ai prospect di individuare la posizione più appropriata per il proprio profilo e interessi. Man mano che si usano queste funzionalità e viene fornito feedback, i suggerimenti migliorano.

> [!NOTE] 
> - Le funzionalità di suggerimenti intelligenti sono disponibili solo con il [componente aggiuntivo per l'assunzione a livello globale](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - La funzionalità indicata in questo argomento è disponibile come parte di un rilascio di verifica di anteprima. Il contenuto e la funzionalità sono soggetti a modifiche. Per utilizzare questa funzionalità, chiedere a un amministratore di abilitarla utilizzando l'**Interfaccia di amministrazione** in Attract. Impostare **Suggerimento candidato**, **Suggerimento posizione** e **Suggerimento prospect** su **Attivato**. Per ulteriori informazioni, vedere [Accesso alle funzionalità di anteprima in Microsoft Dynamics 365 Talent](./access-preview-feature.md). 


## <a name="candidate-recommendations"></a>Suggerimenti candidato

Poiché gli annunci di mansioni potrebbero attirare centinaia di candidati, può essere difficile per selezionatori e responsabili assunzioni individuare i candidati le cui competenze e esperienze corrispondano meglio alla posizione. Analizzando la correlazione tra la descrizione della mansione e i requisiti e i dati del curriculum e i profili dei candidati, l'apprendimento automatico può essere utilizzato per generare i suggerimenti candidato. I suggerimenti candidato possono aiutare selezionatori e responsabili assunzioni a identificare i migliori talenti per passarli più rapidamente alla fase di colloquio. Per ogni mansione, se sono disponibili più di dieci candidati o prospect con curriculum o profili completi, i candidati o prospect che soddisfano maggiormente i requisiti della mansione vengono visualizzati nella sezione **Candidati da considerare** della pagina **mansione**.

Per qualsiasi candidato suggerito, è possibile selezionare **Visualizza candidato** nella scheda del candidato per esaminare il profilo del candidato e intraprendere le azioni sulla relativa domanda di lavoro. È possibile utilizzare il pulsante con i puntini di sospensione (**...**) per aprire il profilo del candidato in una nuova scheda. È inoltre possibile utilizzare il pulsante con i puntini di sospensione per fornire un riscontro sul suggerimento. In questo modo, si contribuisce all'ottimizzazione del motore di suggerimento e si migliorano i suggerimenti futuri. Tutte le raccomandazioni che non piacciono verranno rimosse dalla sezione **Candidati da considerare** quando si aggiorna la pagina **Mansione**. È possibile utilizzare la scheda di riscontro per indicare il motivo per cui non si è trovato utile il suggerimento.

## <a name="job-recommendations"></a>Suggerimenti mansione 

Quando un dipendente potenziale usa il sito di avanzamento professionale per fare domanda per una mansione, Attract consiglia altre posizioni aperte nell'organizzazione. Questi suggerimenti sono basati sulle passate domande di lavoro e sul curriculum o sul profilo del prospect. Di conseguenza, i suggerimenti mansione aiutano i prospect a identificare rapidamente le mansioni pià adatte a loro. I suggerimenti mansione vengono forniti ai prospect se più di dieci mansioni vengono pubblicate nel sito di avanzamento professionale. I prospect possono aprire i dettagli di un annuncio di mansione nella scheda di suggerimento. Possono inoltre fornire un riscontro su un suggerimento per aiutare a migliorare i suggerimenti futuri.

## <a name="prospect-recommendations"></a>Suggerimenti prospect 

Quando una nuova posizione diventa disponibile, esaminare tutti i candidati passati e l'intera rete di competenze può richiedere tempo. Per utilizzare Attract a questo scopo, è possibile utilizzare algoritmi di machine learning intelligenti. Ciò significa che Attract esamina tutti i candidati e suggerisce quelli che sono una buona corrispondenza non appena si crea la mansione. Per visualizzare questi suggerimenti, abilitare la fase **Prospect** per la mansione. Attract può richiedere fino a un minuto per esaminare l'intero database di candidati per proporre suggerimenti.

I suggerimenti sono visualizzati come schede nella scheda **Prospect** di qualsiasi mansione per la quale è stata abilitata la fase **Prospect**. Queste schede elencano le competenze nel profilo del prospect, nonché le informazioni sul titolo di studio. Se si trova un suggerimento appropriato, è possibile aggiungere il candidato come prospect per quella mansione.

> [!NOTE]
> Se di recente si è iniziato a utilizzare Attract, sarà necessario attendere di avere 10 o più candidati che hanno profili o curriculum completi prima di poter utilizzare questa funzionalità.

Per evitare potenziali problemi nei suggerimenti, Attract esamina solo i profili per competenze, qualifiche e altre parole chiave che corrispondono alla descrizione della mansione. Inoltre, Attract rimuove informazioni di identificazione personale dai profili dei candidati prima della valutazione.
