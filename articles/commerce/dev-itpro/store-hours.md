---
title: Creare e aggiornare gli orari del punto vendita
description: In questo argomento viene descritto come creare e aggiornare gli orari del punto vendita in Commerce Headquarters.
author: josaw1
manager: AnnBe
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.openlocfilehash: 00c532dfa9ceed2cda6652496d874cb82785dc7b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230642"
---
# <a name="create-and-update-store-hours"></a>Creare e aggiornare gli orari del punto vendita

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a>Panoramica

I rivenditori possono creare e gestire gli orari di differenti punti vendita in tutte le aree geografiche da un'unica posizione. Gli orari dei punti vendita possono quindi essere visualizzati nei terminali POS. In questo modo, i cassieri possono condividere tali orari con i clienti e fornire informazioni utili a quelli interessati a fare acquisti in altri punti vendita. Gli orari del punto vendita possono essere stampati sulle ricevute, nel caso in cui i clienti intendano ritornare al punto vendita in seguito.

Molteplici orari possono essere configurati in differenti canali. Questi canali includono negozi fisici, servizi clienti, dispositivi mobili e siti di e-commerce.

Se un cliente ha un ordine per un prelievo presso un altro punto vendita, il cassiere può selezionare le date in cui il prelievo sarà disponibile in quel punto vendita. La ricerca del punto vendita fornirà un riferimento alle date e agli orari del punto vendita. Il cassiere può selezionare una data e un ubicazione nonché stampare una ricevuta di prelievo che include gli orari del punto vendita.

Questa funzionalità è disponibile in Microsoft Dynamics 365 Retail versioni 8.1.2 e successive.

## <a name="configure-store-hours"></a>Configurare gli orari del punto vendita

Attenersi a questa procedura per configurare gli orari del punto vendita.

1. Vai a **Retail e Commerce** \> **Impostazione canale** \> **Orario punto vendita**.
2. Selezionare **Nuovo** per creare un nuovo modello di orari. Per utilizzare un modello esistente, selezionare il modello nel riquadro sinistro.
3. Nella finestra di dialogo **Aggiungi intervallo**, definire l'intervallo di date, gli orari del punto vendita e tutte le festività necessarie.

    - Se gli orari del punto vendita non cambiano, selezionare **Senza fine** nel campo **Data di fine**.
    - Se gli orari del punto vendita si riferiscono a un mese, una settimana, o un giorno specifico, impostare le date appropriate nei campi **Data di fine** e **Data di inizio**.

    > [!NOTE]
    > È possibile creare più modelli con date di inizio e di fine che si sovrappongono. Di conseguenza, è ad esempio possibile definire gli orari dei punti vendita con fusi orari differenti.

    ![Finestra di dialogo Aggiungi intervallo](../dev-itpro/media/Storehours1.png "Finestra di dialogo Aggiungi intervallo")

4. Associare il modello di orari ai punti vendita in cui verrà utilizzato. Nella finestra di dialogo **Scegli nodi organizzazione**, selezionare i punti vendita, le aree geografiche e le organizzazioni a cui il modello deve essere associato.

    - Un solo modello di orari può essere associato a ogni punto vendita.
    - Utilizzare i pulsanti freccia per selezionare punti vendita, aree geoagrafiche o organizzazioni. Il calendario sarà disponibile nei punti vendita o nei gruppi di punti vendita e sarà visibile nel POS come riferimento.

    ![Finestra di dialogo Scegli nodi organizzazione](../dev-itpro/media/Storehours2.png "Finestra di dialogo Scegli nodi organizzazione")

5. Nella pagina **Programmazione della distribuzione**, eseguire i processi **1070** e **1090** per rendere disponibili gli orari del punto vendita nel POS.

## <a name="add-store-hours-to-printed-receipts"></a>Aggiungere gli orari del punto vendita sulle ricevute stampate

Seguire questi passaggi per aggiungere gli orari del punto vendita sulle ricevute POS stampate.

1. Aprire Designer ricevute.
2. Selezionare **Piè di pagina** nell'angolo in basso a sinistra.
3. Trascinare l'elemento **Orario punto vendita** dal riquadro sinistro sul piè di pagina nella parte inferiore del modello di ricevuta.
4. È possibile modificare le etichette predefinite nell'elemento **Orario punto vendita** come necessario.
5. Salvare la ricevuta e chiudere Designer ricevute.
6. Nella pagina **Programmazione della distribuzione**, eseguire i processi **1070** e **1090**.
7. Accedere al POS.
8. Completare una vendita e selezionare la stampa di una ricevuta.

Le ricevute POS ora includono gli orari del punto vendita. Se nel modello sono state incluse le festività, saranno visualizzate sulla ricevuta.

![Esempio di ricevuta](../dev-itpro/media/Storehours3.png "Esempio di ricevuta")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]