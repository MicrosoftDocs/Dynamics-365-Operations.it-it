---
title: Dichiarare finito a un'ubicazione a un'ubicazione non controllata da targa (Applicazione, maggio 2016)
description: In questa guida di attività è riportato un esempio di dichiarazione di finito a un'ubicazione che non controllata da targa.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdParmCostEstimation, ProdParmStartUp, ProdParmReportFinished, WHSWorkTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f891b2e3b20993a08138dfac1aed4f4bab33c6b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576714"
---
# <a name="report-as-finished-to-a-non-license-plate-controlled-location--application-may-2016"></a>Dichiarare finito a un'ubicazione a un'ubicazione non controllata da targa (Applicazione, maggio 2016)

[!include [banner](../../includes/banner.md)]

In questa guida di attività è riportato un esempio di dichiarazione di finito a un'ubicazione che non controllata da targa. I criteri di lavoro applicabili sono il prerequisito per questa attività. Una guida di attività precedente ha mostrato l'impostazione dei criteri di lavoro. Questa guida attività richiede l'applicazione Dynamics AX 7.0.1 o versione successiva.




## <a name="set-up-an-output-location"></a>Impostare un'ubicazione di output
1. Andare ad Amministrazione organizzazione > Risorse > Gruppi di risorse.
2. Nell'elenco selezionare il gruppo di risorse "5102".
3. Fare clic su Modifica.
4. Nel campo Magazzino di output immettere "51".
5. Nel campo Ubicazione di output immettere "001".
    * L'ubicazione 001 non è un'ubicazione controllata da targa. È possibile impostare un'ubicazione di output senza targa solo se i criteri di lavoro applicabili sono disponibili per l'ubicazione.  

## <a name="create-a-production-order-and-report-it-as-finished"></a>Creare un ordine di produzione e segnalarlo come finito
1. Chiudere la pagina.
2. Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.
3. Fare clic su Nuovo ordine di produzione.
4. Nel campo Numero articolo immettere "L0101".
5. Fare clic su Crea.
6. Nel riquadro azioni, fare clic su Ordine di produzione.
7. Fare clic su Stima.
8. Fare clic su OK.
9. Fare clic su Inizia.
10. Fare clic sulla scheda Generale.
11. Nel campo Consumo DBA automatico selezionare "Mai".
12. Fare clic su OK.
13. Fare clic su Dichiarato finito.
14. Fare clic sulla scheda Generale.
15. Selezionare Sì nel campo Accetta errore.
16. Fare clic su OK.
17. Nel riquadro azioni fare clic su Magazzino.
18. Fare clic su Dettagli lavoro.
    * Quando l'ordine di produzione è stato dichiarato finito, nessun lavoro è stato generato per lo stoccaggio. Questa situazione si verifica perché vengono definiti criteri di lavoro che impediscono la generazione del lavoro quando il prodotto L0101 viene dichiarato finito all'ubicazione 001.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]