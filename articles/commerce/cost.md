---
title: Configurazione dei costi per la gestione ordini distribuiti
description: In questo argomento viene descritta la configurazione dei costi per la gestione degli ordini distribuiti (DOM, Distributed Order Management) in Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: b96780745e8dd8a6e2b46a3286bf4a6a307d886c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001051"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a>Configurazione dei costi per la gestione ordini distribuiti

[!include [banner](../includes/banner.md)]

Per stabilire l'ubicazione ottimale da cui evadere un ordine, le organizzazioni prendono in considerazione più componenti di costo. Alcune componenti sono rappresentate dalla spedizione, il trasporto e l'imballaggio. Per determinare l'ubicazione di evasione, viene calcolata una combinazione di tali costi.

Nell'ottimizzazione dell'assegnazione degli ordini nelle ubicazioni di evasione durante la prima iterazione di gestione degli ordini distribuiti (DOM) in Dynamics 365 Commerce, si teneva conto solo della distanza. Sebbene la distanza possa essere correlata ai costi, non può essere considerati alla pari di un costo. Una spedizione effettuata durante la notte, ad esempio, costa più di una spedizione di tre giorni o di sette giorni sulla stessa distanza.

La funzionalità di configurazione dei costi consente ai rivenditori di definire e configurare componenti di costo aggiuntivo che verranno calcolate e prese in considerazione per determinare l'ubicazione ottimale da cui evadere le righe ordine.

Quando le componenti di costo vengono configurate, il risolutore DOM utilizza solo tali definizioni di costo per determinare l'ubicazione ottimale per l'evasione dell'ordine. La distanza non viene considerata come componente di costo. Se non viene configurata alcune componente di costo, tuttavia, il risolutore DOM utilizza la distanza come componente di costo per determinare l'ubicazione ottimale per l'evasione dell'ordine.

## <a name="set-up-cost-components"></a>Configurare le componenti di costo

Nel sistema è possibile definire due tipi di componenti di costo principali: **Spedizione** e **Altro**.

Entrambi i tipi supportano più basi di calcolo, come illustrato nella tabella seguente.

<table>
<thead>
<tr>
<th>Tipo di componente di costo</th>
<th>Base di calcolo</th>
</tr>
</thead>
<tbody>
<tr>
<td>Spedizione</td>
<td>
<ul>
<li>Semplice</li>
<li>A livelli</li>
</ul>
</td>
</tr>
<tr>
<td>Altro</td>
<td>
<ul>
<li>Ordine cliente</li>
<li>Riga di vendita</li>
<li>Ubicazione</li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a>Tipo di componente di costo Spedizione

In questa sezione viene descritto come configurare ciascuna combinazione del tipo di componente di costo **Spedizione** e di base di calcolo per i costi di spedizione. Viene inoltre illustrato come il risolutore DOM utilizza ciascuna combinazione.

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a>Tipo componente di costo = Spedizione e base di calcolo = Semplice

Se viene utilizzata una combinazione del tipo di componente di costo **Spedizione** e della base di calcolo **Semplice**, il costo di spedizione per una modalità di consegna si basa su un costo forfettario o sulla distanza.

Per questa combinazione, è necessario impostare i campi seguenti:

- **Fattore costo** - Immettere un identificatore univoco per il fattore di costo.
- **Descrizione** - Immettere il nome e la descrizione del fattore di costo.
- **Data di inizio** e **Data di fine** - Questi campi consentono di limitare il fattore di costo per un intervallo di date specifico. Se questi campi vengono lasciati vuoti, il fattore di costo è valido per un periodo di tempo indefinito.
- **Attivo** - Indica se il fattore di costo è attivo. La funzionalità DOM prende in considerazione solo i fattori di costo attivi associati al profilo di evasione.
- **Società** - Specifica la persona giuridica per cui è configurato il fattore di costo. Tutte le righe dei criteri di calcolo devono essere correlate alla stessa persona giuridica.
- **Modalità di consegna** - Specifica le modalità di consegna per cui è configurato il costo.
- **Tipo di calcolo** - Specifica le modalità di calcolo del costo per una determinata modalità di consegna. Sono supportati due tipi di calcolo:

    - **Fisso** - Per la modalità di consegna viene utilizzato un costo forfettario. Se si seleziona questo tipo di calcolo, il campo **Costo** definisce il costo forfettario.
    - **Per unità di distanza** - Il costo per la modalità di consegna viene calcolato come il valore del costo specificato nel campo **Costo** moltiplicato per la distanza tra l'indirizzo di consegna e le ubicazioni.

