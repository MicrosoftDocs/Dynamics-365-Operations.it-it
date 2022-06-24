---
title: Ritenuta d'acconto globale
description: Questo articolo fornisce informazioni sulla funzionalità della ritenuta d'acconto globale e su come configurarla. La funzionalità della ritenuta d'acconto globale è stata migliorata per le transazioni di fornitori e clienti, in modo che la ritenuta d'acconto venga calcolata a livello di articolo.
author: kailiang
ms.date: 01/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: kfend
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 49d5048b9df30e94d959cf9f22b8ae837b74abdd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846830"
---
# <a name="global-withholding-tax"></a>Ritenuta d'acconto globale

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sulla funzionalità della ritenuta d'acconto globale e spiega come configurarla. La nuova funzionalità è disponibile nella versione 10.0.17 e successive.

La funzionalità della ritenuta d'acconto globale è stata migliorata per le transazioni di fornitori e clienti, in modo che la ritenuta d'acconto venga calcolata a livello di articolo. Il saldo nel conto della ritenuta d'acconto derivante dalle transazioni di acquisto può essere regolato eseguendo il processo di pagamento della ritenuta d'acconto sul conto liquidazione della ritenuta d'acconto.

> [!NOTE]
> La ritenuta d'acconto globale non supporta la funzione **Gestisci spese** nelle pagine dell'ordine di acquisto, della fattura fornitore e dell'ordine fornitore.

## <a name="turn-on-global-withholding-tax"></a>Attivare la ritenuta d'acconto globale

1. Nell'area di lavoro **Gestione funzionalità**, seleziona **Ritenuta d'acconto globale** nell'elenco, quindi seleziona **Abilita ora**.
2. Vai a **Imposta \> Impostazione \> Parametri \> Parametri di contabilità generale** e quindi nella scheda **Ritenuta d'acconto** imposta l'opzione **Attiva ritenuta d'acconto globale** su **Sì**.
3. Selezionare **Salva**.
4. Aggiorna la pagina nel tuo browser web.

> [!NOTE]
> La funzionalità ritenuta d'acconto globale non può essere attivata per paesi/aree geografiche in cui esistono già soluzioni di ritenuta d'acconto localizzate. Queste aree includono ma non sono limitate a India, Brasile, Tailandia, Arabia Saudita, Irlanda, Gran Bretagna e Stati Uniti.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
