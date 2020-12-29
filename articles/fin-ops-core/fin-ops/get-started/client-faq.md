---
title: Domande frequenti sul client
description: Questo articolo fornisce risposte alle domande frequenti sul client Finance and Operations.
author: jasongre
manager: AnnBe
ms.date: 09/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1925c23891a637ba9e9666538323274819692a06
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692920"
---
# <a name="client-faq"></a>Domande frequenti sul client

[!include [banner](../includes/banner.md)]

Questo articolo fornisce risposte alle domande frequenti sul client Finance and Operations.

## <a name="why-arent-symbols-loaded"></a>Perché i simboli non vengono caricati?

Le impostazioni di sicurezza nel browser potrebbero impedire ai simboli di caricarsi correttamente. Per risolvere questo problema, tentare di procedere come segue:

- Se questo problema si verifica in Internet Explorer, fare clic su **Strumenti**, quindi su **Opzioni Internet**. Nella finestra di dialogo Opzioni Internet, nella scheda **Privacy**, fare clic su **Livello personalizzato** e assicurarsi che l'opzione **Download dei caratteri** sia selezionata.
- In caso contrario, potrebbe essere necessario aggiungere il sito dell'app all'elenco dei siti attendibili.

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>La barra multifunzione di Dynamics AX 2012 non è visibile. Posso mantenere sempre aperte le schede del riquadro azioni?

Implementeremo presto questa funzionalità. Gli utenti potranno a quel punto scegliere di tenere le schede sempre aperte nei riquadri azioni. In caso contrario, le schede verranno compresse quando non saranno utilizzate, per ottenere maggiore spazio sullo schermo per la pagina.

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-right-click"></a>Perché talvolta vedo menu di scelta rapida diversi quando faccio clic con il pulsante destro del mouse?

Se si fa clic con il pulsante destro del mouse in un campo modificabile (o se il testo viene selezionato), verrà visualizzato il menu di scelta rapida del browser. Questo menu consente l'accesso ai comandi **Taglia**, **Copia** e **Incolla**. Non è possibile includere questi comandi nei menu di scelta rapida poiché, per motivi di sicurezza, i browser non concedono di accedere a livello di codice agli Appunti del sistema.

Se si fa clic con il pulsante destro del mouse su un'etichetta di campo o sul valore di un controllo di sola lettura, verrà visualizzato il menu di scelta rapida.

Per rendere l'accesso alla tastiera più semplice, si ha in programma di implementare in futuro tasti di scelta rapida che apriranno il menu di scelta rapida.

## <a name="where-is-the-view-details-functionality"></a>Dov'è la funzionalità Visualizza dettagli?

L'opzione **Visualizza dettagli** è disponibile in un paio di modi:

- Se un controllo ha le funzionalità **Visualizza dettagli** e se il controllo ha un valore, il valore viene visualizzato come collegamento ipertestuale. È possibile fare clic sul collegamento ipertestuale per aprire la pagina contenente dettagli aggiuntivi.
- **Visualizza dettagli** è anche un'opzione dei menu di scelta rapida. Per ulteriori informazioni su quando i menu di scelta rapida vengono visualizzati quando si fa clic con il pulsante destro del mouse, vedere la sezione precedente.
