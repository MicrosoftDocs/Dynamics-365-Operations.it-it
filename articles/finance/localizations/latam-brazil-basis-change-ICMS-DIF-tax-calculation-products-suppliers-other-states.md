---
title: Modifica di base nei calcoli delle imposte ICMS-DIF per i prodotti di fornitori in altri stati
description: Questo articolo descrive la configurazione per i calcoli del tipo di imposta ICMS-DIF quando un documento fiscale viene ricevuto nello stato brasiliano di Rio Grande do Sul (RS) o São Paulo (SP).
author: Kai-Cloud
ms.date: 06/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-1-17
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 1bd9982a3804778a27203b4311682ee8bc3c4841
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218651"
---
# <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>Modifica di base (doppia base) nei calcoli delle imposte ICMS-DIF per prodotti di fornitori in altri stati

Questo articolo descrive la configurazione per i calcoli del tipo di imposta **ICMS-DIF** quando un documento fiscale viene ricevuto nello stato brasiliano di Rio Grande do Sul (RS) o São Paulo (SP).

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
    - Nel campo **Base marginale**, seleziona **Importo netto per riga**.
    - Definisci il codice imposta in modo che abbia un valore fiscale di **3**. In questo modo l'operazione di rettifica verrà creata automaticamente al momento dell'abilitazione del modulo **Libri fiscali**.
    - Nella configurazione della fascia IVA, seleziona l'opzione **Imposta di utilizzo** per il codice IVA **ICMS-DIF**.

### <a name="use-the-delta-tax-rate-in-the-configuration-of-dual-base-icms-dif-sales-tax-codes"></a>Utilizzare l'aliquota delta nella configurazione dei codici IVA ICMS-DIF per doppia base

Quando vengono utilizzate le impostazioni descritte in precedenza, il codice IVA **ICMS-DIF** sarà calcolato nella regola di doppia base. Tuttavia, l'aliquota nominale passa al 18%, che differisce dall'aliquota del 6% nella regola di base semplice. Questa differenza causa problemi di incoerenza nel documento fiscale e nella dichiarazione IVA. A partire da Microsoft Dynamics 365 Finance versione 10.0.29, puoi abilitare la funzionalità **(Brasile) Configurare l'aliquota delta nel codice imposta ICMS-DIF per il caso doppia base** in **Gestione funzionalità** per risolvere l'incoerenza.

- Oltre a completare i passaggi nella sezione precedente, seleziona il codice IVA **ICMS 12** nel campo **IVA sull'IVA**.
- Imposta l'aliquota del codice IVA **ICMS-DIF** su 18%. Il campo **Percentuale/Importo** mostrerà l'aliquota nominale del 6%.

> [!NOTE]
> I codici IVA **ICMS-DIF** e **ICMS 12** devono essere assegnati nella stessa fascia IVA.

## <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-to-non-taxpayer-consumers-difal-in-other-states"></a>Modifica di base (doppia base) nei calcoli dell'imposta ICMS-DIF per prodotti destinati a consumatori non contribuenti (DIFAL) in altri stati

Abilita la funzionalità **(Brasile) Calcolo doppia base per ICMS-DITC nelle transazioni di vendita** in **Gestione funzionalità** per supportare il cambio di base ICMS-DIF per le attività commerciali con consumatori non contribuenti di un altro stato. Il codice IVA ICMS-DIF di esempio diventa effettivo nelle transazioni di ordini cliente e fatture a testo libero.

Abilita la funzionalità **(Brasile) Calcolo doppia base per ICMS-DIFAL per casi IPI** in **Gestione funzionalità** per supportare scenari in cui le attività commerciali con consumatori non contribuenti di un altro stato sono soggette anche a Imposto sobre Produtos Industrializados (IPI). L'importo fiscale del codice IVA IPI verrà riconosciuto e applicato nell'imponibile ICMS-DIFAL.

- Nell'intestazione dell'ordine cliente o della fattura a testo libero, nella Scheda dettaglio **Informazioni fiscali**, l'opzione **Utente finale** deve essere impostata su **Sì**.
- Nell'intestazione dell'ordine fornitore o della fattura fornitore, nella Scheda dettaglio **Informazioni fiscali**, l'opzione **Uso e consumo** deve essere impostata su **Sì**.
