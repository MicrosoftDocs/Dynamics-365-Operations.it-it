---
title: Dynamics 365 for Operations client FAQ
description: L&quot;articolo prevede le risposte alle domande frequenti relative Microsoft Dynamics 365 per il client delle operazioni.
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 2c99b2e1f7ddecb61be62832ca1a8d3ac1fd21a8
ms.lasthandoff: 03/31/2017


---

# <a name="dynamics-365-for-operations-client-faq"></a>Dynamics 365 for Operations client FAQ

L'articolo prevede le risposte alle domande frequenti relative Microsoft Dynamics 365 per il client delle operazioni.

<a name="why-arent-symbols-loaded-when-i-use-dynamics-365-for-operations"></a>Perché i simboli non vengono caricati in uso Dynamics 365 per le operazioni?
-----------------------------------------------------------------

Le impostazioni di sicurezza nel browser potrebbero impedire ai simboli di caricarsi correttamente. Per risolvere questo problema, tentare di procedere come segue:

-   Se si verificano questo problema in Internet Explorer, fare clic su ** strumenti ** quindi fare clic su ** opzioni Internet **.  Nella finestra di dialogo Opzioni Internet, ** privacy ** nella scheda, fare clic su ** livello personalizzato ** e che verificare che ** download del carattere ** l'opzione sia selezionata.
-   In caso contrario, potrebbe essere necessario aggiungere Dynamics 365 per il sito delle operazioni all'elenco dei siti di fiducia selezionata.

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>Manco il la barra multifunzione da Dynamics AX 2012. Posso mantenere le schede del riquadro azioni aperte continuamente?
Stiamo prevede di implementare questa funzionalità in precedenza. Gli utenti potranno quindi scegliere di mantenere le schede nei riquadri azioni aperte continuamente. In caso contrario, le schede verranno compresse quando non saranno utilizzate, per ottenere maggiore spazio sullo schermo per la pagina.

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-rightclick"></a>Perché talvolta vedo i menu di scelta rapida diverse quando rightclick?
Se si fa clic con il pulsante destro del mouse in un campo modificabile (o se il testo viene selezionato), verrà visualizzato il menu di scelta rapida del browser. Questo menu consente l'accesso ai comandi **Taglia**, **Copia** e **Incolla**. Non possiamo importare questi controlli in Dynamics 365 per menu di scelta rapida delle operazioni poiché, per motivi di protezione, quelli non consentono il quale livello accediamo negli Appunti di sistema.

Se si fa clic con il pulsante destro del mouse un'etichetta del campo o il valore di un controllo passivo, vedrete Dynamics 365 per il menu di scelta rapida delle operazioni.

Per effettuare la tastiera l'accesso a più semplice, quale piano da implementare una scorciatoia tasti di scelta rapida in futuro che verrà Dynamics 365 per il menu di scelta rapida delle operazioni.

## <a name="where-is-the-view-details-functionality-in-dynamics-365-for-operations"></a>Se la funzionalità dei dettagli di visualizzazione in Dynamics 365 per le operazioni?
L'opzione **Visualizza dettagli** è disponibile in un paio di modi:

-   Se un controllo ha le funzionalità **Visualizza dettagli **e se il controllo ha un valore, il valore viene visualizzato come collegamento ipertestuale. È possibile fare clic sul collegamento ipertestuale per aprire la pagina contenente dettagli aggiuntivi.
-   ** Consente di visualizzare ** è anche un'opzione in Dynamics 365 per menu di scelta rapida delle operazioni. Per ulteriori informazioni sulla Dynamics 365 per menu di scelta rapida delle operazioni viene visualizzato quando si fa clic con il pulsante destro del mouse, vedere la sezione precedente.



