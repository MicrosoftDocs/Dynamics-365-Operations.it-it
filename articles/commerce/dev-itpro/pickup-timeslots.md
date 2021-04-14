---
title: Creare e aggiornare le fasce orarie per il ritiro del cliente
description: In questo argomento viene descritto come creare, configurare e aggiornare le fasce orarie per il ritiro del cliente in Commerce headquarters.
author: anupamar-ms
ms.date: 01/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.15 update
ms.openlocfilehash: c3da7474f9a61e97ee11688a18cb91a5ad1ccb5c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791167"
---
# <a name="create-and-update-time-slots-for-customer-pickup"></a>Creare e aggiornare le fasce orarie per il ritiro del cliente

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come creare, configurare e aggiornare le fasce orarie per il ritiro del cliente in Commerce headquarters.

La funzione fascia oraria offre ai rivenditori un modo per definire una fascia oraria per gli articoli per cui è attivata la modalità di consegna ritiro del cliente. Le fasce orarie consentono ai rivenditori di definire i giorni e gli orari in cui gli ordini possono essere ritirati in un negozio. I rivenditori possono anche definire il numero di ordini che possono essere ritirati durante un determinato periodo. In questo modo, i rivenditori possono limitare il numero di ordini che possono essere ritirati in un determinato giorno e in un determinato momento. Il risultato è un'esperienza di migliore qualità per i clienti.

> [!NOTE]
> La funzionalità delle fasce orarie è disponibile in Microsoft Dynamics 365 Commerce versione 10.0.15 e successive.

La figura seguente mostra un esempio di selezione della fascia oraria durante il checkout e-commerce.

