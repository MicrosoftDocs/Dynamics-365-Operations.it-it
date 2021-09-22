---
title: Impossibile rilasciare l'ordine cliente con operazioni di magazzino in uscita
description: Esistono diversi motivi per cui potresti ricevere un messaggio di errore che indica che un ordine cliente non può essere rilasciato. Questa pagina spiega perché e come mitigare il problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fca5ee1bc97545ea4de56d940fdedd320a6cfe84
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476783"
---
# <a name="sales-order-could-not-be-released-with-outbound-warehouse-operations"></a>Impossibile rilasciare l'ordine cliente con operazioni di magazzino in uscita

## <a name="symptoms"></a>Sintomi

Quando si utilizzano operazioni di magazzino in uscita, è possibile che venga visualizzato il seguente messaggio di errore:

> Impossibile rilasciare l'ordine cliente.

## <a name="cause"></a>Causa

Questo problema può verificarsi per diversi motivi. Ad esempio, l'ordine è in attesa della gestione del credito e non è possibile creare spedizioni finché non viene immesso un indirizzo postale valido per tutte le righe di vendita associate a un ordine. In alternativa, esiste una sospensione dell'ordine che deve essere risolta prima che l'ordine possa essere rilasciato al magazzino. Questa sospensione potrebbe essere specifica dell'ordine o potrebbe essere sull'account del cliente.

## <a name="resolution"></a>Risoluzione

Aggiungere o aggiornare l'indirizzo nell'ordine cliente e nelle righe ordine, quindi rilasciare l'ordine al magazzino. Gli ordini possono essere rilasciati al magazzino solo se hanno un indirizzo di consegna valido (in base all'impostazione del formato dell'indirizzo nel modulo **Amministrazione organizzazione**).

Esaminare la sospensione dell'ordine e risolvere i problemi. Quindi rimuovere la sospensione dall'ordine o dal cliente e rilasciare l'ordine al magazzino.
