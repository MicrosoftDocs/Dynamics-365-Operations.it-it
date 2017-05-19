---
title: Domande frequenti sul client Microsoft Dynamics 365 for Operations
description: Questo articolo fornisce risposte alle domande frequenti sul client Microsoft Dynamics 365 for Operations.
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 94f5874cb24b53476843f1a073dc9c4cfdb36ac9
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="dynamics-365-for-operations-client-faq"></a>Domande frequenti sul client Microsoft Dynamics 365 for Operations

[!include[banner](../includes/banner.md)]


Questo articolo fornisce risposte alle domande frequenti sul client Microsoft Dynamics 365 for Operations.

<a name="why-arent-symbols-loaded-when-i-use-dynamics-365-for-operations"></a>Perché i simboli non vengono caricati quando utilizzo Dynamics 365 for Operations?
-----------------------------------------------------------------

Le impostazioni di sicurezza nel browser potrebbero impedire ai simboli di caricarsi correttamente. Per risolvere questo problema, tentare di procedere come segue:

-   Se questo problema si verifica in Internet Explorer, fare clic su **Strumenti**, quindi su **Opzioni Internet**.  Nella finestra di dialogo Opzioni Internet, nella scheda **Privacy**, fare clic su **Livello personalizzato** e assicurarsi che l'opzione **Download dei caratteri** sia selezionata.
-   In caso contrario, potrebbe essere necessario aggiungere il sito Dynamics 365 for Operations all'elenco dei siti attendibili.

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>La barra multifunzione di Dynamics AX 2012 non è visibile. Posso mantenere sempre aperte le schede del riquadro azioni?
Implementeremo presto questa funzionalità. Gli utenti potranno a quel punto scegliere di tenere le schede sempre aperte nei riquadri azioni. In caso contrario, le schede verranno compresse quando non saranno utilizzate, per ottenere maggiore spazio sullo schermo per la pagina.

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-rightclick"></a>Perché talvolta vedo menu di scelta rapida diversi quando faccio clic con il pulsante destro del mouse?
Se si fa clic con il pulsante destro del mouse in un campo modificabile (o se il testo viene selezionato), verrà visualizzato il menu di scelta rapida del browser. Questo menu consente l'accesso ai comandi **Taglia**, **Copia** e **Incolla**. Non è possibile includere questi comandi nei menu di scelta rapida di Dynamics 365 for Operations, perché, per motivi di sicurezza, i browser non consentono di accedere agli Appunti del sistema a livello di codice.

Se si fa clic con il pulsante destro del mouse su un'etichetta di campo o sul valore di un controllo di sola lettura, verrà visualizzato il menu di scelta rapida di Dynamics 365 for Operations.

Per rendere l'accesso alla tastiera più semplice, si intende implementare in futuro tasti di scelta rapida che apriranno il menu di scelta rapida Dynamics 365 for Operations.

## <a name="where-is-the-view-details-functionality-in-dynamics-365-for-operations"></a>Dov'è la funzionalità Visualizza dettagli in Dynamics 365 for Operations?
L'opzione **Visualizza dettagli** è disponibile in un paio di modi:

-   Se un controllo ha le funzionalità **Visualizza dettagli**e se il controllo ha un valore, il valore viene visualizzato come collegamento ipertestuale. È possibile fare clic sul collegamento ipertestuale per aprire la pagina contenente dettagli aggiuntivi.
-   **Visualizza dettagli** è anche un'opzione dei menu di scelta rapida di Dynamics 365 for Operations. Per ulteriori informazioni su quando i menu di scelta rapida di Dynamics 365 for Operations vengono visualizzati quando si fa clic con il pulsante destro del mouse, vedere la sezione precedente.





