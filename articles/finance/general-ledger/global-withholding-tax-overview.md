---
title: Ritenuta d'acconto globale
description: Questo argomento fornisce informazioni sulla funzionalità della ritenuta d'acconto globale e su come configurarla. La funzionalità della ritenuta d'acconto globale è stata migliorata per le transazioni di fornitori e clienti, in modo che la ritenuta d'acconto venga calcolata a livello di articolo.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 9a73d34fb4fbf007cbb5a996cfa6e9719532869c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826668"
---
# <a name="global-withholding-tax"></a>Ritenuta d'acconto globale

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni sulla funzionalità della ritenuta d'acconto globale e spiega come configurarla. La nuova funzionalità è disponibile nella versione 10.0.17 e successive.

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