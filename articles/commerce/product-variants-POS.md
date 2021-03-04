---
title: Ricerca di scorte nel POS
description: In questo argomento vengono descritte le opzioni disponibili per esaminare le informazioni sulle scorte nel POS.
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: 1d6133d80d7674a1d896bc19a743a6bd4d0fb40f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413567"
---
# <a name="inventory-lookup-in-the-point-of-sale-pos"></a>Ricerca di scorte nel POS

[!include [banner](includes/banner.md)]

La ricerca di scorte nel POS aiuta i rivenditori a raggiungere l'eccellenza operativa in tempo reale e a ottenere informazioni dettagliate collegando punti vendita, POS e back office. Questa funzionalità fornisce una visione accurata in tempo reale dell'inventario dei prodotti nei punti vendita e centri di distribuzione. Consente inoltre ai rivenditori a incrementare l'efficienza e ridurre i costi migliorando la pianificazione delle scorte in tempo reale.

Un'accurata visualizzazione in tempo reale dell'inventario in un'organizzazione consente alle filiali di fornire un servizio clienti tempestivo e di qualità superiore. Il momento che conta di più è il momento in cui il cliente è pronto a prendere una decisione d'acquisto. È importante che i cassieri del punto vendita abbiano a portata di mano informazioni sulle scorte in tempo reale, in modo che possano promettere in modo preciso la consegna e il ritiro dei prodotti.

È possibile aprire la pagina **Ricerca in magazzino** dall'area di lavoro **Retail Modern POS** o dall'area di lavoro **Retail Cloud POS**.

![Riquadro Ricerca in magazzino nella home page del POS](media/POSHomepage.png)

Nella pagina **Ricerca in magazzino**, è possibile utilizzare la tastiera numerica per immettere un numero prodotto. È quindi possibile visualizzare la quantità disponibile per più punti vendita e magazzini.

![Pagina standard di Ricerca in magazzino](media/InventoryLookUp.png)

Le quantità **Ordinato** e **Prenotato** vengono visualizzate per ogni ubicazione.

- **Prenotato**: questa quantità si riferisce al valore **Fisico prenotato** dal back office per il numero di prodotto specificato nell'ubicazione.
- **Ordinato**: questa quantità si riferisce al valore **Ordinato in totale** dal back office per il numero di prodotto specificato nell'ubicazione.

## <a name="locations-that-inventory-availability-information-is-shown-for"></a>Ubicazioni per cui vengono visualizzate le informazioni sulla disponibilità delle scorte

L'elenco delle ubicazioni include due tipi di entità:

- **Punti vendita**: l'elenco mostra i punti vendita configurati utilizzando il gruppo di ricerca punto vendita per il punto vendita corrente in Headquarters.
- **Centri di distribuzione**: diversi tipi di centri di distribuzione (ad esempio magazzini) possono essere configurati in Commerce. Tuttavia, l'elenco mostra le informazioni sulla disponibilità delle scorte solo per i centri di distribuzione del tipo predefinito **Standard**.

    > [!NOTE]
    > Le informazioni di magazzino non vengono visualizzate per i tipi di magazzino **Transito**, **Quarantena** e **Articoli in lavorazione** per il POS.

Nella pagina **Ricerca in magazzino**, è possibile visualizzare le quantità available-to-promise (ATP) per ogni punto vendita, oltre alle quantità scorte disponibili correnti, alle quantità prenotate e alle quantità ordinate. Selezionare il punto vendita per cui visualizzare le informazioni ATP e quindi selezionare **Mostra disponibilità punto vendita**.

