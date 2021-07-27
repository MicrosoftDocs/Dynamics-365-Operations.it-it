---
title: Stato e ciclo di vita documento
description: In questo argomento vengono descritti i diversi stati documento di elementi pagina in Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: intro-internal
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ee6f0e9114475418badbbdb1f9468f7f1e668814
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "6338585"
---
# <a name="document-states-and-lifecycle"></a>Stato e ciclo di vita documento

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i diversi stati documento di elementi pagina in Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Descrizioni di stati documento

L'argomento [Elementi pagina](page-elements-overview.md) elenca vari tipi di documenti nel sistema di gestione dei contenuti (CMS). Questi tipi di documenti possono avere vari stati nello strumento di creazione. Gli stati documento impediscono conflitti di dati e applicano il controllo delle versioni. Determinano chi può modificare i documenti, quando i documenti possono essere modificati e quando le modifiche possono essere visualizzate da altre persone.

Nella tabella seguente vengono illustrati gli stati documento possibili degli elementi pagina in Commerce.

| Stato documento      | Azione di Creazione di siti Web        | Descrizione                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| Check out         | Selezionare **Modifica**.           | Il documento applicabile è stato estratto. Mentre un documento si trova in questo stato, non può essere modificato da altri utenti di sistema autenticati e qualsiasi modifica apportata al documento è visibile solo all'utente. |
| Salvato               | Selezionare **Salva**.           | Le modifiche apportate a un documento estratto vengono salvate nel database, ma il documento non è ancora archiviato o pubblicato. Le modifiche salvate non sono visibili ad altri utenti di sistema autenticati fino a che l'autore seleziona **Fine modifica**. Non sono visibili agli utenti esterni fino a che l'articolo non viene pubblicato. |
| Estrazione annullata | Selezionare **Ignora modifiche**.  | Tutte le modifiche al documento estratto vengono eliminate e l'elemento torna all'ultima versione archiviata. |
| Elemento archiviato          | Selezionare **Fine modifica**. | Il documento modificato è archiviato. Tutte le modifiche sono visibili agli altri utenti del sistema autenticati e tali utenti possono quindi modificare il documento. Ogni archiviazione crea un record delle versioni del documento nello storico dell'articolo. |
| Pubblicata           | Selezionare **Pubblica**        | Il documento viene pubblicato e le modifiche vengono inviate al sito live e diventano rilevabili da utenti esterni. Gli articoli possono essere pubblicati solo se sono stati prima archiviati selezionando **Fine modifica**. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Modalità di aggiungere contenuti](add-manage-content.md)

[Glossario del modello di pagina](page-elements-overview.md)

[Utilizzare i gruppi di pubblicazione](publish-groups.md)

[Abilitare e utilizzare la condivisione multicanale](cross-channel-sharing.md)

[Utilizzare i moduli](work-with-modules.md)

[Utilizzare i frammenti](work-with-fragments.md)

[Panoramica modelli e layout](templates-layouts-overview.md)

[Personalizzare la navigazione del sito](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]