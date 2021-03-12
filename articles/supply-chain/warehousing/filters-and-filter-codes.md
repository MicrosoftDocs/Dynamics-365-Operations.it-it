---
title: Configurare i filtri di prodotto per le transazioni di magazzino
description: In questo argomento viene descritto come configurare i filtri prodotto e i codici filtro per classificare gli articoli di magazzino in un magazzino. È inoltre possibile utilizzare i filtri per specificare quali clienti possono richiedere un determinato articolo e per specificare gli articoli che possono essere acquistati da un fornitore specifico.
author: Mirzaab
manager: tfehr
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSFilters,WHSFilterGroupTable,EcoResProductDetailsExtended,WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 922ff818e069f41c139cc00db9161dc6e113888b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973737"
---
# <a name="configure-product-filters-for-warehouse-transactions"></a>Configurare i filtri di prodotto per le transazioni di magazzino

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come configurare i filtri prodotto e i codici filtro per classificare gli articoli di magazzino in un magazzino. È inoltre possibile utilizzare i filtri per specificare quali clienti possono richiedere un determinato articolo e per specificare gli articoli che possono essere acquistati da un fornitore specifico.

Inoltre, è possibile impostare e utilizzare i filtri di prodotto per organizzare automaticamente gli articoli di magazzino in un magazzino e per combinare gli articoli filtrati in gruppi di filtro. I filtri possono essere utilizzati per inserire gli articoli in categorie per i processi di gestione, acquisto e vendita. È consigliabile raggruppare gli articoli o separarli gli uni dagli altri quando il modo in cui vengono gestiti è basato sul peso o sulle restrizioni di manipolazione. Puoi anche specificare da quali clienti o fornitori è possibile acquistare o vendere un articolo.

## <a name="prerequisites"></a>Prerequisiti

Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.

| Prerequisito | Istruzioni |
|---|---|
| Prima di iniziare a configurare i prodotti nella pagina **Dettagli prodotto rilasciato**, è necessario attivare l'elaborazione del magazzino per il gruppo di dimensioni di immagazzinamento del prodotto. | Vai a **Gestione informazioni sul prodotto \> Configura \> Gruppi di dimensioni e varianti \> Gruppi di dimensioni di archiviazione** e seleziona o crea un gruppo di dimensioni di immagazzinamento in cui l'opzione **Usa processi di gestione magazzino** è impostata su *Sì*. |
| Se si utilizzeranno filtri cliente e/o filtri fornitore, è necessario abilitarne l'utilizzo nei parametri di gestione magazzino. | Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**. Nella scheda **Filtri prodotto**, imposta l'opzione **Abilita filtri cliente** e/o **Abilita filtri fornitore** su *Sì*. |

## <a name="set-up-product-filters"></a>Configurare filtri di prodotto

I filtri di prodotto offrono fino a 10 caratteristiche **Titolo del filtro** che corrispondono a valori di enumerazione (enum). Questi valori di enumerazione sono disponibili per la selezione quando si crea un filtro di prodotto. I valori di enumerazione da *Codice 1* a *Codice 10* sono definiti dal sistema e rappresentano una caratteristica o un attributo specifico di un articolo. Per esempio, *Codice 1* potrebbe rappresentare articoli che hanno una classificazione di materiali pericolosi. *Codice 2* potrebbe rappresentare articoli che solo i fornitori possono acquistare. I filtri di prodotto definiscono quindi lo specifico valore **Codice di filtro** associato a un valore **Titolo del filtro**.

1. Vai a **Gestione magazzino \> Imposta \> Filtri di prodotto \> Filtri di prodotto**.
1. Nel riquadro azioni seleziona **Nuovo** per aggiungere un filtro di prodotto alla griglia.
1. Seleziona un valore nel campo **Titolo filtro**.
1. Nel campo **Codice filtro** immetti un valore.

    ![Configurazione di un filtro di prodotto](media/Product_Filters10.png "Configurazione di un filtro di prodotto")