- **Costo** - Specifica il valore di costo utilizzato in combinazione con il campo **Tipo di calcolo** per calcolare il costo di una modalità di consegna.

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a>Tipo componente di costo = Spedizione e base di calcolo = A livelli

Se viene utilizzata una combinazione del tipo di componente di costo **Spedizione** e della base di calcolo **A livelli**, il costo di spedizione per una modalità di consegna si basa su un costo forfettario o sulla distanza. In questa combinazione, tuttavia, la distanza si basa su un intervallo di distanze a livelli.

Per questa combinazione, è necessario impostare i campi seguenti:

- **Fattore costo** - Immettere un identificatore univoco per il fattore di costo.
- **Descrizione** - Immettere il nome e la descrizione del fattore di costo.
- **Costo predefinito** - Specifica il costo da utilizzare per una modalità di consegna se la distanza tra l'indirizzo di consegna e l'ubicazione non rientra in una delle distanze a livelli per la modalità di consegna.
- **Data di inizio** e **Data di fine** - Questi campi consentono di limitare il fattore di costo per un intervallo di date specifico. Se questi campi vengono lasciati vuoti, il fattore di costo è valido per un periodo di tempo indefinito.
- **Attivo** - Indica se il fattore di costo è attivo. La funzionalità DOM prende in considerazione solo i fattori di costo attivi associati al profilo di evasione.
- **Società** - Specifica la persona giuridica per cui è configurato il fattore di costo. Tutte le righe dei criteri di calcolo devono essere correlate alla stessa persona giuridica.
- **Modalità di consegna** - Specifica le modalità di consegna per cui è configurato il costo.
- **Tipo distanza** - Specifica se la definizione di distanza a livelli è aerea o stradale.
- **Unità di distanza** - Specifica l'unità di misura della distanza a livelli.
- **Distanza da** - Specifica l'intervallo iniziale per la distanza a livelli.
- **Distanza a** - Specifica l'intervallo finale per la distanza a livelli.
- **Tipo di calcolo** - Specifica le modalità di calcolo del costo per una modalità di consegna e una distanza a livelli specifiche. Sono supportati due tipi di calcolo:

    - **Fisso** - Per la modalità di consegna viene utilizzato un costo forfettario. Se si seleziona questo tipo di calcolo, il campo **Costo** definisce il costo forfettario.
    - **Per unità di distanza** - Il costo per la modalità di consegna e la distanza a livelli viene calcolato come il valore del costo specificato nel campo **Costo** moltiplicato per la distanza tra l'indirizzo di consegna e le ubicazioni.

- **Costo** - Specifica il valore di costo utilizzato in combinazione con il campo **Tipo di calcolo** per calcolare il costo di una modalità di consegna.

> [!NOTE]
> - Quando si definiscono le distanze a livelli, nel sistema viene verificato che tutte le distanze siano presenti e che non siano presenti distanze sovrapposte.
> - Il tipo di distanza utilizzato per la modalità di consegna deve essere lo stesso per tutte le distanze a livelli.

### <a name="other-cost-component-type"></a>Altro tipo di componente di costo

In questa sezione viene descritto come configurare ciascuna combinazione del tipo di componente di costo **Altro** e di un altro tipo di costo per costi diversi da quelli di spedizione. Viene inoltre illustrato come il risolutore DOM utilizza ciascuna combinazione.

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a>Tipo di componente di costo = Altro e altro tipo di costo = Ordine cliente

