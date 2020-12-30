---
title: Rettificare leasing
description: L'argomento spiega come rettificare un leasing. Potrebbe essere necessario una rettifica se i termini del leasing vengono modificati, il leasing viene prolungato o altre circostanze cambiano.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9d1c6e20e72fb2816c32e71e8921a94724ae5656
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444996"
---
# <a name="adjust-leases"></a>Rettificare leasing

[!include [banner](../includes/banner.md)]

L'argomento spiega come rettificare un leasing. Potrebbe essere necessario una rettifica se i termini del leasing vengono modificati, il leasing viene prolungato o altre circostanze cambiano. Il leasing di cespiti è conforme alle linee guida fornite dagli standard Accounting Standards Codification Topic 842 (ASC 842) e International Financial Reporting Standard 16 (IFRS 16) sulle modifiche del leasing. ASC 842-20-15-1 definisce una modifica del leasing come qualsiasi modifica ai termini e alle condizioni di un contratto che causa una modifica dell'ambito o nella considerazione di un leasing. Il paragrafo 39 dell'IFRS 16 stabilisce che un conduttore deve rivalutare l'obbligazione sul leasingin modo che rifletta le modifiche ai canoni di leasing.

Per le organizzazioni che aderiscono ad ASC 842 o IFRS 16, un leasing viene rimisurato per riflettere una variazione del valore attuale dei canoni minimi futuri del leasing (PVFMLP). Se il PVFMLP aumenta, la scrittura contabile creata sarà un addebito sull'Asset Right of use e un accredito sull'obbligazione sul leasing per la differenza tra il nuovo PVFMLP e il PVFMLP precedente. Se il PVFMLP diminuisce, la scrittura contabile sarà un addebito sull'obbligazione sul leasing e un acredito all'Asset ROU per la differenza.

Se la rettifica riduce l'Asset ROU oltre 0 (zero), il resto verrà accreditato sul conto di registrazione del guadagno sulla modifica del leasing specificato nella pagina **Conti di registrazione leasing**. Il sistema contabilizza queste transazioni e di altre voci di rettifica, quali modifiche alla classificazione, costi diretti iniziali, incentivi di leasing, pagamenti anticipati e costi di smantellamento derivanti da modifiche del leasing.

Per indicazioni specifiche sulle transazioni di rettifica del leasing, si consiglia di consultare IFRS 16 e l'ASC 842.

Per rettificare un leasing, segui questi passaggi. I dati modificati aggiorneranno i programmi di leasing dopo l'esecuzione del processo di creazione della pianificazione.

1. Vai a **Leasing cespiti \> Leasing \> Riepilogo leasing**.
2. Nella pagina **Riepilogo leasing**, seleziona il leasing da rettificare, quindi seleziona **Rettifica leasing**.
3. Nella pagina **Rettifica leasing**, immetti le nuove informazioni per il lasing rettificato.

    Tieni presente che la pagina **Rettifica leasing** ha un aspetto simile alla pagina **Aggiungi leasing**. Inoltre, proprio come la data di inizio specificata quando si aggiunge un leasing determina quando inizia il nuovo leasing, il campo **Data di modifica** della pagina **Rettifica leasing** determina quando inizia il leasing modificato. Questa data non può essere successiva alla data di inizio nelle righe dello scadenzario pagamenti.

    > [!NOTE]
    > I campi **Considerazioni ROU** si applicano alla rettifica del leasing. Se al leasing modificato non sono associati costi diretti iniziali, incentivi di leasing, pagamenti anticipati o costi di smantellamento, lascia questi campi vuoti. Gli importi originali non si applicheranno al leasing aggiornato. Eventuali costi aggiuntivi sostenuti in occasione della modifica del leasing devono essere inseriti nella pagina **Rettifica leasing**.
    > 
    > Ad esempio, un locatore fornisce un incentivo di $1.000 per accettare un'estensione del leasing. In questo caso, quando modifichi il leasing per contabilizzare l'estensione, immetti **1.000** nel campo **Incentivi di leasing**. Se nessun incentivo è associato alla rettifica del leasing, è consigliabile cancellare qualsiasi valore precedentemente inserito in questo campo. La stessa logica viene applicata ad altre considerazioni ROU.

    Le righe nello scadenziario pagamenti del leasing rettificato dovrebbero essere create su base prospettica. Le righe dello scadenzario pagamenti create su base prospettiva non possono iniziare prima che le modifiche del leasing abbiano effetto.

    I passaggi seguenti sono quasi identici a quelli per il riconoscimento iniziale di un leasing.

4. Seleziona **Crea scadenziari** per generare lo scadenziario pagamenti rettificato. Viene visualizzato un messaggio che informa che è stato creato lo scadenzario dei pagamenti per il leasing.

    > [!IMPORTANT]
    > Prima di selezionare **Crea scadenziari**, assicurati che la data di modifica e le righe dello scadenzario pagamenti siano corrette. Assicurati inoltre che tutti i costi diretti iniziali, gli incentivi di leasing, i pagamenti anticipati o i costi di smantellamento corrispondano solo ai costi che derivano dalla rettifica.

5. Per visualizzare lo scadenziario pagamenti appena creato, seleziona **Libri** e apri la pagina **Scadenziario pagamenti**.
6. Nella pagina **Scadenziario pagamenti** puoi modificare gli importi dei pagamenti rettificati prima di confermare lo scadenziario pagamenti. Per confermare lo scadenziario, seleziona **Conferma scadenziario**.

    Quando lo scadenziario pagamenti viene confermato, vengono creati il nuovo ammortamento dei cespiti e i nuovi programmi di canone di leasing.

7. Per visualizzare il nuovo piano di ammortamento dell'obbligazione sul leasing generato dai nuovi input, chiudei la pagina **Scadenziario pagamenti** e apri il la pagina **Piano di ammortamento dell'obbligazione**.
8. Per visualizzare il piano di ammortamento dei cespiti appena generato, apri la pagina **Piano di ammortamento dei cespiti** dalla pagina **Dettagli libro**.
9. Per generare la scrittura contabile di rettifica, seleziona **Funzione \> Rettifica leasing**. Ricevi un messaggio che informa che la scrittura contabile di rettifica è stata creata. 
10. Per visualizzare la scrittura contabile, seleziona **Giornali di registrazione \> Giornale di registrazione leasing cespiti**.
11. Per registrare la scrittura contabile, selezionare la riga, quindi seleziona **Registra**.

## <a name="view-lease-versions"></a>Visualizzare le versioni del leasing

Se un leasing è stato modificato, puoi visualizzarne le diverse versioni. Puoi inoltre visualizzare le pianificazioni storiche e i dettagli dei leasing precedenti.

1. Nella pagina **Riepilogo leasing**, seleziona il leasing, quindi, nel riquadro azioni, seleziona **Cronologia versioni leasing**.

    Se il leasing selezionato è stato rettificato, la pagina **Cronologia versioni leasing** mostra le sue diverse versioni. Il leasing originale è etichettato **1** e le versioni successive hanno un ordine numerico crescente.

    Per una versione di leasing selezionata, puoi visualizzare le dimensioni finanziarie, i dettagli del contratto, la posizione e le righe dello scadenzario pagamenti.

2. Per visualizzare i programmi storici, apri il leasing modificato dalla pagina **Riepilogo leasing**, seleziona il libro desiderato, quindi, nel riquadro azioni, seleziona **Cronologia versioni libro**.
3. Nella pagina **Versione libro** seleziona la versione desiderata e il programma desiderato da visualizzare.
