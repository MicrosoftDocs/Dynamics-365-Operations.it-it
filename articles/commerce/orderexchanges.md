---
title: Configurare ed elaborare uno scambio in un ordine di reso
description: In questo argomento viene descritto come configurare uno scambio su un reso in Dynamics 365 Commerce.
author: josaw1
ms.date: 07/28/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 488f6fb5af6451bc462566a9714054b49eb1a80b8264528778797f6a39647764
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758338"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>Configurare ed elaborare uno scambio in un ordine di reso

[!include [banner](includes/banner.md)]

Nelle versioni precedenti di Dynamics 365 Commerce, i resi a fronte degli ordini cliente venivano elaborati tramite il documento dell'ordine di reso in Headquarters. Tuttavia, il documento dell'ordine di reso può essere utilizzato per elaborare solo i prodotti resi. I prodotti resi sono indicati da una quantità negativa nelle righe dell'ordine di reso. Di contro, le vendite vengono contrassegnate da una quantità positiva. Tuttavia, il documento dell'ordine di reso non supporta le quantità positive. A causa di questa limitazione, le versioni precedenti dell'app non supportavano scenari in cui gli scambi di prodotto sono effettuati utilizzando il documento dell'ordine di reso.

Tuttavia, è stata aggiunta una funzionalità per supportare gli scenari in cui gli scambi vengono effettuati sugli ordini di reso. Commerce utilizza ora il documento dell'ordine cliente anziché il documento dell'ordine di reso per elaborare questi tipi di transazioni.

## <a name="configure-commerce-to-support-exchanges-on-return-orders"></a>Configurare Commerce per supportare gli scambi sugli ordini di reso

> [!NOTE]
> In Commerce versione 10.0.20 e successive è disponibile una nuova funzionalità denominata "Esperienza di elaborazione dei resi unificata in POS". Se si abilita la funzionalità, i seguenti passaggi di configurazione non sono necessari. **Elabora ordini di reso come ordini cliente** diventa un'impostazione configurata in modo permanente e non è possibile modificarla.

Attenersi alla seguente procedura per configurare il sistema per supportare gli scambi sugli ordini di reso (se la funzionalità **Esperienza unificata nell'elaborazione dei resi in POS** non è abilitata.

1. Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri di commercio**. Nella Scheda dettaglio **Ordini cliente**, impostare l'opzione **Elabora ordini di reso come ordini cliente** su **Sì**.
2. Eseguire il processo **Programmazione di distribuzione configurazione globale** (**1110**).

## <a name="make-an-exchange"></a>Eseguire uno scambio

Dopo che il sistema è configurato come descritto nella sezione precedente, l'utente di POS selezionerà comunque un ordine cliente o una fattura di vendita per elaborare un reso, come nelle versioni precedenti dell'app. Tuttavia, dopo che i resi vengono aggiunti al carrello, l'utente potrà aggiungere nuove righe di vendita al carrello.

Per le nuove righe di vendita, l'utente deve definire tutti gli attributi necessari per l'elaborazione di una riga di ordine cliente. Tali attributi includono il metodo di consegna e l'ubicazione di evasione. Il pagamento dovuto per la transazione sarà il netto delle righe dell'ordine di reso e righe ordine cliente. Quando un pagamento viene offerto per la transazione, l'ordine di reso verrà registrato come documento dell'ordine cliente in Headquarters e il sistema fatturerà immediatamente le righe di reso.

Per una maggiore visibilità dei vari importi relativi al carrello, tre nuovi campi di importi sono stati aggiunti al carrello. È possibile utilizzare la finestra di progettazione della schermata per rendere disponibili i nuovi campi nell'interfaccia utente di POS (UI).

- **Deposito applicato**: l'importo del deposito applicato in una transazione quando l'utente effettua un prelievo dell'ordine cliente. Se non esiste alcuna sostituzione deposito e viene configurato un deposito del 10 per cento, l'importo riportato in questo campo è 90 percento dell'importo totale dell'ordine cliente.
- **Importo esecuzione**: l'importo totale per le righe in cui la modalità di consegna è stata impostata su **Eseguire** quando l'ordine cliente è stato creato o modificato o durante lo scambio degli ordini cliente. L'importo in questo campo include IVA e spese.
- **Importo reso**: l'importo totale per le righe con le quantità negative durante lo scambio dell'ordine cliente. L'importo in questo campo include IVA e spese.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
