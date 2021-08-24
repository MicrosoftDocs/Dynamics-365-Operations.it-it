---
title: Operazione di ricerca in magazzino nel POS
description: Questo argomento descrive come utilizzare l'operazione di ricerca in magazzino nel POS di Dynamics 365 Commerce per visualizzare la disponibilità delle scorte dei prodotti in punti vendita e magazzini.
author: boycezhu
ms.date: 05/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: b697583f2ebf9950ad805d4f415dafb2c891de8052d4a47563b048059475030f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745334"
---
# <a name="inventory-lookup-operation-in-pos"></a>Operazione di ricerca in magazzino nel POS

[!include [banner](includes/banner.md)]

Questo argomento descrive come utilizzare l'operazione di ricerca in magazzino nel POS di Dynamics 365 Commerce per visualizzare la disponibilità delle scorte dei prodotti in punti vendita e magazzini.

Una visualizzazione accurata delle scorte in un'organizzazione consente alle filiali di fornire un servizio clienti tempestivo ed efficace. Il momento più importante è quello in cui un cliente è pronto a prendere una decisione d'acquisto. È importante che i cassieri di un punto vendita al dettaglio abbiano a portata di mano informazioni sulle scorte in tempo reale o near real-time, in modo da poter promettere in modo preciso la consegna e il ritiro dei prodotti.

L'operazione di ricerca in magazzino nel POS di Commerce aiuta i rivenditori a raggiungere l'eccellenza operativa e a ottenere informazioni dettagliate collegando i punti vendita con Commerce Headquarters. Questa funzionalità fornisce una visualizzazione della disponibilità delle scorte dei prodotti in punti vendita e magazzini. Consente inoltre ai rivenditori di incrementare l'efficienza e ridurre i costi migliorando la pianificazione delle scorte in tempo reale.

Quando l'operazione di ricerca in magazzino viene avviata dall'applicazione POS, il cassiere POS utilizza la tastiera numerica per immettere un numero di prodotto ed effettuare una query sulle informazioni delle relative scorte. Se il prodotto immesso presenta delle varianti, il cassiere può facoltativamente selezionare dimensioni o altri valori per controllare le informazioni sulle scorte di una specifica variante del prodotto.

## <a name="inventory-lookup-list-view-for-individual-products"></a>Visualizzazione elenco della ricerca in magazzino per singoli prodotti

Per un singolo prodotto, l'operazione di ricerca in magazzino fornisce una visualizzazione elenco della ricerca in magazzino che mostra le seguenti informazioni sui prodotti per un elenco di ubicazioni:

- **Scorte** - Si riferisce alla quantità "fisica disponibile" di un prodotto.
- **Prenotata** - Si riferisce alla quantità "fisica prenotata" recuperata da Headquarters.
- **Prenotata** - Si riferisce alla quantità "ordinata in totale" recuperata da Headquarters.
- **Unità** - Si riferisce all'unità di misura del magazzino configurata in Headquarters.

La visualizzazione elenco delle ubicazioni include tutti i punti vendita e i magazzini configurati nei gruppi di evasione a cui è collegato il punto vendita corrente, come mostrato nell'immagine di esempio seguente.

