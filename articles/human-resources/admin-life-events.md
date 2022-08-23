---
title: Impostare diritti di amministratore per eventi di vita
description: Questo articolo descrive come configurare diritti di amministratore per eventi di vita in Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9deed240977394667cee8b107397267b182d960b
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229900"
---
# <a name="set-administrator-rights-for-life-events"></a>Impostare diritti di amministratore per eventi di vita

[!include [banner](../includes/preview-banner.md)]

Gli amministratori possono aggiornare le opzioni degli eventi di vita, a seconda delle impostazioni di configurazione. Nella pagina **Parametri risorse umane**, puoi configurare i parametri che consentono agli amministratori di apportare modifiche alle selezioni del piano. Puoi anche impedire completamente agli amministratori di apportare modifiche.

Nella pagina **Parametri risorse umane**, puoi impostare le restrizioni di modifica del piano per i piani confermati e le opzioni di eventi di vita.

Se l'opzione **Piani confermati** è selezionata, le modifiche possono essere apportate solo se è attivo un periodo di iscrizione (esempi di periodi di iscrizione includono periodi di iscrizione aperta, periodi di iscrizione di nuove assunzioni e periodi di iscrizione a eventi di vita). Se questa opzione non è selezionata, è possibile apportare modifiche in qualsiasi momento.

Se l'opzione **Opzioni di eventi di vita** è selezionata, le modifiche al piano durante un evento di vita sono limitate dalle opzioni dell'evento di vita definite nel tipo di piano. Se questa opzione non è selezionata, le selezioni del piano possono essere modificate durante un evento di vita.

## <a name="set-plan-change-restrictions"></a>Impostare restrizioni per la modifica del piano

Nella pagina **Parametri Risorse umane**, nella scheda **Gestione benefit**, sono disponibili i campi seguenti.

| Campo | Description |
|-------|-------------|
| Piani confermati | Seleziona questa opzione se le modifiche a un piano sono consentite solo se è attivo un periodo di iscrizione. Se questa opzione non è selezionata, è possibile apportare modifiche in qualsiasi momento. |
| Opzioni evento reale | Seleziona questa opzione se le modifiche al piano durante un evento di vita sono limitate dalle opzioni degli eventi di vita definite nel tipo di piano. Se questa opzione non è selezionata, le selezioni del piano possono essere modificate durante un evento di vita. |
