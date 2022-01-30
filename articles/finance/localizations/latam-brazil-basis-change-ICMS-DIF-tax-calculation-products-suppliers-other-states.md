---
title: Modifica di base nei calcoli delle imposte ICMS-DIF per i prodotti di fornitori in altri stati
description: Questo argomento descrive la configurazione per i calcoli del tipo di imposta ICMS-DIF quando un documento fiscale viene ricevuto nello stato brasiliano di Rio Grande do Sul (RS) o São Paulo (SP).
author: Kai-Cloud
ms.date: 1/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-1-17
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 16f78b85567e6d08c588e621119513ff070bf618
ms.sourcegitcommit: 68655c5673aef9892063e5913ffee6bfc3817387
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2022
ms.locfileid: "8016173"
---
# <a name="basis-change-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>Modifica di base nei calcoli delle imposte ICMS-DIF per i prodotti di fornitori in altri stati

Questo argomento descrive la configurazione per i calcoli del tipo di imposta **ICMS-DIF** quando un documento fiscale viene ricevuto nello stato brasiliano di Rio Grande do Sul (RS) o São Paulo (SP).

Secondo la definizione della legge statale, l'Imposto sobre Circulação de Mercadorias e Serviços (ICMS) che viene raccolta deve seguire questa regola:

*ICMS da raccogliere* = ([(*Importo operazione* – *ICMS dalla fonte*) ÷ (1 – *ICMS % interna*)] × *ICMS % interna*) – *Importo ICMS dalla fonte*

## <a name="example"></a>Esempio

Una società brasiliana nello stato RS riceve un documento fiscale per un acquisto da un venditore nello stato SP. L'azienda deve raccogliere la differenza percentuale di ICMS tra lo stato RS (18%) e lo stato SP (12%). Tuttavia, la base deve essere calcolata secondo la regola precedente.

- **Importo operazione:** 1.000,00 real brasiliani (R$ 1.000,00)
- **ICMS interstatale:** R$ 120,00
- **Percentuale ICMS nello stato RS:** 18%
- **ICMS da raccogliere nello stato RS:** (\[(1.000 – 120) ÷ (1 – 0,18)\] × 0,18) – 120 = R$ 73,17 

## <a name="resolution"></a>Risoluzione

Per calcolare l'ICMS differenziale (ICMS-DIF) secondo le regole dello stato RS, è necessario impostare i codici IVA e una fascia IVA nel modo seguente:

1. Crea un codice IVA per ricevere il 12% ICMS (per l'altro stato). Questo codice viene utilizzato per registrare l'importo del credito d'imposta dal fornitore.
2. Crea un codice IVA per raccogliere l'ICMS-DIF. Questo codice IVA deve avere un importo percentuale del 18% (per il tuo stato) per definire la differenza tra il 18 percento e il 12 percento. Imposta il tipo di imposta su **ICMS-DIF**. Questo codice IVA deve essere definito nel modo seguente nei parametri di calcolo:

    - Nel campo **Origine** seleziona **Percentuale dell'importo lordo**.
    - Nel campo **Imponibile marginale**, seleziona **Importo netto per riga** o **Importo netto del saldo fattura**.
    - Definisci il codice imposta in modo che abbia un valore fiscale di **3**. In questo modo l'operazione di rettifica verrà creata automaticamente al momento dell'abilitazione del modulo **Libri fiscali**.
    - Nella configurazione della fascia IVA, seleziona l'opzione **Imposta di utilizzo** per il codice IVA **ICMS-DIF**.