![Quantità ATP](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a>Apertura della visualizzazione matrice basata su dimensione per mostrare tutte le varianti

Nella pagina **Dettagli prodotto** di una rappresentazione generale prodotto oppure nella pagina **Ricerca in magazzino** selezionare **Visualizza tutte le varianti** dalla barra delle applicazioni nella parte inferiore della pagina. La visualizzazione **Matrice basata su dimensione** per l'avvio iniziale da queste pagine mostra le informazioni sulla disponibilità delle scorte per tutte le varianti di un prodotto per il punto vendita corrente.

> [!NOTE]
> Il pulsante **Visualizza tutte le varianti** è disponibile solo per le rappresentazioni generali prodotto di articoli con varianti prodotto. Non è disponibile per i prodotti autonomi o per i kit.

![Pulsante Visualizza tutte le varianti nella pagina di ricerca in magazzino](media/StandardToMatrix.png)

Selezionare **Visualizza tutte le varianti** nella pagina **Dettagli prodotto** di una rappresentazione generale prodotto oppure nella pagina **Ricerca in magazzino** senza selezionare un'ubicazione, passare alla visualizzazione **Matrice basata su dimensione** per visualizzare le informazioni sulla disponibilità delle scorte per tutte le varianti di un prodotto per il punto vendita corrente.

![Visualizzazione Matrice basata su dimensione per la pagina Ricerca in magazzino](media/Matrix.png)

> [!NOTE]
> Nell'illustrazione precedente, l'ordine di visualizzazione delle dimensioni è alfabetico, poiché l'ordine di visualizzazione delle dimensioni non è stato configurato per il prodotto selezionato.

Nella visualizzazione **Matrice basata su dimensione**, le celle per le varianti del prodotto includono un valore delle scorte disponibili nell'angolo in basso a destra. Nella tabella seguente viene illustrato il significato dei diversi valori.

| Valore disponibilità                            | descrizione |
|------------------------------------------|-------------|
| Valore numerico maggiore di 0 (zero) | Una variante è stata rilasciata nell'ubicazione selezionata ed è possibile eseguire ulteriori azioni nella cella. Queste azioni verranno descritte in modo più dettagliato nelle sezioni successive dell'argomento. |
| **0** (zero)                             | Una variante è stata rilasciata nell'ubicazione selezionata, ma l'articolo non è disponibile nell'ubicazione selezionata. Tuttavia, è possibile eseguire operazioni aggiuntive nella cella. Queste azioni verranno descritte in modo più dettagliato nelle sezioni successive dell'argomento. |
| **n/a** o cella non attiva              | Una variante non è stata rilasciata nell'ubicazione selezionata e non è possibile eseguire ulteriori azioni nella cella. |

È inoltre possibile modificare il pivot per le dimensioni selezionando la nuova dimensione da utilizzare.

![Cambiamento del pivot](media/ChangePivot.png)

![Pivot modificato](media/PivotChanged.png)

> [!NOTE]
> Nelle illustrazioni precedenti, l'ordine di visualizzazione delle dimensioni per il prodotto selezionato è personalizzato (non alfabetico). Si basa sull'ordine di visualizzazione delle dimensioni impostato nel back office.

Inoltre, nella visualizzazione **Matrice basata su dimensione** è possibile eseguire più azioni per aumentare la produttività di una filiale del punto vendita. Di seguito sono riportati alcuni esempi.

- Modificare l'ubicazione del punto vendita per eseguire una ricerca della disponibilità di scorte di tutte le varianti del prodotto in altre ubicazioni. Queste ubicazioni includono altri punti vendita nel gruppo di localizzatore punto vendita e nei centri di distribuzione del tipo predefinito **Standard**.
- Vendere una singola variante prodotto a un cliente utilizzando la modalità cash-and-carry, ritiro presso un punto vendita o spedizione a un indirizzo.
- Fornire al cliente informazioni ATP per una singola variante prodotto in un'ubicazione specifica.

![Azioni aggiuntive per i riquadri delle variabili](media/VariantActions.png)

> [!NOTE]
> Nell'illustrazione precedente, l'ordine di visualizzazione delle dimensioni è alfabetico, poiché l'ordine di visualizzazione delle dimensioni non è stato configurato per il prodotto selezionato.

Nella tabella seguente vengono fornite ulteriori informazioni sulle azioni aggiuntive disponibili.

| Azione               | descrizione |
|----------------------|-------------|
| Vendi adesso             | Aggiunge la variante dell'articolo selezionata alla transazione e reindirizza l'utente alla schermata della transazione. Questa azione non è disponibile quando l'ubicazione selezionata è un centro di distribuzione. |
| Preleva al punto vendita     | Crea un ordine cliente per la variante prodotto che verrà prelevata dall'ubicazione selezionata e reindirizza l'utente alla schermata della transazione. Questa azione non è disponibile quando l'ubicazione selezionata è un centro di distribuzione. |
| Spedizione prodotto         | Crea un ordine cliente per la variante prodotto che verrà spedita dall'ubicazione selezionata e reindirizza l'utente alla schermata della transazione. |
| Disponibilità         | Visualizza informazioni ATP per la combinazione di varianti selezionata per l'ubicazione selezionata. |
| Mostra tutte le ubicazioni   | Passa alla visualizzazione della ricerca in magazzino standard ed evidenzia le informazioni sulla disponibilità delle scorte per la variante articolo in tutti i punti vendita nel gruppo di localizzatore punto vendita e anche nei centri di distribuzione di tipo **Standard/Predefinito**. |
| Visualizza dettagli prodotto | Reindirizza l'utente alla pagina **Dettagli prodotto** della rappresentazione generale prodotto associata. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]