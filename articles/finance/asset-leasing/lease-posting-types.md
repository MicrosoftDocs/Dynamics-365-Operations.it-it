---
title: Tipi di registrazione di leasing
description: In questo argomento vengono descritti i tipi di registrazione utilizzati per le transazioni di leasing di cespiti.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1d76c7ea72346c432db04bbe7947dea0c2911ea8
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881134"
---
# <a name="lease-posting-types"></a>Tipi di registrazione di leasing

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritti i tipi di registrazione utilizzati per le transazioni di leasing di cespiti.

## <a name="lease-asset"></a>Cespite di leasing

L'account è associato all'Asset Right of use. Su questo conto viene effettuato un addebito quando un leasing viene inizialmente riconosciuto in base ai nuovi principi contabili di leasing, Accounting Standards Codification Topic 842 (ASC 842) e International Financial Reporting Standard 16 (IFRS 16). Per un leasing modificato, su questo conto potrebbe essere effettuato un addebito o un accredito, a seconda che la modifica aumenti o diminuisca l'obbligazione sul leasing.

**Scritture contabili di esempio:** riconoscimento iniziale<br>
**Dare:** cespite leasing XXX<br>
**Avere:** obbligazione sul leasing XXX

## <a name="lease-liability"></a>Obbligazione sul leasing

Il conto è associato all'obbligazione sul leasing che si verifica quando i pagamenti vengono scontati secondo i nuovi standard IFRS 16 e ASC 842. Su questo conto viene effettuato un accredito un leasing viene inizialmente riconosciuto secondo i nuovi standard. Viene effettuato un addebito per i canoni di leasing e accreditato per gli interessi maturati.

**Scritture contabili di esempio:** riconoscimento iniziale<br>
**Dare:** cespite leasing XXX<br>
**Avere:** obbligazione sul leasing XXX

**Esempi di scritture contabili:** interessi maturati<br>
**Dare:** interesse passivo XXX<br>
**Avere:** obbligazione sul leasing XXX

**Scritture contabili di esempio:** canone di leasing<br>
**Dare:** obbligazione sul leasing XXX<br>
**Avere:** debito fornitore/canone di leasing XXX

## <a name="short-term-lease-liability"></a>Obbligazione sul leasing a breve termine

Il conto è associato all'obbligazione sul leasing a breve termine quando viene registrata la scrittura contabile di riclassificazione dell'obbligazione sul leasing a breve termine. Su questo conto viene effettuato un accredito per la passività a breve termine dal piano di ammortamento l'ultimo giorno del mese. Tuttavia, lo stesso importo viene addebitato il primo giorno del mese successivo.

**Registrazioni contabili di esempio:** riclassificazione dell'obbligazione sul leasing a breve termine<br>
**Dare:** obbligazione sul leasing XXX<br>
**Avere:** obbligazione sul leasing a breve termine XXX<br>
**Dare:** obbligazione sul leasing a breve termine XXX<br>
**Avere:** obbligazione sul leasing XXX

## <a name="depreciation-expense"></a>Spesa di ammortamento

Il conto è associato alla spesa correlata all'ammortamento del'Asset ROU ai sensi di IFRS 16, ASC 842 e ai leasing finanziari secondo lo IAS 17 e l'ASC 840. Su questo conto viene effettuato un addebito quando un asset ROU viene ammortizzato ogni mese.

**Esempi di scritture contabili:** ratei di ammortamento<br>
**Dare:** spesa di ammortamento XXX<br>
**Avere:** Ammortamento accumulato XXX

## <a name="gainloss-on-lease-modification"></a>Profitti/Perdite per la modifica del leasing

Il conto è associato a eventuali guadagni o perdite derivanti da modifiche del leasing. Un guadagno potrebbe verificarsi durante una modifica del leasing se la modifica riduce l'obbligazione sul leasing di un importo che supera il valore contabile dell'asset ROU.

Ad esempio, un leasing ha un valore contabile corrente dell'obbligazione sul leasing di $150.000 e un valore contabile dell'asset ROU di $100.000. Il leasing viene modificato e questa modifica produce un nuovo valore attuale dei canoni di leasing futuri(PVFMLP) di $40.000. Pertanto, l'obbligazione sul leasing verrà addebitata da $110.000 ($ 150.000 - $40.000). Poiché l'asset ROU è pari solo a $100.000, la diminuzione di $110.000 farà diminuire l'asset oltre 0 (zero). Pertanto, la guida contabile afferma che il resto deve essere registrato in un conto di guadagno. In questo caso, l'ultima scrittura contabile sarà un addebito sull'obbligazione sul leasing per $110.000, un accredito sul cespite del leasing di $100.000 e un accredito sul conto guadagni per $10.000.

