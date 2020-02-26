---
title: Stato e ciclo di vita documento
description: In questo argomento vengono descritti i diversi stati documento di elementi pagina in Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b4f1c462f734b2d58843308f0f877fe18a4d9af7
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002983"
---
# <a name="document-states-and-lifecycle"></a>Stato e ciclo di vita documento


[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i diversi stati documento di elementi pagina in Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Descrizioni di stati documento

L'argomento [Elementi pagina](page-elements-overview.md) elenca vari tipi di documenti nel sistema di gestione dei contenuti (CMS). Questi tipi di documenti possono avere vari stati nello strumento di creazione. Gli stati documento impediscono conflitti di dati e applicano il controllo delle versioni. Determinano chi può modificare i documenti, quando i documenti possono essere modificati e quando le modifiche possono essere visualizzate da altre persone.

Nella tabella seguente vengono illustrati gli stati documento possibili degli elementi pagina in Commerce.

| Stato documento | Descrizione |
|---|---|
| Estratte | Quando un articolo CMS viene estratto, non può essere modificato da altri utenti di sistema autenticati. Eventuali modifiche apportate all'articolo dall'utente sono visibili solo all'utente. |
| Archiviate | Quando un articolo CMS viene archiviato, tutte le modifiche sono visibili agli altri utenti di sistema autenticati, che possono quindi estrarre l'articolo e modificarlo. Ogni archiviazione crea un record delle versioni del documento nello storico dell'articolo. |
| Pubblicata | Quando un articolo CMS viene pubblicato, viene inviato al sito live e diventa individuabile su Internet da utenti esterni non autenticati. Gli articoli possono essere pubblicati solo se sono stati archiviati. |
| Salvato | Le modifiche apportate a un articolo CMS estratto possono essere salvate in CMS prima che l'articolo venga archiviato o pubblicato. Queste modifiche salvate non sono visibili ad altri utenti di sistema autenticati fino a che l'articolo non viene archiviato. Non sono visibili agli utenti esterni fino a che l'articolo non viene pubblicato. |
| Estrazione annullata | Quando l'estrazione di un articolo CMS viene annullata, tutte le modifiche salvate vengono eliminate e viene ripristinata la versione archiviata più recente dell'articolo. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Modalità di aggiungere contenuti](add-manage-content.md)

[Glossario del modello di pagina](page-elements-overview.md)

[Utilizzare i gruppi di pubblicazione](publish-groups.md)

[Utilizzare i moduli](work-with-modules.md)

[Utilizzare i frammenti](work-with-fragments.md)

[Panoramica modelli e layout](templates-layouts-overview.md)

[Personalizzare la navigazione del sito](customize-site-navigation.md)
