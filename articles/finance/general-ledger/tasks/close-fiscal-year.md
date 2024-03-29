---
title: Chiudere l'anno fiscale
description: Questa procedura descrive il processo di chiusura di fine anno per il trasferimento dei saldi in un nuovo anno fiscale.
author: aprilolson
ms.date: 11/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, LedgerFiscalCloseGroup, LedgerFiscalCloseAddLedger, SysLookupMultiSelectGrid, LedgerFiscalCloseRunGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4d52e6789a96defaf1d0132fe97fc183a05af207
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779814"
---
# <a name="close-the-fiscal-year"></a>Chiudere l'anno fiscale

[!include [banner](../../includes/banner.md)]

Questa procedura descrive il processo di chiusura di fine anno per il trasferimento dei saldi in un nuovo anno fiscale.


## <a name="validate-year-end-close-parameters"></a>Convalidare i parametri di chiusura di fine anno
1. Passare a **Pannello di navigazione > Moduli > Contabilità generale > Impostazione contabilità generale > Parametri di contabilità generale**.
2. Espandere la sezione **Chiusura anno fiscale**.
3. Selezionare **Sì** o **No** per l'opzione **Elimina transazioni di fine anno durante il trasferimento**.
    
Se l'anno fiscale è già stato chiuso e la chiusura di fine anno viene rieseguita, questa impostazione è importante. Se impostata su **Sì**, il giustificativo per la precedente chiusura di fine anno verrà eliminato e un nuovo giustificativo verrà creato per tutti i saldi iniziali di conti. Se l'opzione è impostata su **No**, il giustificativo precedente rimarrà e un nuovo giustificativo verrà creato solo per le voci di rettifica registrate dopo l'ultima chiusura di fine anno.

4. Selezionare **Sì** o **No** per l'opzione **Crea transazioni di chiusura durante il trasferimento**.

Se l'opzione è impostata su **Sì**, due transazioni vengono create. Un giustificativo viene creato nell'anno fiscale che viene chiuso per azzerare i saldi di tutti i conti CoGe e un secondo giustificativo viene creato nell'anno fiscale successivo per i saldi iniziali. Se impostata su **No**, a un singolo giustificativo viene creato nell'anno fiscale successivo per i saldi iniziali.  

5. Selezionare **Sì** o **No** per l'opzione **Imposta stato anno fiscale su chiuso in modo permanente**.

Se impostata su **Sì**, lo stato dell'anno fiscale verrà impostato su **Chiuso in modo permanente**. Poiché un anno chiuso in modo permanente non può essere riaperto, la procedura consigliata è di impostare questa opzione su **No**.  

6. Selezionare **Sì** o **No** per l'opzione **È necessario compilare il numero del giustificativo durante la chiusura di fine anno**.

Se impostata su **Sì**, è necessario immettere un numero di giustificativo manualmente durante il processo di chiusura di fine anno. Una sequenza numerica non viene utilizzata per generare il numero di giustificativo. La procedura consigliata è di impostare questa opzione su **Sì**.  

7. Chiudere la pagina.
8. Andare a **Contabilità generale > Periodo chiuso > Chiusura di fine anno**.
9. Fare clic su **Nuovo** per creare un modello di chiusura di fine anno.

Un modello può essere creato per un gruppo di persone giuridiche per cui eseguire la chiusura di fine anno. Questo modello può essere riutilizzato anno dopo anno.  

10. Nel campo **Nome gruppo** immettere un nome di modello di chiusura di fine anno.
11. Nel campo **Calendario fiscale**, selezionare l'anno fiscale per il quale il modello verrà creato.

Solo le persone giuridiche che utilizzano lo stesso anno fiscale possono essere raggruppate nel modello di chiusura di fine anno. Questo perché la chiusura di fine anno viene effettuata selezionando un anno fiscale, non una data.  

12. Nel **riquadro azioni** fare clic su **Salva**.
13. Nella sezione **Persone giuridiche**, fare clic su **Aggiungi** per selezionare le persone giuridiche per il modello.
    
Le persone giuridiche possono essere aggiunti selezionando le persone giuridiche o selezionando una gerarchia organizzativa. Solo le persone giuridiche con la gerarchia organizzativa con lo stesso calendario fiscale selezionato verranno aggiunte.  

14. Selezionare le persone giuridiche o la gerarchia organizzativa.
15. Fare clic su **OK**.
16. Selezionare **Sì** o **No** in **Trasferisci dimensioni di conto patrimoniale**.

La procedura consigliata è di impostare questa opzione su **Sì** per i conti dello stato patrimoniale. Questo per gestire le dimensioni finanziarie nelle transazioni registrate durante la creazione dei saldi iniziali per i conti dello stato patrimoniale. Per i conti profitti e perdite, è possibile selezionare di gestire le dimensioni finanziarie (**Chiudi tutto**) quando i saldi vengono spostati negli utili non distribuiti oppure di avere le dimensioni finanziarie sostituite con un altro valore di dimensione (**Chiudi singolo**). Se si seleziona **Chiudi singolo**, è possibile definire un valore specifico per ogni dimensione o anche scegliere di lasciarla vuota.  

17. Fare clic su **Salva**.
18. Avviare la chiusura di fine anno scegliendo **Esegui chiusura fiscale** nel **riquadro azioni**. La chiusura di fine anno verrà eseguita per il modello selezionato.  
19. Selezionare tutte o un sottoinsieme di persone giuridiche dal modello per cui eseguire la chiusura di fine anno.

Alla prima esecuzione della chiusura di fine anno, per ottenere i saldi iniziali la maggior parte delle organizzazioni possono scegliere di eseguire la chiusura di fine anno per tutte le persone giuridiche nel modello. Se le voci di rettifica vengono effettuate successivamente, è possibile scegliere di eseguire la chiusura di fine anno solo per le persone giuridiche con rettifiche.  

20. Fare clic su **OK**.
21. Selezionare l'anno fiscale per cui eseguire la chiusura.
22. Nel campo **Giustificativo** digitare un valore. È consigliabile includere l'anno fiscale nel numero di giustificativo, per semplificare la ricerca del giustificativo di chiusura di fine anno creato.  
23. La chiusura di fine anno viene eseguita in modalità batch per impostazione predefinita. È consigliabile eseguire in modalità batch i processi a esecuzione prolungata. Questo è in genere uno di tali processi, che è il motivo per cui l'impostazione predefinita è utilizzare la modalità batch.  
24. Fare clic su **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
