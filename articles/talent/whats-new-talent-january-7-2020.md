---
title: Novità o modifiche in Dynamics 365 Talent (7 gennaio 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
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
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461645"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a>Novità o modifiche in Dynamics 365 Talent (7 gennaio 2020)

Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2697. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a>Impossibile eliminare lavoratori che non hanno record di impiego - (386157)

Questa modifica aggiunge un'opzione di eliminazione nel modulo **Lavoratori con impiego**. I lavoratori sono visualizzati in questo modulo quando non esistono impieghi futuri, attivi o storici per il lavoratore. In questa versione, la funzionalità di eliminazione è abilitata solo per gli amministratori di sistema. Tuttavia, nella versione della settimana successiva, la sicurezza verrà aggiornata per consentire a tutti gli utenti con il ruolo di assistente delle risorse umane di rimuovere dipendenti senza impiego. È inoltre possibile apportare queste modifiche manualmente procedendo come segue.

1. Selezionare **Configurazione sicurezza**.
2. Nella scheda **Privilegi**, filtrare l'elenco **Privilegi** in base a **Gestisci lavoratori**.
3. Nella colonna **Riferimenti**, selezionare colonna, selezionare **Voci di menu Visualizza**.
4. In **Voci di menu Visualizza**, selezionare **HcmWOrkersWithoutEmployment**.
5. Impostare l'autorizzazione **Elimina** su Concedi.
6. Selezionare la scheda **Oggetti non pubblicati**.
7. Selezionare **Pubblica tutto**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]