1. Nel campo **Descrizione** immetti un nome per il codice. Per esempio, *Codice 2* potrebbe rappresentare i fornitori. È quindi possibile creare un filtro di prodotto per un fornitore o un gruppo di fornitori specifico. Per ulteriori informazioni, vedere la sezione [Configurare i codici di filtro fornitore](#vendor-product-filters) più avanti in questo argomento.

    ![Set di filtri di prodotto](media/Product_Filters.png "Set di filtri di prodotto")

## <a name="set-up-product-filter-groups"></a>Configurare gruppi di filtri di prodotto

È possibile utilizzare gruppi di filtri per filtrare in gruppo i codici. Questa funzionalità è utile quando il gruppo viene utilizzato in una query in una direttiva ubicazione e si desidera cercare il gruppo anziché una serie di codici. Ogni gruppo di filtri è associato a un gruppo di articoli.

> [!IMPORTANT]
> Non tutti i gruppi di filtri di prodotto sono disponibili per codici di filtro superiori a *Codice 4* (vale a dire da *Codice 5* a *Codice 10*). Ad esempio, per i prodotti rilasciati, anche se verranno aggiunti tutti i codici di filtro di prodotto, il raggruppamento dei codici filtro non verrà aggiornato. Questo comportamento potrebbe essere aggiornato nelle versioni successive.

Per configurare i gruppi di filtri, effettuare le seguenti operazioni.

1. Vai a **Gestione magazzino \> Imposta \> Filtri di prodotto \> Gruppi di filtri di prodotto**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nei campi **Gruppo 1** e **Gruppo 2** immettere i nomi che saranno utilizzati per classificare gli articoli.
1. Nella Scheda dettaglio **Dettagli** seleziona **Nuova** per aggiungere una riga.
1. Nei campi **Data/ora di inizio** e **Data/ora di fine**, immettere le date di inizio e di fine per il gruppo di filtri.
1. Nel campo **Gruppo di articoli** selezionare il gruppo di articoli a cui applicare il filtro del prodotto.
1. Nei campi da **Codice 1** a **Codice 10** selezionare i codici filtro da includere nel gruppo, come richiesto.

    ![Gruppo di articoli](media/ProdFilterGroup.png "Gruppo di articoli")

> [!NOTE]
> Se viene visualizzato un messaggio di errore quando si chiude la pagina, è possibile che manchi l'impostazione di un codice. Nella pagina **Gruppi di articoli** è possibile rendere obbligatori i codici per un gruppo di articoli selezionando le caselle di controllo **Assegna il codice filtro 1 al gruppo di articoli**, **Assegna il codice filtro 2 al gruppo di articoli** e così via.

## <a name="set-up-filter-codes-on-item-groups"></a>Configurare i codici di filtro su gruppi di articoli

L'impostazione di codici filtro su un gruppo di articoli consente di rendere obbligatori i codici per i prodotti associati a tale gruppo di articoli.

Per impostare i codici filtro su gruppi di articoli, effettuare le operazioni seguenti.

1. Vai a **Gestione inventario \> Imposta \> Inventario \> Gruppi di articoli**.
1. Nel riquadro azioni seleziona **Nuovo** per creare un gruppo di articoli.
1. Nel campo **Gruppo di articoli** immetti un nome.
1. Nel campo **Nome** immettere una descrizione.
1. Nella Scheda dettaglio **Magazzino**, nella sezione **Filtro richiesto**, seleziona le caselle di controllo per i codici filtro che devono essere specificati per i prodotti associati al gruppo di articoli.

    Per aggiornare un prodotto rilasciato, apri la relativa pagina **Dettagli prodotto rilasciato**, quindi, nel riquadro azioni, seleziona **Modifica**. I filtri associati ai codici diventano quindi disponibili nella scheda Dettaglio **Magazzino**.

    ![Gruppi di articoli](media/ItemGroup10.png "Gruppi di articoli")

1. Nella sezione **Filtro del gruppo di articoli**, seleziona le caselle di controllo per i filtri che devono corrispondere affinché il gruppo di filtri sia il gruppo di filtri predefinito per un articolo.

    Ad esempio, se vengono selezionate le caselle di controllo **Utilizza codice filtro 1** e **Utilizza codice filtro 2**, entrambi i codici filtro 1 e 2 dell'articolo devono corrispondere all'impostazione del gruppo di filtri per il gruppo di articoli prima che il gruppo di filtri possa essere selezionato. Quando crei un nuovo articolo, il gruppo di filtri selezionato sarà il gruppo di filtri predefinito nei campi **Gruppo 1** e **Gruppo 2** della scheda Dettaglio **Magazzino** della pagina **Dettagli prodotto rilasciato**.

> [!IMPORTANT]
> I codici filtro di prodotto sono abilitati solo per gli articoli che utilizzano la gestione avanzata del magazzino.

## <a name="specify-filter-codes-for-released-products"></a>Specificare i codici filtro per i prodotti rilasciati

Seguire questi passaggi per specificare i codici filtro per prodotti rilasciati. Ad esempio, è possibile utilizzare codici filtro per raggruppare prodotti pericolosi acquistati da fornitori specifici.

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Nel riquadro azioni seleziona **Nuovo** per creare un prodotto.
1. Nella finestra di dialogo **Nuovo prodotto rilasciato**, immetti i dati richiesti per creare la base di un nuovo prodotto, quindi seleziona **OK**.

    I codici di filtro del prodotto non sono abilitati a meno che il gruppo di articoli allegato al prodotto non sia stato configurato per i codici di filtro.

    Per ulteriori informazioni, vedere [Creare un nuovo prodotto](../pim/tasks/create-new-product.md).

1. Nella scheda dettaglio **Magazzino**, nella sezione **Codici filtro prodotto** selezionare i codici filtro per i campi da **Codice 1** a **Codice 10**, come richiesto, per specificare i codici filtro per il prodotto.

## <a name="set-up-generally-available-items"></a>Configurare articoli generalmente disponibili

È possibile rendere alcuni articoli di magazzino specifici disponibili solo per clienti o fornitori o per entrambi.

> [!NOTE]
> I filtri cliente e fornitore non si applicano a qualsiasi articolo configurato come generalmente disponibile.

Per impostare articoli generalmente disponibili, effettuare le seguenti operazioni.

1. Vai a **Gestione magazzino \> Imposta \> Filtri di prodotto \> Prodotti generalmente disponibili**.
1. Nel riquadro azioni seleziona **Nuovo** per creare un record.
1. Nel campo **Cliente o fornitore**, seleziona *Cliente*, *Fornitore* o *Tutti* per rendere gli articoli disponibili per clienti, fornitori o entrambi.
1. Nel campo **Data/ora di inizio** immetti la data e l'ora in cui l'articolo sarà disponibile.
1. Nel campo **Gruppo di articoli**, seleziona un gruppo di articoli.
1. Nei campi da **Codice 1** a **Codice 10**, seleziona i codici filtro per limitare gli articoli generalmente disponibili.

    Quando si seleziona un gruppo di articoli, si imposta il gruppo in modo che sia generalmente disponibile. Selezionando i codici filtro in questi campi, si limitano gli articoli che sono disponibili.

## <a name="set-up-customer-product-filters"></a>Configurare filtri di prodotto del cliente

Puoi utilizzare questa procedura facoltativa per specificare gli articoli che devono essere disponibili per un cliente oltre agli articoli che vengono resi disponibili mediante l'impostazione di filtri nella pagina **Articoli generalmente disponibili**. È possibile impostare più filtri per un singolo cliente.

Per impostare i codici filtro per un cliente, effettuare le seguenti operazioni.

1. Vai a **Vendite e marketing \> Clienti \> Tutti i clienti**.
1. Seleziona un cliente.
1. Nel riquadro azioni, nella scheda **Cliente**, nel gruppo **Imposta**, seleziona **Filtri di prodotto**.
1. Nella pagina **Codici filtri di prodotto**, nel riquadro azioni, seleziona **Nuovo**.
1. Nei campi **Data/ora di inizio** e **Data/ora di fine**, immettere le date di inizio e di fine per il gruppo di articoli selezionato.
1. Nel campo **Gruppo di articoli**, seleziona un gruppo di articoli.
1. Nei campi da **Codice 1** a **Codice 10** selezionare i codici filtro da utilizzare come criteri per limitare gli articoli disponibili per i clienti nel gruppo di articoli selezionato. È necessario effettuare una selezione per ogni codice filtro impostato per il gruppo di articoli.

## <a name="set-up-vendor-product-filters"></a><a name="vendor-product-filters"></a>Configurare filtri di prodotto del fornitore

Puoi utilizzare questa procedura facoltativa per specificare gli articoli che devono essere disponibili per un fornitore oltre agli articoli che vengono resi disponibili mediante l'impostazione di filtri nella pagina **Articoli generalmente disponibili**. È possibile impostare più filtri per un singolo fornitore.

Per impostare i codici filtro per un fornitore, effettuare le seguenti operazioni.

1. Andare ad **Approvvigionamento \> Fornitori \> Tutti i fornitori**.
1. Selezionare un fornitore.
1. Nel riquadro azioni, nella scheda **Fornitore**, nel gruppo **Imposta**, seleziona **Filtri di prodotto**.
1. Nella pagina **Codici filtri**, nel riquadro azioni, seleziona **Nuovo**.
1. Nei campi **Data/ora di inizio** e **Data/ora di fine**, immettere le date di inizio e di fine per il gruppo di articoli selezionato.
1. Nel campo **Gruppo di articoli**, seleziona un gruppo di articoli.
1. Nei campi da **Codice 1** a **Codice 10** selezionare i codici filtro da utilizzare come criteri per limitare gli articoli disponibili per i fornitori nel gruppo di articoli selezionato. È necessario effettuare una selezione per ogni codice filtro impostato per il gruppo di articoli.

> [!NOTE]
> L'impostazione dei filtri dei prodotti del fornitore si applica ai prodotti rilasciati in cui i processi di gestione del magazzino sono abilitati per il gruppo di dimensioni di immagazzinamento associato. I codici filtro vengono utilizzati per determinare se il sistema consentirà agli utenti di acquistare un determinato articolo da un determinato fornitore quando creano righe ordine di acquisto. Microsoft Dynamics 365 Supply Chain Management prevede due metodi per gestire l'approvazione del fornitore. Se esistono uno o più prodotti rilasciati in cui il campo **Metodo di controllo fornitore approvato** è impostato su *Solo avvertimento* o *Non autorizzato*, entrambi i metodi di approvazione del fornitore potrebbero essere abilitati per tali articoli. Questa situazione potrebbe causare problemi quando gli utenti creano righe ordine fornitore.

## <a name="see-also"></a>Vedere anche

[Per ulteriori informazioni, vedere il post del blog WMS-Warehouse Filter Codes](http://blog.dynamics-for-operations.com/2017/09/26/wms-warehouse-filter-codes/)