**Scritture contabili di esempio:** modifica del leasing<br>
**Dare:** obbligazione sul leasing XXX<br>
**Avere:** cespite del leasing XXX<br>
**Avere:** guadagno XXX

## <a name="accumulated-depreciation"></a>Fondo di ammortamento

Il conto è associato al conto contro-asset dell'asset ROU. Viene eseguito un accredito sul conto quando viene registrata una spesa di ammortamento.

**Esempi di scritture contabili:** ratei di ammortamento<br>
**Dare:** spesa di ammortamento XXX<br>
**Avere:** Ammortamento accumulato XXX

## <a name="variable-payment"></a>Pagamento variabile

Il conto è associato a canoni di leasing variabili prodotti da una rivalutazione dell'indice ai sensi dei leasing ASC 842, ASC 840 e IAS 17. Nello scadenziario dei canoni di leasing, i pagamenti variabili sono inclusi nella colonna **Pagamento variabile**. Su questo conto viene effettuato un addebito quando viene creata una fattura su una riga di scadenziario di pagamento che contiene un pagamento variabile.

**Scritture contabili di esempio:** canone di leasing<br>
**Dare:** obbligazione sul leasing XXX<br>
**Dare:** pagamento variabile XXX<br>
**Avere:** debito fornitore/canone di leasing XXX

## <a name="deferred-rent-asset-liability"></a>Cespite passività sui contratti (passività)

Il conto è associato alla passività di cespiti passività sui contratti o passività prodotta da un leasing per passività sui contratti. Su questo conto viene effettuato un addebito quando una fattura viene registrata a fronte di un leasing con trattamento di passività sui contratti, se l'importo del canone del leasing è superiore al costo del leasing a quote costanti del periodo. Viene accreditato se il canone di leasing è inferiore al costo del leasing a quote costanti del periodo.

**Scritture contabili di esempio:** canone di leasing (leasing con trattamento di passività sui contratti)<br>
**Dare:** costo di leasing XXX<br>
**Avere:** passività sui contratti XXX<br>
**Avere:** debito fornitore/canone di leasing XXX

## <a name="lease-expense"></a>Spesa di leasing

Il conto è associato al costo del leasing se il leasing è classificato come leasing per trattamento passività sui contratti. Su questo conto viene effettuato un addebito quando una fattura viene registrata a fronte di un leasing con trattamento di passività sui contratti.

**Scritture contabili di esempio:** canone di leasing (leasing con trattamento di passività sui contratti)<br>
**Dare:** costo di leasing XXX<br>
**Avere:** passività sui contratti XXX<br>
**Avere:** debito fornitore/canone di leasing XXX

## <a name="impairment-expense"></a>Spesa di svalutazione

Il conto viene registrato a fronte di un leasing compromesso. Su questo conto viene effettuato un addebito, mentre sul conto asset ROU viene direttamente effettuato un accredito.

**Scritture contabili di esempio:** canone di leasing<br>
**Dare:** Spesa di riduzione del valore XXX<br>
**Avere:** Asset ROU XXX

## <a name="lease-payment"></a>Canone di leasing

L'account viene registrato a fronte se il parametro **Paga al fornitore** è disattivato. Su questo conto viene effettuato invece un accredito se il parametro pagabile al fornitore è disattivato.

**Scritture contabili di esempio:** canone di leasing<br>
**Dare:** obbligazione sul leasing XXX<br>
**Avere:** canone di leasing XXX

## <a name="expense-type-postings"></a>Registrazioni del tipo di spesa

Sul conto selezionato per ogni tipo di spesa viene effettuato un addebito quando viene generato un pagamento per quel tipo di spesa. Ad esempio, sul conto specificato per il tipo di spesa **Assicurazione** viene effettuato un addebito ogni volta che viene creata una fattura o una scrittura contabile di pagamento dalla pianificazione del costo esecutivo per le spese assicurative.

**Scritture contabili di esempio:** pagamento assicurazione<br>
**Dare:** conto tipo di spesa assicurativa XXX<br>
**Avere:** conto di contropartita XXX

> [!NOTE]
> Il conto di contropartita viene selezionato a livello di leasing nelle righe per il programma di pagamento del costo esecutivo. Questo conto di contropartita può essere associato al fornitore o a un conto CoGe.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
