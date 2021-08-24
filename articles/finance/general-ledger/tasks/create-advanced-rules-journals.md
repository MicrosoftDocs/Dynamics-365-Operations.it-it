---
title: Creare regole avanzate per giornali di registrazione
description: Questa procedura descrive come creare regole avanzate per i giornali di registrazione.
author: aprilolson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fe26409ebaa83595885756056810a4a2037045f0f8ad312b52c507343dec3b2d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779472"
---
# <a name="create-advanced-rules-for-journals"></a>Creare regole avanzate per giornali di registrazione

[!include [banner](../../includes/banner.md)]

Questa procedura descrive come creare regole avanzate per i giornali di registrazione. Sono incluse le impostazioni del controllo del giornale di registrazione e delle restrizioni della registrazione per utente. Questa procedura utilizza la società di dati dimostrativi USMF.


## <a name="set-up-journal-control"></a>Impostare il controllo del giornale di registrazione
1. Nel **pannello di navigazione**, andare a **Moduli > Contabilità generale > Impostazione giornale di registrazione > Nomi giornale di registrazione**.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Fare clic su **Riquadro azioni** nel **Controllo giornale di registrazione**.
4. Nella Scheda dettaglio **Quali tipi di conto è possibile registrare?**, fare clic su **Aggiungi**.
5. Nel campo **Account società** fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco trovare e selezionare il record desiderato.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Nella Scheda dettaglio **Quali sono i valori segmento validi per questo giornale di registrazione?**, fare clic su **Aggiungi**.
9. Nel campo **Struttura dei conti** fare clic sul pulsante a discesa per aprire la ricerca.
10. Trovare e selezionare il record desiderato nell'elenco.
11. Nell'elenco fare clic sul collegamento nella riga selezionata.
12. Nel campo **Segmento** fare clic sul pulsante a discesa per aprire la ricerca.
13. Nell'elenco fare clic sul collegamento nella riga selezionata.
14. Nel campo **Dal valore** fare clic sul pulsante a discesa per aprire la ricerca.
15. Trovare e selezionare il record desiderato nell'elenco.
16. Nell'elenco fare clic sul collegamento nella riga selezionata.
17. Nel campo **Al valore** fare clic sul pulsante a discesa per aprire la ricerca.
18. Nell'elenco trovare e selezionare il record desiderato.
19. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="set-up-posting-restrictions"></a>Impostare le restrizioni di registrazione
1. Chiudere la pagina.
2. Fare clic su **Restrizioni registrazione**.
3. In **Come si desidera impostare le restrizioni di registrazione**, selezionare "Per gruppo utenti".
4. Nella struttura, selezionare 'il gruppo a cui è consentita la registrazione per questo nome di giornale di registrazione'.
5. Fare clic su **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]