---
title: Operazione di ricerca in magazzino nel POS
description: Questo articolo descrive come utilizzare l'operazione di ricerca in magazzino nel POS di Dynamics 365 Commerce per visualizzare la disponibilità delle scorte dei prodotti in punti vendita e magazzini.
author: boycezhu
ms.date: 08/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: fc8c7dad0a7cb66ba7d6c6f527be84cfe74dee52
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288327"
---
# <a name="inventory-lookup-operation-in-pos"></a>Operazione di ricerca in magazzino nel POS

[!include [banner](includes/banner.md)]

Questo articolo descrive come utilizzare l'operazione di ricerca in magazzino nel POS di Dynamics 365 Commerce per visualizzare la disponibilità delle scorte dei prodotti in punti vendita e magazzini.

Una visualizzazione accurata delle scorte in un'organizzazione consente alle filiali di fornire un servizio clienti tempestivo ed efficace. Il momento più importante è quello in cui un cliente è pronto a prendere una decisione d'acquisto. È importante che i cassieri di un punto vendita al dettaglio abbiano a portata di mano informazioni sulle scorte in tempo reale o near real-time, in modo da poter promettere in modo preciso la consegna e il ritiro dei prodotti.

L'operazione di ricerca in magazzino nel POS di Commerce aiuta i rivenditori a raggiungere l'eccellenza operativa e a ottenere informazioni dettagliate collegando i punti vendita con Commerce Headquarters. Questa funzionalità fornisce una visualizzazione della disponibilità delle scorte dei prodotti in punti vendita e magazzini. Consente inoltre ai rivenditori di incrementare l'efficienza e ridurre i costi migliorando la pianificazione delle scorte in tempo reale.

Quando l'operazione di ricerca in magazzino viene avviata dall'applicazione POS, il cassiere POS utilizza la tastiera numerica per immettere un numero di prodotto ed effettuare una query sulle informazioni delle relative scorte. Se il prodotto immesso presenta delle varianti, il cassiere può facoltativamente selezionare dimensioni o altri valori per controllare le informazioni sulle scorte di una specifica variante del prodotto.

## <a name="inventory-lookup-list-view-for-individual-products"></a>Visualizzazione elenco della ricerca in magazzino per singoli prodotti

Per un singolo prodotto, l'operazione di ricerca in magazzino fornisce una visualizzazione elenco della ricerca in magazzino che mostra le seguenti informazioni sui prodotti per un elenco di ubicazioni:

- **Inventario** - Si riferisce alla quantità "fisica disponibile" di un prodotto.
- **Riservato** - Si riferisce alla quantità "riservata fisica" recuperata dalla sede centrale.
- **Ordinato** - Si riferisce alla quantità "ordinata in totale" recuperata dalla sede centrale.
- **Unità** - Si riferisce all'unità di misura dell'inventario configurata nella sede centrale.

La visualizzazione elenco delle ubicazioni include tutti i punti vendita e i magazzini configurati nei gruppi di evasione a cui è collegato il punto vendita corrente, come mostrato nell'immagine di esempio seguente.

![Visualizzazione elenco dell'operazione di ricerca in magazzino.](media/inventory-lookup-list-view.png)

> [!NOTE]
> Assicurarsi che il negozio sia incluso nei gruppi di evasione ordini associati.

Le seguenti azioni sono disponibili nella barra delle app del POS:

- **Ordina** - Questa azione permette all'utente del POS di ordinare i dati nella vista elenco in base a vari criteri. L'ordinamento basato sull'ubicazione è l'opzione predefinita.

    - **Posizione geografica** (dalla posizione più vicina a quella più lontana, in base alla distanza dal negozio attuale)
    - **Nome** (in ordine crescente o decrescente)
    - **Numero punto vendita** (in ordine crescente o decrescente)
    - **Scorte** (in ordine decrescente)
    - **Scorte** (in ordine decrescente)
    - **Ordinate** (in ordine decrescente)

- **Filtro** - Questa azione permette all'utente del POS di visualizzare i dati filtrati per una posizione specifica.
- **Mostra la disponibilità del negozio** - Questa azione permette all'utente del POS di visualizzare le quantità disponibili alla promessa (ATP) per un prodotto nel negozio selezionato.
- **Mostra la posizione del negozio** - Questa azione apre una pagina separata per mostrare la vista della mappa, l'indirizzo e gli orari del negozio selezionato.
- **Ritiro in negozio** - Questa azione crea un ordine del cliente per il prodotto che sarà ritirato dal negozio selezionato, e reindirizza l'utente alla schermata della transazione.
- **Spedisci prodotto** - Questa azione crea un ordine del cliente per il prodotto che sarà spedito dal negozio selezionato, e reindirizza l'utente alla schermata della transazione.
- **Visualizza tutte le varianti** - Per un prodotto con varianti, questa azione passa da una vista elenco a una vista matrice che visualizza le informazioni di inventario per tutte le varianti del prodotto.
- **Aggiungi alla transazione** - Questa azione aggiunge il prodotto al carrello e reindirizza l'utente alla schermata della transazione.

> [!NOTE]
> L'ordinamento basato sulla posizione che è stato introdotto nella versione Commerce 10.0.17 mostra il negozio corrente in alto. Per altre località, la distanza tra la località e il negozio attuale è determinata dalle coordinate (latitudine e longitudine) che sono definite nella sede centrale di Commerce. Per un negozio, l'informazione sulla posizione è definita nell'indirizzo primario dell'unità operativa che è associata al negozio. Per un magazzino non punto vendita, le informazioni sull'ubicazione sono definite nell'indirizzo del deposito. Prima della versione 10.0.17, la vista elenco mostrava sempre il negozio corrente in alto e ordinava le altre posizioni in ordine alfabetico.
>
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

- **Vendi ora** - Questa azione aggiunge la variante selezionata al carrello e reindirizza l'utente alla schermata della transazione.
- **Ritira in negozio** - Questa azione crea un ordine del cliente per la variante selezionata che sarà ritirato dal negozio selezionato, e reindirizza l'utente alla schermata della transazione.
- **Spedisci prodotto** - Questa azione crea un ordine del cliente per la variante selezionata che sarà spedita dal negozio selezionato, e reindirizza l'utente alla schermata della transazione.
- **Disponibilità** - Questa azione porta l'utente ad una pagina separata che mostra le quantità ATP per la variante selezionata nel negozio selezionato.
- **Mostra tutte le località** - Questa azione passa alla vista standard dell'elenco di disponibilità dell'inventario che mostra le informazioni dell'inventario per la variante selezionata.
- **Visualizza i dettagli del prodotto** - Questa azione reindirizza l'utente alla pagina dei dettagli del prodotto (PDP) della variante selezionata.

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