Una combinazione del tipo di componente di costo **Altro** e di un altro tipo di costo **Ordine cliente** viene utilizzata per definire costi diversi da quelli di spedizione a livello di ordine cliente.

Per questa combinazione, è necessario impostare i campi seguenti:

- **Fattore costo** - Immettere un identificatore univoco per il fattore di costo.
- **Descrizione** - Immettere il nome e la descrizione del fattore di costo.
- **Data di inizio** e **Data di fine** - Questi campi consentono di limitare il fattore di costo per un intervallo di date specifico. Se questi campi vengono lasciati vuoti, il fattore di costo è valido per un periodo di tempo indefinito.
- **Attivo** - Indica se il fattore di costo è attivo. La funzionalità DOM prende in considerazione solo i fattori di costo attivi associati al profilo di evasione.
- **Costo** - Specifica il valore del costo per un costo diverso da quello di spedizione a livello di ordine cliente.

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a>Tipo di componente di costo = Altro e altro tipo di costo = Riga ordine

Una combinazione del tipo di componente di costo **Altro** e di un altro tipo di costo **Riga vendita** viene utilizzata per definire costi diversi da quelli di spedizione a livello di riga ordine cliente.

Per questa combinazione, è necessario impostare i campi seguenti:

- **Fattore costo** - Immettere un identificatore univoco per il fattore di costo.
- **Descrizione** - Immettere il nome e la descrizione del fattore di costo.
- **Data di inizio** e **Data di fine** - Questi campi consentono di limitare il fattore di costo per un intervallo di date specifico. Se questi campi vengono lasciati vuoti, il fattore di costo è valido per un periodo di tempo indefinito.
- **Attivo** - Indica se il fattore di costo è attivo. La funzionalità DOM prende in considerazione solo i fattori di costo attivi associati al profilo di evasione.
- **Costo** - Specifica il valore del costo per un costo diverso da quello di spedizione a livello di riga ordine cliente.

#### <a name="cost-component-type--other-and-other-cost-type--location"></a>Tipo di componente di costo = Altro e altro tipo di costo = Ubicazione

Una combinazione del tipo di componente di costo **Altro** e di un altro tipo di costo **Ubicazione** viene utilizzato per definire costi diversi da quelli di spedizione per un gruppo di ubicazioni o per un'ubicazione singola.

Per questa combinazione, è necessario impostare i campi seguenti:

- **Fattore costo** - Immettere un identificatore univoco per il fattore di costo.
- **Descrizione** - Immettere il nome e la descrizione del fattore di costo.
- **Data di inizio** e **Data di fine** - Questi campi consentono di limitare il fattore di costo per un intervallo di date specifico. Se questi campi vengono lasciati vuoti, il fattore di costo è valido per un periodo di tempo indefinito.
- **Attivo** - Indica se il fattore di costo è attivo. La funzionalità DOM prende in considerazione solo i fattori di costo attivi associati al profilo di evasione.
- **Gruppo di evasione** - Specifica il gruppo di ubicazioni per cui è definito il costo diverso da quello di spedizione.
- **Ubicazione di evasione** - Specifica l'ubicazione per cui è definito il costo diverso da quello di spedizione.

    > [!NOTE]
    > Non è possibile specificare un gruppo di evasione né un'ubicazione di evasione sulla stessa riga per i criteri di calcolo basati sull'ubicazione.

- **Costo** - Specifica il valore del costo per un costo diverso da quello di spedizione a livello di gruppo o di ubicazione di evasione.

> [!IMPORTANT]
> La funzionalità DOM prende in considerazione questi costi durante l'esecuzione solo se il fattore di costo viene aggiunto al profilo di evasione rilevante.


[!INCLUDE[footer-include](../includes/footer-banner.md)]