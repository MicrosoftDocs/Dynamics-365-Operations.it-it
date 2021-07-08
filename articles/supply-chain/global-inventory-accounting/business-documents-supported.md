---
title: Documenti aziendali supportati da Contabilità inventario globale
description: Questo argomento elenca i documenti commerciali supportati da Contabilità inventario globale. Fornisce inoltre un esempio dettagliato per i documenti dell'ordine fornitore.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 311c894d709985d0d053b0ec3a317142aa582c39
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273181"
---
# <a name="business-documents-supported-by-global-inventory-accounting"></a>Documenti aziendali supportati da Contabilità inventario globale

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Dopo che il componente aggiuntivo Contabilità inventario globale è stato completamente configurato, è pronto per elaborare i documenti relativi all'inventario immessi in Microsoft Dynamics 365 Supply Chain Management.

## <a name="supported-business-documents"></a>Documenti aziendali supportati

Sono disponibili due tipi di documenti aziendali:

- **Documenti che hanno un giornale di registrazione** – Questi documenti includono la ricevuta del prodotto, la fattura di acquisto, la distinta di imballaggio e la fattura di vendita.
- **Documenti che non hanno un giornale di registrazione** – Questi documenti includono conteggio, movimento e rettifica dell'inventario.

Più avanti in questo argomento, gli ordini fornitore verranno utilizzati come esempio per illustrare il processo.

La tabella seguente elenca i documenti supportati dalla versione corrente.

| Tipo di documento      | Documento        |
|--------------------|-----------------|
| Ordine fornitore     | Entrata prodotti |
| Ordine fornitore     | Fattura         |
| Ordine cliente        | Documento di trasporto    |
| Ordine cliente        | Fattura         |
| Giornali di registrazione magazzino | Movimento        |
| Giornali di registrazione magazzino | Rettifica      |
| Giornali di registrazione magazzino | Conteggio        |
| Giornali di registrazione magazzino | Trasferito        |
| Ordine di trasferimento     | Spedizione        |
| Ordine di trasferimento     | Ricevimento         |

> [!IMPORTANT]
> Contabilità inventario globale elabora in modo asincrono i documenti immessi in Supply Chain Management. Nessun messaggio di errore verrà mostrato per i documenti problematici.

## <a name="example-purchase-order"></a>Esempio: ordine fornitore

### <a name="product-receipt"></a>Entrata prodotti

Pubblica le ricevute dei prodotti nel modo consueto. Nella pagina **Tutti gli ordini fornitore** seleziona un ordine fornitore, quindi, nel riquadro azioni, nella scheda **Ricevuta** seleziona **Ricevuta prodotto** per aprire la pagina **Giornale di registrazione ricevute prodotti**. Per ogni riga vengono generati un evento operazione e un evento Contabilità inventario globale. Pertanto, seleziona la scheda **Righe** quindi seleziona **Inventario \> Eventi e misure** per aprire la pagina **Eventi e misure**.

Contabilità inventario globale è un sistema di contabilità basato su eventi e misure. La griglia della riga di misura sulla pagina **Eventi e misure** mostra un elenco di misure. Ogni misura ha un elenco di dimensioni.

Per ogni evento di operazione sono previste due tipologie di misura:

- **Misure delle operazioni** – Queste misure descrivono i documenti commerciali in termini generici. Una misura è la quantità del prodotto utilizzando l'unità di misura usata nel documento. Esistono anche misure che influiscono sul valore dell'inventario, ad esempio prezzo esteso, sconto, percentuale di sconto e addebito riga.
- **Misure contabili delle risorse** – Queste misure sono dal punto di vista del registro di inventario. Descrivono l'impatto del documento sull'inventario nell'unità di misura dell'inventario. Se sono presenti più registrazioni di inventario, sono presenti più righe di misure della contabilità delle risorse.

Le dimensioni sono organizzate nel modo seguente:

- **Dualità** – La dualità descrive gli agenti che partecipano agli eventi economici. Per i documenti commerciali esterni, le dimensioni primarie descrivono la persona giuridica in cui viene immesso il documento, mentre le dimensioni duali descrivono il fornitore, il cliente e così via. Per i documenti commerciali interni (ad esempio, gli ordini di trasferimento), le dimensioni duali descrivono il magazzino di controparte.
- **Tipo di dimensione** – I tipi di dimensione classificano le dimensioni.
- **Dimensione** – Il nome della dimensione.
- **Valore dimensione** – Il valore della dimensione.

### <a name="global-inventory-accounting-event"></a>Evento di contabilità inventario globale

Contabilità inventario globale usa come input gli eventi operativi e le misure. Quindi esegue la contabilità appropriata per ciascun libro contabile correlato, in base alla valuta e alla convenzione collegate. Puoi selezionare **Eventi e misure contabilità inventario globale** per visualizzare l'evento Contabilità inventario globale. L'evento Contabilità inventario globale segue la stessa metodologia degli eventi operativi, ma utilizza misure diverse. Esistono tre tipi di misure principali: quantità del costo del prodotto, costo del prodotto e scostamento.

I conti CoGe secondari vengono utilizzati per classificare ulteriormente le misure. Potrebbero esserci più libri contabili. Questi libri contabili sono collegati alla persona giuridica in cui viene inserito il documento. È possibile visualizzare gli eventi e le misure per ogni libro contabile modificando il valore del campo **Libro contabile**.

### <a name="cost-element"></a>Elemento di costo

In base ai criteri dell'elemento di costo collegata al libro contabile, il sistema assegna un elemento di costo a ciascuna misura dell'evento dell'operazione contabilizzata che influisce sul costo delle scorte. Queste misure includono prezzo esteso, sconto, percentuale di sconto e addebito riga.

### <a name="measurement-line-details"></a>Dettagli riga di misura

La scheda **Panoramica** mostra i dettagli dei criteri collegati. Le dimensioni oggetto di costo mostrano l'oggetto di costo, in base al criterio oggetto di costo. Le dimensioni di identificazione specifiche mostrano il numero batch se l'ipotesi di flusso dei costi è *Specifico – Batch*.

### <a name="purchase-invoice"></a>Fattura acquisto

Pubblica la fattura nel modo consueto. Quindi, nella scheda **Fattura** del riquadro azioni, nel gruppo **Giornali di registrazione**, seleziona **Fattura** per aprire il giornale di registrazione fatture. Per ogni riga vengono generati un evento operazione e un evento Contabilità inventario globale. Pertanto, seleziona la scheda **Righe** quindi seleziona **Inventario \> Eventi e misure** per aprire la pagina **Eventi e misure**. La pagina **Eventi e misure** mostra lo stesso tipo di misura. Tuttavia, poiché la pagina mostra un ruolo di misura e un modificatore di misura diversi, l'impatto sull'agente (persona giuridica) è diverso.

Seleziona **Eventi e misure contabilità inventario globale** per visualizzare l'evento Contabilità inventario globale. La quantità e il costo dell'inventario ora passano dal conto CoGe secondario *Merce ricevuta non fatturata inventario* e nel conto CoGe secondario *Costo della merce acquistata*.