![Esempio di selezione della fascia oraria durante il checkout e-commerce](../dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="time-slot-properties"></a>Proprietà delle fasce orarie

Una fascia oraria è un intervallo specifico in cui un cliente può scegliere di ritirare un ordine da un negozio o luogo specifico. La funzione di gestione delle fasce orarie è disponibile solo quando la modalità di consegna ritiro del cliente è configurata in Dynamics 365 Commerce.

Una fascia oraria viene definita utilizzando le seguenti proprietà:

- **Modalità di spedizione** - Specificare la modalità di consegna ritiro a cui si applica la fascia oraria.
- **Numero minimo di giorni** e **Numero massimo di giorni** - Specificare la prima e l'ultima data che possono essere selezionate per il ritiro rispetto alla data in cui viene effettuato l'ordine. 

    La proprietà **Numero minimo di giorni** garantisce che il rivenditore abbia tempo sufficiente per elaborare l'ordine prima che sia pronto per il ritiro. La proprietà **Numero massimo di giorni** garantisce che l'utente non possa selezionare una data troppo lontana nel futuro. Ad esempio, se il valore minimo è impostato su **1** e viene effettuato un ordine il 20 settembre, il primo giorno in cui l'ordine sarà disponibile per il ritiro è il giorno idoneo successivo (21 settembre). Allo stesso modo, impostando un valore massimo, è possibile definire il numero massimo di giorni in cui un ordine può essere ritirato. Quando vengono definiti i valori minimo e massimo, gli utenti del sito possono vedere e selezionare solo un insieme specifico di giorni durante la loro esperienza di pagamento.

    È possibile impostare il valore minimo su un valore decimale inferiore a 1. Ad esempio, se il ritiro è disponibile quattro ore dopo aver effettuato un ordine, imposta il valore minimo su **0,17** (= 4 ÷ 24, arrotondato per eccesso a due cifre decimali). Tuttavia, se si imposta il valore minimo su un valore decimale maggiore di 1, viene sempre arrotondato in eccesso al numero intero più vicino. Ad esempio, un valore di **1,2** verrà arrotondato a **2**. Analogamente, se si imposta il valore massimo su un valore decimale, viene sempre arrotondato in eccesso al numero intero più vicino. 

- **Data di inizio** e **Data di fine** - Specificare le date di inizio e di fine della fascia oraria. Ogni voce di fascia oraria ha una data di inizio e una data di fine. Pertanto si dispone della flessibilità di aggiungere diverse fasce orarie durante l'anno (ad esempio, ritiri durante le ore di vacanza). Se l'inizio e le date di una fascia oraria vengono modificate dopo che è stato effettuato un ordine, le modifiche non verranno applicate a tale ordine. Quando si definiscono le date di inizio e di fine, è necessario considerare le date di chiusura del negozio (ad esempio, il giorno di Natale) e assicurarsi che non siano definiti fasce orarie per quei giorni.
- **Orario di ritiro attivo** - Specifica il periodo in cui è consentito il ritiro. Ad esempio, l'orario di ritiro potrebbe essere tra le 14.00 e le 17.00 ogni giorno. Questa proprietà consente agli orari di ritiro di essere indipendenti dagli orari di negozio. Pertanto, il rivenditore può configurare orari di ritiro che soddisfino i suoi requisiti aziendali specifici. Quando si definiscono gli orari di ritiro attivi, è necessario considerare gli orari del negozio e assicurarsi che gli orari di ritiro non siano definiti per gli orari in cui il negozio è chiuso.

    > [!NOTE]
    > Gli orari per il ritiro in negozio devono essere definiti nel fuso orario del negozio appropriato.

- **Intervallo fascia oraria** - Specificare la durata che può essere assegnata a ciascuna fascia oraria. Ad esempio, la durata di ogni fascia oraria potrebbe essere in incrementi di 15 minuti, 30 minuti o un'ora. Se il valore della fascia oraria è 0, la fascia oraria è disponibile per l'intera durata tra l'ora di inizio e l'ora di fine.
- **Fasce per intervallo** - Specificare il numero di clienti o ordini che possono essere serviti per il ritiro durante ogni intervallo di fascia oraria. Ad esempio, inserire **1**, **2**, **3** o qualsiasi altro numero intero.
- **Giorni attivi** - Specificare i giorni della settimana in cui le fasce orarie di ritiro sono attive. Questa proprietà consente al rivenditore di definire i giorni in cui desidera supportare gli ordini di ritiro.
- **Canali di vendita al dettaglio** - Specificare i canali di vendita al dettaglio. Ogni fascia oraria può essere associata a uno o più punti vendita. A seconda dell'orario di apertura di ogni negozio, è possibile creare una o più voci di fascia oraria e associarle a un canale. 

<!-- ![HQ Timeslot overview](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

È possibile configurare un solo modello di fascia oraria per canale. Questi canali includono negozi fisici, servizi clienti, dispositivi mobili e siti di e-commerce.

## <a name="configure-the-time-slot-feature-in-commerce-headquarters"></a>Configurare la funzione di fascia oraria in Commerce headquarters

Per ciascuna modalità di consegna ritiro in Commerce headquarters devono essere definite delle fasce orarie in modo che i canali del punto vendita (POS) e dell'e-commerce possano consultarle.

- Un solo modello di fascia oraria può essere associato a ogni punto vendita o canale.
- Ogni fascia oraria creata deve essere univoca per ciascuna modalità di consegna in ogni modello.
- Dopo aver configurato la funzione della fascia oraria, il calendario della fascia oraria sarà disponibile per i negozi o gruppi di negozi selezionati. Sarà anche visibile presso il POS, per riferimento.

Per configurare la funzione di fascia oraria in Commerce headquarters, seguire questi passaggi.

1. Andare a **Commerce** \> **Configurazione canale** \> **Fascia oraria per ritiro in negozio**.
1. Selezionare **Nuovo** per creare un nuovo modello di fascia oraria. Per utilizzare un modello esistente, selezionare il modello nel riquadro sinistro.
1. Immettere valori nei campi **ID fascia oraria** e **Descrizione**.
1. Nella scheda dettaglio **Ritiro ordine - Impostazioni ora** selezionare **Aggiungi**.
1. Nella finestra di dialogo **Ritiro ordine - Impostazioni ora** definire l'intervallo di date, la modalità di consegna, le ore di consegna attive, i giorni attivi, l'intervallo di fascia oraria, le fasce orarie per intervallo e altre impostazioni.

    Se le fasce orarie saranno statiche per il prossimo futuro, imposta il campo **Data di fine** su **Mai**.

    > [!NOTE]
    > È possibile creare più modelli, ma solo un modello può essere associato a un singolo canale o negozio.

    ![Finestra di dialogo Ritiro ordine - Impostazioni ora](../dev-itpro/media/Curbside_timeslot_Settings_Page.PNG)

1. Al termine, selezionare **OK**.
1. Se le fasce orarie di un giorno variano, creare voci aggiuntive nella scheda dettaglio **Ritiro ordine - Impostazioni ora** per garantire che le date e le ore non si sovrappongano.
1. Nella scheda dettaglio **Canali di vendita al dettaglio** selezionare **Aggiungi** per associare il modello di fascia oraria ai negozi o ai canali in cui verrà utilizzato.
1. Nella finestra di dialogo **Scegli nodi organizzazione**, usare i tasti con le frecce per selezionare (o deselezionare) i punti vendita, le aree geografiche e le organizzazioni a cui il modello deve essere associato.

    <!-- ![HQ Timeslot overview](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

1. Al termine, selezionare **OK**.
1. Nella pagina **Programmazione distribuzione**, eseguire i processi **1135** e **1070** per sincronizzare i dati ai canali.

## <a name="time-slot-selection-for-pos-orders"></a>Selezione della fascia oraria per gli ordini POS

Nel POS, quando viene identificato un ordine o una riga ordine per il ritiro, il cassiere può selezionare il punto vendita o la posizione per il ritiro e una data e una fascia oraria. Se un cliente ha un ordine per un prelievo presso un altro punto vendita, il cassiere può selezionare le date in cui il prelievo sarà disponibile in quel punto vendita. La ricerca del punto vendita fornirà un riferimento alle date e agli orari del punto vendita.

La figura seguente mostra un esempio di selezione della fascia oraria per un ordine POS.

![Un esempio di selezione della fascia oraria per un ordine POS](../dev-itpro/media/Curbside_timeslot_POS.png)

## <a name="time-slot-selection-for-e-commerce-orders"></a>Selezione della fascia oraria per gli ordini e-commerce

Per informazioni su come rendere disponibile la selezione delle fasce orarie per gli ordini e-commerce, vedere [Modulo di informazioni sul ritiro](../pickup-info-module.md).

> [!NOTE]
> Gli utenti possono visualizzare o modificare le fasce orarie di ritiro sulla pagina di pagamento di un sito di Commerce solo se il modulo delle informazioni sul ritiro è stato aggiunto a quella pagina. Se la pagina di pagamento non include il modulo delle informazioni sul ritiro, gli ordini verranno effettuati senza consentire agli utenti di specificare o visualizzare le informazioni sulla fascia oraria.

La seguente illustrazione mostra un esempio di un ordine e-commerce in cui è stata selezionata una fascia oraria per il ritiro.

![Esempio di un ordine e-commerce in cui è stata selezionata una fascia oraria per il ritiro](../dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="time-slot-selection-for-call-center-orders"></a>Selezione della fascia oraria per gli ordini del servizio clienti

Nell'app del servizio clienti, gli agenti del servizio clienti possono selezionare il punto di ritiro o la posizione, nonché una data e un intervallo di tempo come evidenziato nella figura seguente.

![Esempio di un ordine del servizio clienti in cui è stata selezionata una fascia oraria per il ritiro](../dev-itpro/media/Curbside_timeslot_callcenter.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo di informazioni sul ritiro](../pickup-info-module.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]