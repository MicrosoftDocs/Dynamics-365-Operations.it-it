---
title: Lavoratori responsabili dell'approvazione delle non conformità
description: Questo argomento descrive come configurare i lavoratori responsabili dell'approvazione delle non conformità.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5fd1c7c86ac8627bd332bc578e98b4d7f091cdc8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575898"
---
# <a name="workers-responsible-for-approving-nonconformances"></a>Lavoratori responsabili dell'approvazione delle non conformità

[!include [banner](../includes/banner.md)]

Questo argomento descrive come configurare i lavoratori responsabili dell'approvazione delle non conformità.

Le non conformità devono essere approvate prima che gli utenti possano iniziare a inserire dettagli come correzioni o operazioni. Prima che gli utenti possano approvare o respingere le non conformità, il loro ID utente (record utente) deve essere collegato a un record lavoratore. Facoltativamente, puoi configurare i lavoratori responsabili della qualità e quindi consentire a un lavoratore di approvare il lavoro per conto di un altro lavoratore.

## <a name="enable-a-user-for-nonconformance-processing"></a>Abilitare un utente per l'elaborazione di non conformità

Prima che un utente possa approvare o respingere le non conformità, devi collegare il suo record utente a un record lavoratore. I campi di approvazione possono quindi essere impostati automaticamente e l'utente corrente può essere compilato automaticamente per il foglio presenze. Prima che l'utente possa utilizzare le note del documento, devi attivare la Gestione documenti nelle sue opzioni utente.

1. Selezionare **Amministrazione sistema \> Utenti \> Utenti**.
1. Trova e apri l'utente che dovrebbe essere in grado di approvare o respingere le non conformità.
1. Imposta il campo **Persona** sul nome del lavoratore correlato al record utente corrente.
1. Nel riquadro azioni selezionare **Opzioni utente**.
1. Nella pagina **Opzioni** per il record utente corrente, nella scheda **Preferenze**, impostare l'opzione **Attiva gestione documenti** su *Sì*.
1. Chiudere le pagine.

## <a name="define-workers-that-are-responsible-for-quality"></a>Definire i lavoratori responsabili della qualità

1. Andare a **Gestione inventario \> Impostazione \> Controllo qualità \> Lavoratori responsabili della qualità**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **Lavoratore** selezionare il lavoratore che inserisce i dati sulla qualità.
4. Nel campo **Lavoratore responsabile** selezionare il lavoratore per conto del quale il lavoratore selezionato inserisce il lavoro. Quando vengono create e aggiornate le non conformità, questo lavoratore verrà inserito per impostazione predefinita nei campi **Lavoratore**.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica gestione qualità](quality-management-processes.md)
- [Abilitare la gestione della qualità e della non conformità](enable-quality-management.md)
- [Spese gestione qualità](quality-charges.md)
- [Aree di quarantena per non conformità](quality-quarantine-zones.md)
- [Tipi di diagnostica per non conformità](quality-diagnostic-types.md)
- [Spese di gestione qualità per non conformità](quality-charges.md)
- [Operazioni per non conformità](quality-operations.md)
- [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
