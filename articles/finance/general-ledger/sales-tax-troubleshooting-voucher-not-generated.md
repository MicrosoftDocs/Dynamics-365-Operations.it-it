---
title: Il giustificativo non viene generato
description: Questo articolo fornisce informazioni sulla risoluzione dei problemi che possono essere utili quando un giustificativo deve essere generato ma non lo è.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1200fe50bf9be4c6d1ca809ad9a86da2ff3e0ced
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909013"
---
# <a name="voucher-isnt-generated"></a>Il giustificativo non viene generato

[!include [banner](../includes/banner.md)]

Se un giustificativo dovrebbe essere generato ma la pagina **Transazioni giustificativo** non ne mostra alcuno, segui i passaggi nelle sezioni seguenti come richiesto per risolvere questo problema.

[![Pagina Transazioni giustificativo senza giustificativi.](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)

## <a name="check-the-tax-applicability"></a>Verificare l'applicabilità fiscale

1. Vai a **Imposta** \> **Attività periodiche** \> **Inserimenti nel giornale di registrazione secondario non ancora trasferiti**.
2. Se è presente un record di giornale di registrazione, selezionalo e quindi seleziona **Trasferisci ora**.

    [![Pulsante Trasferisci ora nella pagina Inserimenti nel giornale di registrazione secondario non ancora trasferiti.](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)

3. Apri di nuovo la pagina **Transazioni giustificativo** per vedere se il giustificativo è stato generato.

## <a name="determine-whether-customization-exists"></a>Determinare se esiste la personalizzazione

Se hai completato i passaggi nella sezione precedenti ma non hai riscontrato alcun problema, determina se esiste la personalizzazione. Se non esiste alcuna personalizzazione, creare una richiesta di assistenza Microsoft per ulteriore supporto.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
