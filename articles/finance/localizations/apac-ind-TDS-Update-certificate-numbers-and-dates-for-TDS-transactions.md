---
title: Aggiornare i numeri e le date dei certificati per transazioni TDS
description: In questo argomento viene illustrato come aggiornare i numeri e le date dei certificati recuperabili registrati per i conti fornitore, cliente e CoGe per l'imposta dedotta all'origine (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7f8b5713e8ce3f9e9c89b8b3bc6ea84fe1f0fa54
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724813"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a>Aggiornare i numeri e le date dei certificati per transazioni TDS

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come aggiornare i numeri e le date dei certificati recuperabili registrati per i conti fornitore, cliente e CoGe per l'imposta dedotta all'origine (TDS). Puoi visualizzare i certificati per le transazioni TDS nella pagina **Certificati recuperabili**. Puoi aggiornare i certificati utilizzando la pagina **Aggiorna certificati**.

Segui questi passaggi per aggiornare i numeri e le date dei certificati per transazioni TDS.

1. Seleziona **Imposta \> Dichiarazioni \> Ritenuta d'acconto \> Aggiorna certificato**.

    [![Pagina Aggiorna certificato.](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)

2. Nella pagina **Aggiorna certificato**, nella sezione **Seleziona**, nel campo **Tipo di imposta**, seleziona **TDS**.
3. Nel campo **Numero certificato** seleziona il numero di certificato TDS del cliente o del fornitore.

    > [!NOTE]
    > Il campo **Numero certificato** elenca solo i numeri di certificato TDS per i quali la casella di controllo **Chiuso** è deselezionata nella pagina **Certificati recuperabili**.

    Il campo **Data certificato** mostra la data del certificato. Il campo **Tipo di conto** Il campo mostra il tipo di conto per il quale viene ricevuto il numero di certificato TDS e il campo **Nome** mostra il nome del conto.

5. Nei campi **Data iniziale** e **Data finale**, seleziona le date finale e finale del periodo per cui visualizzare le transazioni TDS.
6. Seleziona **Mostra dati** per visualizzare le transazioni TDS registrate durante il periodo selezionato.

    Nella tabella **Panoramica**, la griglia nel riquadro superiore mostra le seguenti informazioni su ciascuna transazione TDS registrata per il fornitore o il cliente durante il periodo selezionato:

    - **Giustificativo** - Il numero di giustificativo della transazione TDS.
    - **Data** - La data della transazione TDS.
    - **Importo** - L'importo della fattura su cui è stata calcolata la TDS.
    - **Importo imposta** - L'importo della TDS calcolato per la transazione.

7. Per spostare specifiche transazioni TDS dalla griglia superiore a quella inferiore, seleziona le transazioni, quindi seleziona **Includi**. In alternativa, seleziona **Includi tutto** per spostare tutte le transazioni TDS dalla griglia superiore alla griglia inferiore.

    Per spostare specifiche transazioni TDS o tutte le transazioni TDS dalla griglia inferiore a quella superiore, utilizza il pulsante **Escludi** o **Escludi tutto**.

8. Seleziona **Aggiorna** per aggiornare i campi **Numero certificato** e **Data certificato** per le transazioni TDS nella griglia inferiore.
10. Vai a **Imposta \> Imposte indirette \> Ritenuta d'acconto \> Certificato recuperabile** e seleziona **Richiesta info** per visualizzare le righe di transazioni aggiornate che hanno nuovi numeri di certificato nella pagina **Transazioni certificato**.

    [![Pagina Transazioni certificato.](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)
