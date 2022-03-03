---
title: Creare un codice interessi con un intervallo
description: I codici interessi possono essere impostati per calcolare importi d'interesse diversi in base a un intervallo di valori.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d77fc88f606f4e690583fbcda79f628a35f14f6a
ms.sourcegitcommit: 6a269db08e8bb3bb3405c9f4a512091d13c80faa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119476"
---
# <a name="create-an-interest-code-with-a-range"></a>Creare un codice interessi con un intervallo

[!include [banner](../../includes/banner.md)]
I codici interessi possono essere impostati per calcolare importi d'interesse diversi in base a un intervallo di valori. Questa procedura consente di aggiungere un codice interessi e un intervallo.

1. Andare a **Crediti e riscossioni > Interessi > Imposta codici interessi**.
2. Fare clic su **Nuovo**.
3. Nel campo **Codice interessi**, immettere il nome del codice interessi.
4. Nel campo **Descrizione** immettere una descrizione per il codice interessi.
5. Selezionare **Mese**.
6. Espandere la sezione **Redditi**.
7. Espandere la sezione **Utili per valuta**.
8. Nel campo **Conto di registrazione contabile**, specificare i valori desiderati.
9. Nel campo **Interessi in base a intervallo**, selezionare "Mesi".
10. Scegliere **Aggiungi**.
11. Nel campo **Descrizione** immettere una descrizione per la valuta e l'intervallo.
12. Fare clic su **Salva**.
13. Fare clic su **Intervalli**.
14. Fare clic su **Nuovo**.
15. Immettere 0 in **Dal valore** e immettere la percentuale di interesse per mese da utilizzare per calcolare gli interessi. In questo esempio, è 1,5.
16. Fare clic su **Nuovo**.
17. Immettere il successivo valore Dal come 4, ovvero il primo mese in cui verrà calcolato un nuovo importo d'interesse.
18. Immettere la percentuale di interesse per mese da utilizzare per calcolare gli interessi a partire dal mese 4. In questo esempio, è 2,0.
19. Fare clic su **Nuovo**.
20. Immettere il successivo valore Dal come 7, ovvero il mese successivo in cui verrà calcolato un nuovo importo d'interesse.
21. Immettere la percentuale di interesse per mese da utilizzare per calcolare gli interessi a partire dal mese 7. In questo esempio, è 2,5.
22. Fare clic su **Chiudi** per completare l'impostazione.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
