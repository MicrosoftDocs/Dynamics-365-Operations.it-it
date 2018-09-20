---
title: Gestire la convalida del conto IBAN (International Bank Account Number)
description: Questo argomento spiega come gestire la convalida del conto IBAN (International Bank Account Number).
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e091aab70a98e0f4b96c41c1ee48926947539105
ms.contentlocale: it-it
ms.lasthandoff: 08/31/2018

---

# <a name="manage-international-bank-account-number-iban-account-validation"></a>Gestire la convalida del conto IBAN (International Bank Account Number)

[!include [banner](../includes/banner.md)]

La convalida del conto IBAN (International Bank Account Number) aumenta la convalida che viene effettuata quando si aggiunge un IBAN a un conto bancario.

La struttura dell'IBAN viene archiviata in Microsoft Dynamics 365 for Finance and Operations e viene caricata automaticamente la prima volta che si utilizza l'IBAN nei conti bancari. Il numero di conto bancario fa parte della struttura definita per un numero IBAN. In base a tale struttura, se la posizione e la lunghezza del numero di conto nell'IBAN non corrispondono alla posizione definita nella struttura per ciascun paese o area, vengono visualizzati messaggi di avviso.

## <a name="set-up-iban-structures"></a>Impostare le strutture IBAN

1. Passare a **Gestione cassa e banche \> Impostazioni \> Strutture IBAN**.
2. Si noti che le strutture IBAN per ogni paese o area sono state impostate automaticamente.
3. Se è necessario personalizzare le strutture per un paese o un'area specifica, è possibile modificarle.
4. Le definizioni delle strutture saranno parte di ogni nuova versione. È possibile utilizzare il menu **Reimposta strutture** per caricare le definizioni più recenti dopo ogni aggiornamento.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Convalidare la struttura IBAN in un conto bancario

1. Passare a **Gestione cassa e banche \> Conti bancari \> Conti bancari**.
2. Creare un conto bancario.
3. Nella Scheda dettaglio **Informazioni aggiuntive** immettere un IBAN.

    Se la posizione e la lunghezza del numero di conto nell'IBAN non corrispondono alla posizione definita nella struttura per ciascun paese o area, viene visualizzato un messaggio. Non è possibile procedere se la lunghezza dell'IBAN non corrisponde alla lunghezza nella struttura IBAN.

    La convalida verifica inoltre che il numero di conto bancario corrisponda alla parte dell'IBAN che rappresenta il numero di conto bancario. Se il numero di conto bancario non corrisponde, viene visualizzato un messaggio di avviso. Questo messaggio è solo un avviso. È possibile continuare nonostante il numero di conto bancario non corrisponda.

