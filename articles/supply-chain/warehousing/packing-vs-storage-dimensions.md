---
title: Impostare dimensioni diverse per l'imballaggio e l'immagazzinamento
description: In questo articolo viene illustrato come specificare il processo (imballaggio, immagazzinamento o imballaggio nidificato) per cui viene utilizzata ciascuna dimensione specificata.
author: Mirzaab
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResPhysicalProductDimensions, WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8ebea86e5ea63ab4f5a844cd3d0936c0d65bbe2b
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220244"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a>Impostare dimensioni diverse per l'imballaggio e l'immagazzinamento

[!include [banner](../../includes/banner.md)]

Alcuni articoli sono imballati o sotccati in modo tale che potrebbe essere necessario tener traccia delle dimensioni fisiche in modo diverso per ciascuno dei diversi processi. La funzionalità *Dimensioni prodotto di imballaggio* consente di configurare uno o più tipi di dimensioni per ogni prodotto. Ogni tipo di dimensione fornisce una serie di misure fisiche (peso, larghezza, profondità e altezza) e stabilisce il processo in cui si applicano tali valori di misura fisica. Quando questa fnzionalità è abilitata, il sistema supporterà i seguenti tipi di dimensioni:

- *Immagazzinamento*: le dimensione di immagazzinamento vengono utilizzate insieme ai valori volumetrici di ubicazione per determinare il numero di articoli che possono essere immagazzinati in varie ubicazioni di magazzino.
- *Imballaggio*: le dimensioni dell'imballaggio vengono utilizzate durante la containerizzazione e il processo di imballaggio manuale per determinare quanti di ciascun articolo si adatteranno ai vari tipi di contenitore.
- *Imballaggio annidato*: le dimensioni di imballaggio nidificate vengono utilizzate quando il processo di imballaggio contiene più livelli.

Le dimensioni *Immagazzinamento* sono supportate anche quando la funzionalità *Dimensioni prodotto di immagazzinamento* non è abilitata. Puoi configurarle utilizzando la pagina **Dimensione fisica** in Supply Chain Management. Queste dimensioni vengono utilizzate da tutti i processi in cui le dimensioni di imballaggio e imballaggio nidificato non sono specificate.

Le dimensioni di *imballaggio* e *imballaggio annidato* vengono configurate utilizzando la pagina **Dimensioni fisiche del prodotto**, che viene aggiunta quando abiliti la funzionalità *Dimensioni prodotto di immagazzinamento*.
Questo articolo fornisce uno scenario che illustra come utilizzare questa funzionalità.

## <a name="turn-on-the-packaging-product-dimensions-feature"></a>Attivare la funzionalità delle dimensioni del prodotto di imballaggio

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Dimensioni prodotto di imballaggio*

## <a name="example-scenario"></a>Scenario di esempio

### <a name="set-up-the-scenario"></a>Impostare lo scenario

Prima di poter eseguire lo scenario di esempio, è necessario preparare il sistema come descritto in questa sezione.

#### <a name="enable-demo-data"></a>Abilitare i dati dimostrativi

Per elaborare lo scenario utilizzando i record e i valori demo specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard. È inoltre necessario selezionare la persona giuridica *USMF* prima di iniziare.

#### <a name="add-a-new-physical-dimension-to-a-product"></a>Aggiungere una nuova dimensione fisica a un prodotto

Aggiungi una nuova dimensione fisica per un prodotto procedendo come segue:

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Seleziona il prodotto con **Numero articolo** *A0001*.
1. Nel riquadro azioni, aprire **Gestione articoli** e, dal gruppo **Magazzino**, selezionare **Dimensioni fisiche del prodotto**.
1. Si apre la pagina **Dimensioni fisiche del prodotto**. Nel riquadro azioni selezionare **Nuovo** per aggiungere una nuova dimensione alla griglia con le impostazioni seguenti:
    - **Tipo di dimensione fisica** - *Imballaggio*
    - **Unità fisica** - *pz*
    - **Peso** - *4*
    - **Unità peso** - *kg*
    - **Profondità** - *3*
    - **Altezza** - *4*
    - **Larghezza** - *3*
    - **Lunghezza** - *cm*
    - **Unità di volume** - *cm3*

