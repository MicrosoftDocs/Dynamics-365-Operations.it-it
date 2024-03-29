---
title: Impostare i documenti di trasferimento per il movimento di merci all'interno di una società
description: In questa procedura viene illustrato come configurare documenti di trasferimento per il movimento di merci in una società.
author: AdamTrukawka
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: InventTransferOrders, InventLocationIdLookup, TransportationDocument, HcmWorkerLookUp, SrsReportViewerForm, InventTransferParmShip
ms.openlocfilehash: 333c5b5e5cfa25e705c9864542517f8ec5532dfe
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282336"
---
# <a name="set-up-the-transfer-documents-for-goods-movement-inside-a-company"></a>Impostare i documenti di trasferimento per il movimento di merci all'interno di una società

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come creare documenti di trasferimento per il movimento di merci in una società. Questa procedura è disponibile solo per le persone giuridiche con un indirizzo principale in Lituania. La procedura è stata creata utilizzando la società di dati dimostrativi DEMF con un indirizzo principale in Lituania. Prima di poter eseguire la procedura, è necessario completare la procedura "Impostare documenti di trasferimento per il movimento di merci in una società". Questa procedura è destinata ai contabili di inventario. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="create-a-transfer-order"></a>Creare un ordine di trasferimento
1. Andare a Gestione articoli > Ordini in entrata > Ordine di trasferimento.
2. Fare clic su Nuovo.
3. Nel campo Magazzino origine immettere o selezionare un valore.
4. Nel campo Magazzino destinazione immettere o selezionare un valore.
5. Scegliere Aggiungi.
6. Nell'elenco contrassegnare la riga selezionata.
7. Nel campo Numero di articoli immettere o selezionare un valore.

## <a name="enter-transportation-details-for-the-transfer-order"></a>Immettere i dettagli di trasporto per l'ordine di trasferimento
1. Fare clic su Salva.
2. Nel riquadro azioni fare clic su Spedisci.
3. Fare clic su Dettagli trasporto.
4. Selezionare Sì nel campo Stampa dettagli di trasporto.
5. Nel campo Beni emessi da immettere o selezionare un valore.
6. Nel campo Collo digitare un valore.
7. Nel campo Livello di rischio del carico, digitare un valore.
8. Nel campo Vettore immettere o selezionare un valore.
9. Nel campo Modello immettere o selezionare un valore.
10. Nel campo Numero di registrazione digitare un valore.
11. Nel campo Numero rimorchio digitare un valore.
12. Nel campo Conducente immettere o selezionare un valore.
13. Digitare un valore nel campo Nome conducente.
14. Fare clic su Salva.
15. Chiudere la pagina.

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a>Visualizzare il documento di trasporto per l'ordine di trasferimento non registrato
1. Fare clic su Documento di trasporto.
2. Fare clic su OK.
3. Chiudere la pagina.

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a>Visualizzare il documento di trasporto per l'ordine di trasferimento registrato
1. Nel riquadro azioni fare clic su Ordine di trasferimento.
2. Nel riquadro azioni fare clic su Spedisci.
3. Fare clic su Ordine di trasferimento spedizione.
4. Fare clic sulla scheda Generale.
5. Nel campo Aggiorna selezionare un'opzione.
6. Fare clic sulla scheda Panoramica.
7. Digitare un valore nel campo Documento di trasporto.
8. Fare clic su OK.
9. Nel riquadro azioni fare clic su Spedisci.
10. Fare clic su Documento di trasporto.
11. Fare clic su OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
