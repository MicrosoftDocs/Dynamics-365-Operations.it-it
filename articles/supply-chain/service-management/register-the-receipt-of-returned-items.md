---
title: Registrare il ricevimento di resi
description: È possibile registrare il ricevimento di resi utilizzando il modulo Panoramica arrivi o il modulo Registrazione.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b46801ee150d1cf25d8f4c6ea9aaa8011e1cbd38
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006618"
---
# <a name="register-the-receipt-of-returned-items"></a>Registrare il ricevimento di resi 

[!include [banner](../includes/banner.md)]


Sono disponibili due metodi per registrare il ricevimento di resi. Il primo metodo è un processo di ricevimento in magazzino che utilizza il modulo **Panoramica arrivi**. Il secondo utilizza il modulo **Registrazione**.

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a>Registrare il ricevimento di resi nel modulo Panoramica arrivi

È possibile utilizzare il modulo **Panoramica arrivi** per identificare la spedizione di un reso in base al relativo numero autorizzazione reso (NAR). Se un nome di giornale di registrazione viene definito nella scheda **Impostazione** e le righe del giornale di registrazione che corrispondono alle righe selezionate nel modulo **Panoramica arrivi** esistono, una nuova intestazione giornale di registrazione viene creata quando si fa clic su **Inizia arrivo**.

1.  Fare clic su **Gestione articoli** \> **Periodico** \> **Panoramica arrivi**.

2.  Nel campo **Nome impostazioni** selezionare **Ordine di reso** e fare clic su **Aggiorna**.
    

    > [!TIP]
    > <P>È possibile utilizzare i campi <STRONG>Intervallo</STRONG> per limitare i risultati della ricerca. Per ottenere un risultato preciso è possibile digitare o selezionare il codice NAR nel campo <STRONG>Codice NAR</STRONG>. Per definire e salvare un set di filtri che limiteranno gli arrivi in entrata visualizzati, fare clic sulla scheda <STRONG>Impostazione</STRONG>. I filtri disponibili includono tipi, magazzini e banchine.</P>

    

    > [!WARNING]
    > <P>Gli ordini di reso non possono essere combinati con altri tipi di arrivi nel modulo <STRONG>Panoramica arrivi</STRONG>. Di conseguenza, il riferimento verrà sempre un ordine cliente, ma nessun ID di ordine cliente verrà specificato nell'intestazione del giornale di registrazione.</P>



3.  Nella griglia **Ricevute** individuare la riga corrispondente al reso, quindi selezionare la casella di controllo nella colonna **Selezionato per arrivo**.

4.  Per escludere determinate righe dal ricevimento dei resi, ad esempio gli articoli dell'ordine originario non inclusi nella spedizione reso, deselezionare le caselle associate **Selezionato per arrivi** della tabella **Righe** nella parte inferiore del modulo.

5.  Fare clic sul pulsante **Inizia arrivo** per creare un giornale di registrazione arrivi.
    

    > [!NOTE]
    > <P>È possibile selezionare più ordini di reso e includerli tutti in un unico processo di arrivo. Ciascuna riga dell'ordine di reso verrà copiata in una riga corrispondente del giornale di registrazione arrivi articoli.</P>

    

    > [!NOTE]
    > <P>È inoltre possibile creare manualmente un giornale di registrazione arrivi tramite il modulo <STRONG>Arrivo articoli</STRONG>. 



6.  Fare clic su **Gestione inventario** \> **Giornali di registrazione** \> **Arrivo articoli** \> **Arrivo articoli**.

7.  Selezionare il giornale di registrazione arrivi appena creato e fare clic su **Righe** per aprire il modulo **Righe giornale di registrazione, ubicazioni**.

8.  Nella scheda **Generale**, rettificare il numero nel campo **Quantità**, se necessario, quindi assegnare un codice smaltimento nel campo **Codice smaltimento**.
    
    In alternativa, è possibile selezionare la casella di controllo **Gestione quarantena** per inviare i resi tramite un processo di ispezione nel contesto di un ordine di quarantena.
    

    > [!NOTE]
    > <P>Se si inviano i resi tramite quarantena, non è possibile specificare un codice smaltimento.</P>



9.  Fare clic sul pulsante **Convalida**.

10. Se dal processo di convalida non risulta alcun errore, fare clic su **Registra**.

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a>Registrare il ricevimento di resi nel modulo Registrazione

In alternativa all'uso del modulo **Panoramica arrivi**, è possibile utilizzare il modulo **Registrazione** per registrare l'arrivo dei resi.

1.  Fare clic su **Vendite e marketing** \> **Comune** \> **Ordini di reso** \> **Tutti gli ordini di reso**. Creare un nuovo ordine di reso o aprire l'ordine di reso dall'elenco. Nella Scheda dettaglio **Righe** selezionare la riga ordine di reso. Fare clic su **Aggiorna riga**, quindi su **Registrazione**.

2.  Assegnare un codice smaltimento nel campo **Codice smaltimento**, quindi fare clic su **OK**.
    

    > [!NOTE]
    > <P>Non è possibile inviare l'articolo per l'ispezione come ordine di quarantena utilizzando il modulo <STRONG>Registrazione</STRONG>.</P>



3.  Nella griglia **Transazioni**, selezionare la transazione da registrare.

4.  Nella griglia **Registra ora**, scegliere **Aggiungi**. Ripetere i due passaggi precedenti finché tutti i resi non compaiano nella griglia **Registra ora**.

5.  Fare clic su **Registra tutto**.

## <a name="see-also"></a>Vedere anche

[Panoramica arrivi (modulo)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]