---
title: Problemi con la riconciliazione dei dati di un report Z
description: Questo articolo descrive i problemi che gli utenti potrebbero riscontrare con la riconciliazione dei dati di un report Z in Commerce headquarters. Descrive anche le possibili cause alla radice e le soluzioni che possono aiutare a prevenire eventi futuri.
author: Shajain
ms.date: 12/06/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: 9803134c4c77233e565525e96fd82af293d4c829
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832138"
---
# <a name="issues-with-the-data-reconciliation-of-a-z-report"></a>Problemi con la riconciliazione dei dati di un report Z

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce indicazioni che possono aiutarti se riscontri problemi con la riconciliazione dei dati di un report Z in Microsoft Dynamics 365 Commerce headquarters. Descrive i problemi che gli utenti potrebbero riscontrare con la riconciliazione dei dati, le possibili cause principali e le soluzioni che possono aiutare a prevenire eventi futuri.

## <a name="description"></a>Description

- C'è una discrepanza tra gli importi mostrati nel report Z e i totali mostrati nell'estratto conto calcolato.
- La transazione in headquarters ha un numero errato di voci o c'è una mancata corrispondenza tra il totale della riga e il totale della transazione.
- Il numero di transazioni visualizzate in un turno in headquarters è inferiore al numero di transazioni nel report Z.
- La registrazione dell'estratto conto non è riuscita per uno dei motivi precedenti.

### <a name="root-cause"></a>Causa principale

La causa principale più comune dei sintomi descritti in precedenza è la generazione di ID transazione duplicati nel database del canale. Gli ID transazione duplicati possono essere generati per i seguenti motivi:

- L'archiviazione del database locale di Modern Point of Sale (MPOS) è danneggiata.
- MPOS ha alcune transazioni in modalità offline e viene riattivato utilizzando un account che non ha accesso al database offline.
- Si è verificato un problema con la personalizzazione correlato alla generazione degli ID transazione.

## <a name="resolution"></a>Risoluzione

Di solito, Commerce si basa su una sequenza numerica per generare gli ID transazione sequenziali. Se il sistema non è in grado di determinare che è stata utilizzata una sequenza numerica per un qualsiasi motivo, viene generato un ID transazione duplicato. 

Per risolvere il problema dell'ID transazione duplicato, crea un ticket di supporto per verificare se i dati della transazione possono essere corretti. In alcuni casi, ad esempio quando non si verificano perdite di dati in headquarters, non è possibile o necessaria alcuna correzione dei dati.

Per evitare questo problema in futuro, devi abilitare la funzione **Abilita nuovo ID transazione per evitare ID transazione duplicati** in headquarters. Questa funzione è stata introdotta nella versione 10.0.19 di Commerce. Aiuta a prevenire la creazione di ID transazione sequenziali assicurando che venga creato un ID transazione univoco per ogni transazione. Per ulteriori informazioni su questa funzione, vedi [Impedire gli ID transazione duplicati](../channel-setup-retail.md#ensure-unique-transaction-ids).