Il campo **Volume** viene calcolato automaticamente in base alle impostazioni **Profondità**, **Altezza** e **Larghezza**.

#### <a name="create-a-new-container-type"></a>Creare un nuovo tipo di contenitore

Vai a **Gestione magazzino \> Imposta \> Contenitori \> Tipi di contenitori** e crea un nuovo record con le seguenti impostazioni:

- **Codice tipo di contenitore** - *Scatola piccola*
- **Descrizione** - *Scatola piccola*
- **Peso netto massimo** - *50*
- **Volume** - *144*
- **Lunghezza** - *6*
- **Larghezza** - *6*
- **Altezza** - *4*

#### <a name="create-a-container-group"></a>Creare un gruppo di contenitori

Vai a **Gestione magazzino \> Imposta \> Contenitori \> Gruppi di contenitori** e crea un nuovo record con le seguenti impostazioni:

- **ID gruppo di contenitori** - *Scatola piccola*
- **Descrizione** - *Scatola piccola*

Aggiungere una nuova riga alla sezione **Dettagli**. Impostare **Tipo di contenitore** su *Scatola piccola*.

#### <a name="set-up-a-container-build-template"></a>Impostare un modello di versione del contenitore

Andare a **Gestione magazzino \> Imposta \> Contenitori \> Modelli di build contenitore** se selezionare **Scatole**. Modificare **ID gruppo di contenitori** su *Scatola piccola*.

### <a name="run-the-scenario"></a>Eseguire lo scenario

Dopo aver preparato il sistema come descritto nella sezione precedente, sei pronto per eseguire lo scenario come descritto nella sezione successiva.

#### <a name="create-a-sales-order-and-create-a-shipment"></a>Creare un ordine cliente e una spedizione

In questo processo creerai una spedizione basata sulle dimensioni di *imballaggio* dell'articolo, per le quali l'altezza è inferiore a 3.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-001*
    - **Magazzino:** *63*

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.
1. Viene aperto il nuovo ordine cliente. Dovrebbe includere una nuova riga vuota nella griglia della Scheda dettaglio **Righe ordine cliente**. Su questa riga, impostare i seguenti valori:

    - **Numero articolo:** *A0001*
    - **Quantità:** *5*

1. Nella scheda dettaglio **Righe ordine cliente**, selezionare **Scorte \> Prenotazione**.
1. Nella pagina **Prenotazione**, quindi nel riquadro azioni, selezionare **Prenota lotto** per prenotare le scorte.
1. Chiudere la pagina.
1. Nel riquadro azioni, aprire la scheda **Magazzino** e selezionare **Rilascia in magazzino** per creare lavoro per il magazzino.
1. Nella Scheda dettaglio **Righe ordine cliente**, selezionare **Magazzino \> Dettagli spedizione**.
1. Nel riquadro azioni, aprire la scheda **Trasporto** e selezionare **Visualizza contenitori**. Confermare che l'articolo è stato containerizzato nei due contenitori *Scatola piccola*.

#### <a name="place-an-item-into-storage"></a>Posizionare un articolo in magazzino

1. Aprire il dispositivo mobile, accedere al magazzino 63 e passare a **Inventario \> Rettifica in entrata**.
1. Immettere **Ubicazione** = *SHORT-01*. Creare una nuova targa con **Articolo** = *A0001* e **Quantità** = *1 pz*.
1. Selezionare **OK**. Riceverai l'errore "Ubicazione SHORT-01 non riuscita perché l'articolo A0001 non si adatta alle dimensioni specificate dell'ubicazione." Questo perché le dimensioni del tipo di *Immagazzinamento* del prodotto sono maggiori delle dimensioni specificate nel profilo di ubicazione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]