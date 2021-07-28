---
title: Registrare numeri di certificati recuperabili TDS
description: In questo argomento viene illustrato come utilizzare la pagina Certificati recuperabili per registrare i numeri e le date dei certificati dell'imposta dedotta all'origine (TDS) ricevuti per uno specifico conto fornitore, cliente e CoGe.
author: kailiang
mms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 2c7fe2e1050053fb2ddaf85854e7ac46dd6912a5
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358364"
---
# <a name="record-tds-recoverable-certificate-numbers"></a>Registrare numeri di certificati recuperabili TDS

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come utilizzare la pagina **Certificati recuperabili** per registrare i numeri e le date dei certificati dell'imposta dedotta all'origine (TDS) ricevuti per uno specifico conto fornitore, cliente e CoGe. Per aggiornare i numeri e le date dei certificati TDS registrati per le transazioni TDS in questa pagina, utilizza la pagina **Aggiorna certificato** (**Contabilità generale \> Periodico \> Ritenuta d'acconto \> Aggiorna certificato**). Dopo aver terminato l'aggiornamento dei numeri di certificato TDS, chiudili.

Segui questi passaggi per registrare i numeri e le date dei certificati TDS.

1. Vai a **Imposta \> Imposte indirette \> Ritenuta d'acconto \> Certificati recuperabili**.

    [![Pagina Certificati recuperabili.](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png) 

2. Nella pagina **Certificati recuperabili**, nel campo **Tipo di imposta**, seleziona **TDS**.
3. Selezionare **Nuovo** per creare un record.
4. Nel campo **Numero certificato**, immetti il numero di certificato TDS.
5. Nel campo **Tipo di account** seleziona il tipo di conto per il quale viene ricevuto il certificato TDS: **Fornitore**, **Cliente** o **CoGe**.
6. Nel campo **Conto**, seleziona il numero di conto fornitore, cliente o CoGe, a seconda del tipo di conto selezionato. Il campo **Nome** mostra il nome del conto fornitore, cliente o CoGe.
7. Nel campo **Importo certificato** immetti l'importo del certificato TDS.
8. Nel campo **Data**, immetti la data del certificato per il numero del certificato.
9. Seleziona **Richieste di informazioni** per aprire la pagina **Transazioni certificati**, in cui puoi visualizzare le transazioni TDS per le quali vengono aggiornati il numero e la data del certificato TDS. Queste informazioni possono essere aggiornate nella pagina **Aggiorna certificato** (**Imposta \> Dichiarazioni \> Ritenuta d'acconto \> Aggiorna certificato**).

    La pagina **Aggiorna certificato** mostra le seguenti informazioni per ciascuna transazione TDS:

    - **Data** - La data di registrazione della transazione TDS.
    - **Giustificativo** - Il numero di giustificativo della transazione TDS.
    - **Origine** - Il modulo in cui la transazione TDS è stata creata.
    - **Conto** - Il numero di conto fornitore, cliente o CoGe per cui è stata creata la transazione TDS.
    - **Nome** - Il numero di conto fornitore, cliente o CoGe per cui la transazione TDS è stata creata.
    - **Importo** - L'importo della fattura su cui è stata calcolata la TDS.
    - **Importo imposta** - L'importo della TDS calcolato per la transazione.
    - **Data certificato** - La data del certificato TDS che è stata aggiornata per la transazione TDS.
    - **Numero certificato** - Il numero del certificato TDS che è stato aggiornato per la transazione TDS.

10. Nella pagina **Certificati recuperabili**, seleziona la casella di controllo **Chiuso** per chiudere il numero del certificato TDS dopo averlo aggiornato per le transazioni TDS nella pagina **Aggiorna certificato**.

    Per selezionare la casella di controllo **Chiuso** per tutti i record nella pagina, seleziona **Contrassegna tutto**.

    > [!NOTE]
    > I numeri di certificato TDS per i quali la casella di controllo **Chiuso** è selezionata non sono disponibili nella pagina **Aggiorna certificato**.
