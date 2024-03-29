---
title: Impostare i dati master tariffe
description: Questa procedura mostra come impostare dati master tariffe.
author: Weijiesa
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e707d226894c3cd647094556bfcc017347cb7f6
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675517"
---
# <a name="set-up-rate-masters"></a>Impostare i dati master tariffe

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come impostare dati master tariffe. Il responsabile della logistica in genere imposta i dati master tariffe, a seconda dei contratti firmati con i vettori. In questo scenario verranno impostati dati master per una compagnia aerea. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.

## <a name="set-up-break-master"></a>Impostare i dati master di interruzione

1. Passare a **Gestione trasporto > Impostazioni > Valutazione > Dati master di interruzione**. I dati master di interruzione vengono utilizzati per definire la struttura dei prezzi e i relativi punti di interruzione. La struttura dei prezzi utilizza livelli di prezzo basati su dimensioni fisiche.  
1. Selezionare **Nuovo**.
1. Nel campo **Dati master di interruzione** immettere un valore.
1. Nel campo **Nome** immettere un valore.
1. Nel campo **Tipo di dati** selezionare il tipo di dati.
1. Nel campo **Confronto** inserire il tipo di confronto richiesto (tramite operatori).
1. Nel campo **Unità di interruzione** immettere i valori dell'unità di interruzione.
1. Nella sezione **Dettagli** creare tutte le interruzioni necessarie per la struttura dei prezzi.
1. Selezionare **Salva**.

## <a name="set-up-rate-master"></a>Impostare dati master tariffe

1. Passare a **Gestione trasporto > Impostazioni > Valutazione > Tariffa principale**.
1. Selezionare **Nuovo**.
1. Digitare un valore nel campo **Tariffa principale**.
1. Digitare un valore nel campo **Nome**.
1. Nel campo **ID di valutazione dei metadati** selezionare il pulsante a discesa per aprire la ricerca. L'ID dei metadati di valutazione determinerà i dati necessari per i dati master tariffe, perché definisce i metadati previsti dal motore di gestione trasporto che utilizza tali dati master.  
1. Per questo esempio, selezionare l'opzione P2P. Questa è già definita nei dati della demo.
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
1. Selezionare **Salva**.

## <a name="set-up-rate-base"></a>Impostare una base tariffa

1. Selezionare la **base della tariffa**.
    * La base della tariffa determina la tariffa del vettore e può essere utilizzata per impostare una struttura tariffaria perché organizza le tariffe in punti di interruzione definiti nei dati master di interruzione.  
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Base tariffa**.
4. Digitare un valore nel campo **Nome**.
5. Nel campo **Dati master di interruzione** selezionare il pulsante a discesa per aprire la ricerca.
    * I dati master di interruzione vengono utilizzati per definire la struttura dei prezzi e i relativi punti di interruzione. La struttura dei prezzi utilizza livelli di prezzo basati su dimensioni fisiche.  
6. Per questo esempio, utilizzare il peso. Questa è già definita nei dati della demo.
7. Nell'elenco fare clic sul collegamento nella riga evidenziata.
8. Espandere la sezione **Dettagli**.
9. Selezionare **Nuovo**.
10. Nel campo **CAP consegna da** digitare "30301".
11. Nel campo **CAP consegna a** digitare "30318".
12. Nel campo **Paese consegna** digitare "USA".
13. Nel campo **<1,00 kg**, digitare "100".
    * Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 1 chilogrammo.  
14. Nel campo **<5,00 kg**, digitare "300".
    * Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 5 chilogrammi.  
15. Nel campo **<20,00 kg**, digitare "500".
    * Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 20 chilogrammi.  
16. Nel campo **<100,00 kg**, digitare "1000".
    * Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 100 chilogrammi.  
17. Nel campo **<1.000,00 kg**, digitare "3000".
    * Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 1000 chilogrammi.  
18. Selezionare **Salva**.
19. Chiudere la pagina.

## <a name="assign-rate-base"></a>Assegnare una base tariffa

1. Espandere la sezione **Assegnazioni base tariffa**.
2. Selezionare **Nuovo**.
    * È possibile includere più assegnazioni di base della tariffa per ogni dato master tariffa. Ciò consente di creare prezzi diversi per ogni vettore a seconda delle destinazioni, dei servizi e delle diverse basi di tariffa. In questa procedura verrà creata solo un'assegnazione di base della tariffa.  
3. Digitare un valore nel campo **Nome**.
4. Nel campo **Base tariffa** selezionare il pulsante a discesa per aprire la ricerca.
5. Nell'elenco fare clic sul collegamento nella riga evidenziata.
6. Nel campo **Servizio** selezionare il pulsante a discesa per aprire la ricerca.
7. Nell'elenco trovare e selezionare il record desiderato.
8. Nell'elenco fare clic sul collegamento nella riga evidenziata.
9. Nel campo **CAP prelievo** digitare "98052".
    * Specificare il codice postale da cui questa assegnazione di base della tariffa deve essere valida.
10. Nel campo **Paese prelievo** digitare "USA".
11. Selezionare **Salva**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]