![Visualizzazione elenco dell'operazione di ricerca in magazzino.](media/inventory-lookup-list-view.png)

> [!NOTE]
> Assicurarsi che il negozio sia incluso nei gruppi di evasione ordini associati.

Le seguenti azioni sono disponibili nella barra delle app del POS:

- **Ordina** - Questa azione consente all'utente del POS di ordinare i dati nella visualizzazione elenco in base a vari criteri. L'ordinamento basato sull'ubicazione è l'opzione predefinita. 
  - **Georilevazione** (dall'ubicazione più vicina a quella più lontana, rispetto al punto vendita attuale)
  - **Nome** (in ordine crescente o decrescente)
  - **Numero punto vendita** (in ordine crescente o decrescente)
  - **Scorte** (in ordine decrescente)
  - **Scorte** (in ordine decrescente)
  - **Ordinate** (in ordine decrescente)
- **Filtro** - Questa azione consente all'utente del POS di visualizzare i dati filtrati per una specifica ubicazione.
- **Mostra disponibilità punto vendita** - Questa azione consente all'utente del POS di visualizzare le quantità available-to-promise (ATP) per un prodotto nel punto vendita selezionato.
- **Mostra ubicazione punto vendita** - Questa azione apre una pagina distinta per mostrare la visualizzazione della mappa, l'indirizzo e gli orari del punto vendita selezionato.
- **Preleva al punto vendita** - Questa azione crea un ordine cliente per il prodotto che verrà prelevata presso il punto vendita selezionato e reindirizza l'utente alla schermata della transazione.
- **Spedizione prodotto** - Questa azione crea un ordine cliente per il prodotto che verrà spedito al punto vendita selezionato e reindirizza l'utente alla schermata della transazione.
- **Visualizza tutte le varianti** - Per un prodotto con varianti, questa azione passa da una visualizzazione elenco a una visualizzazione matrice che mostra le informazioni sulle scorte per tutte le varianti del prodotto.
- **Aggiungi a transazione** - Questa azione aggiunge il prodotto al carrello e reindirizza l'utente alla schermata della transazione.

> [!NOTE]
> Per un ordinamento basato sull'ubicazione, la distanza tra un'ubicazione e il punto vendita corrente è determinata dalle coordinate (latitudine e longitudine) definite in Commerce Headquarters. Per un punto vendita, le informazioni sull'ubicazione sono definite nell'indirizzo principale dell'unità operativa associata al punto vendita. Per un magazzino non punto vendita, le informazioni sull'ubicazione sono definite nell'indirizzo del deposito. Se il punto vendita corrente non ha coordinate definite, l'opzione di ordinamento in base all'ubicazione visualizzerà il punto vendita corrente all'inizio dell'elenco e quindi ordinerà le altre ubicazioni in base al nome.

> [!NOTE]
> Le azioni **Mostra disponibilità punto vendita**, **Mostra ubicazione punto vendita**, **Preleva al punto vendita** e **Spedizione prodotto** non sono disponibili per le ubicazioni che non sono punti vendita.

## <a name="inventory-lookup-matrix-view-for-variants"></a>Visualizzazione matrice della ricerca in magazzino per le varianti

Per un prodotto master con varianti, l'operazione di ricerca in magazzino fornisce anche una visualizzazione matrice basata sulle dimensioni che mostra le informazioni sulla disponibilità delle scorte per tutte le varianti del prodotto master in un'ubicazione selezionata. Per impostazione predefinita, la visualizzazione matrice mostra i dati del punto vendita corrente. Puoi usare l'azione **Punto vendita** nella barra delle app per cercare informazioni sulle scorte presso altri punti vendita configurati nei gruppi di evasione a cui è collegato il punto vendita corrente.

La seguente immagine di esempio mostra la visualizzazione matrice della ricerca in magazzino nel POS.

![Visualizzazione matrice dell'operazione di ricerca in magazzino.](media/inventory-lookup-matrix-view.png)

Nella visualizzazione a matrice, ogni cella rappresenta una singola variante e mostra le scorte disponibili (fisiche disponibili) nell'angolo in basso a destra, nonché le scorte **prenotate** (fisiche prenotate) e **ordinate** (ordinate in totale) nell'angolo in alto a sinistra. Nella tabella seguente viene illustrato il significato dei vari valori relativi alla disponibilità delle scorte.

| Valore disponibilità                            | descrizione |
|------------------------------------------|-------------|
| Valore numerico maggiore di 0 (zero) | Una variante è stata rilasciata nell'ubicazione selezionata ed è possibile eseguire ulteriori azioni nella cella. |
| **0** (zero)                             | Una variante è stata rilasciata nell'ubicazione selezionata, ma l'articolo non è disponibile presso l'ubicazione selezionata. Puoi eseguire operazioni aggiuntive nella cella. |
| **n/d** o cella non attiva              | Una variante non è stata rilasciata nell'ubicazione selezionata e non è possibile eseguire ulteriori azioni nella cella. |

L'ordine di visualizzazione dei valori delle dimensioni nella visualizzazione matrice si basa sulla configurazione dell'ordine di visualizzazione delle dimensioni in Commerce Headquarters. Puoi modificare la configurazione dell'ordine di visualizzazione delle dimensioni selezionando una nuova dimensione da utilizzare. 

Per ogni cella della visualizzazione matrice sono disponibili le seguenti azioni:

- **Vendi adesso** - Questa azione aggiunge la variante selezionata al carrello e reindirizza l'utente alla schermata della transazione.
- **Preleva al punto vendita** - Questa azione crea un ordine cliente per la variante selezionata che verrà prelevata presso il punto vendita selezionato e reindirizza l'utente alla schermata della transazione.
- **Spedizione prodotto** - Questa azione crea un ordine cliente per la variante selezionata che verrà spedita al punto vendita selezionato e reindirizza l'utente alla schermata della transazione.
- **Disponibilità** - Questa azione visualizza una pagina separata che mostra le quantità ATP per la variante selezionata nel punto vendita selezionato.
- **Mostra tutte le ubicazioni** - Questa azione mostra la visualizzazione elenco della disponibilità delle scorte standard con le informazioni sulle scorte per la variante selezionata.
- **Visualizza dettagli prodotto** - Questa azione reindirizza l'utente alla pagina dei dettagli del prodotto della variante selezionata.

## <a name="access-inventory-lookup-from-other-pages-in-pos"></a>Accedere alla ricerca in magazzino da altre pagine nel POS

Gli utenti POS possono accedere all'operazione di ricerca in magazzino da altre pagine nel POS.

La seguente immagine di esempio mostra i risultati della ricerca in magazzino da una pagina dei dettagli del prodotto nel POS.

![Ricerca in magazzino dalla pagina dei dettagli del prodotto.](media/inventory-lookup-from-product-details-page.png)

Nella pagina dei dettagli del prodotto di un prodotto master, puoi utilizzare l'azione **Visualizza tutte le varianti** nella barra delle app per generare la visualizzazione matrice della ricerca in magazzino che mostra le informazioni sulla disponibilità delle scorte per il punto vendita corrente per tutte le varianti di un prodotto. Per un singolo prodotto, la pagina dei dettagli del prodotto visualizza il valore delle scorte disponibili (fisiche disponibili) di quel prodotto per il punto vendita corrente. Inoltre, puoi selezionare il collegamento **Scorte altri punti vendita** per avviare l'operazione di ricerca in magazzino per verificare la disponibilità delle scorte di un prodotto in altri punti vendita o magazzini.

> [!NOTE]
> L'azione **Visualizza tutte le varianti** nella pagina dei dettagli del prodotto è disponibile solo per i prodotti master con varianti. Non è disponibile per specifici prodotti o kit.

Puoi configurare l'operazione di ricerca in magazzino di modo che appaia come collegamento nella griglia dei pulsanti nella schermata della transazione POS. Dopo la configurazione, quando l'utente seleziona una riga del carrello e quindi seleziona il pulsante **Ricerca in magazzino**, verrà visualizzata la visualizzazione elenco della ricerca in magazzino per il prodotto selezionato. Per ulteriori informazioni su come configurare le griglie di pulsanti utilizzando lo strumento di progettazione del layout dello schermo POS, vedi [Configurazioni visive dell'interfaccia utente POS](pos-screen-layouts.md).

## <a name="inventory-lookup-with-channel-side-calculation"></a>Ricerca in magazzino con calcolo sul lato canale

In Commerce versione 10.0.9 e versioni precedenti, il valore **Fisico disponibile** nell'operazione di ricerca in magazzino viene recuperato da Commerce Headquarters tramite una chiamata di servizio in tempo reale. In Commerce 10.0.10 e versioni successive, puoi configurare l'operazione di ricerca in magazzino del POS per utilizzare il calcolo sul lato canale nel server Commerce allo scopo di determinare il valore fisico disponibile, che può fornire una stima più affidabile e più accurata delle scorte disponibili prendendo in considerazione i dati transazionali non ancora sincronizzati con Headquarters. Per ulteriori informazioni sul calcolo delle scorte sul lato canale e sulla relativa configurazione del POS in Headquarters, vedi [Calcolare la disponibilità scorte per i canali di vendita al dettaglio](calculated-inventory-retail-channels.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurazioni visive dell'interfaccia utente POS](pos-screen-layouts.md)

[Calcolare la disponibilità scorte per i canali di vendita al dettaglio](calculated-inventory-retail-channels.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
