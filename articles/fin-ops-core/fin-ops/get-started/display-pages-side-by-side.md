---
title: Mostrare le pagine affiancate utilizzando la funzionalità Apri in nuova finestra
description: Questo articolo illustra come visualizzare pagine affiancate.
author: jasongre
ms.date: 11/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.openlocfilehash: bfc2aa534da17529421af0a28d1c90ee3aeb40cb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288633"
---
# <a name="show-pages-side-by-side-using-the-open-in-new-window-feature"></a>Mostrare le pagine affiancate utilizzando la funzionalità Apri in nuova finestra

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Questo articolo illustra come visualizzare pagine affiancate.

Potrebbe essere utile visualizzare più pagine affiancate per eseguire rapidamente le attività. Come esempio, potrebbe essere utile convalidare o immettere righe in più di un giornale di registrazione. In genere, per convalidare o immettere righe in più di un giornale di registrazione, è necessario andare avanti e indietro tra la pagina che visualizza un elenco di giornali di registrazione e la pagina che visualizza righe di un giornale di registrazione specifico. Tuttavia, la funzionalità **Apri in nuova finestra** consente di visualizzare queste pagine affiancate in modo da poter eseguire rapidamente le attività.

Continuando con l'esempio citato sopra, quando vengono visualizzate le righe, è possibile fare clic sull'icona **Apri in nuova finestra**.

[![Fare clic sull'icona Apri in una nuova finestra.](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)

Se si fa clic su **Apri in nuova finestra** si apre la pagina delle righe in un nuovo browser popup e il browser originale torna indietro nello storico alla pagina in cui era visualizzato l'elenco dei giornali di registrazione. È possibile quindi visualizzare entrambe le pagine in modalità affiancata. Al termine della visualizzazione di un giornale di registrazione, sarà possibile modificare il giornale di registrazione selezionato nella pagina con l'elenco dei giornali di registrazione e nella pagina delle righe della finestra popup verranno automaticamente visualizzate le righe del giornale di registrazione appena selezionato.

[![È possibile visualizzare le pagine in modalità affiancata.](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)

Il collegamento e l'aggiornamento dinamici si verificano a causa delle relazioni esistenti tra i dati dietro a queste pagine. Se il sistema non è informato della relazione tra i dati, la finestra popup non si aggiornerà automaticamente in risposta a una modifica nella finestra da cui è stata originata.

Alcune pagine presentano più visualizzazioni, ad esempio le visualizzazioni Griglia, Intestazione e Dettagli. L'icona **Apri in nuova finestra** causa l'apertura dell'intera pagina nella nuova finestra del browser. Di conseguenza, non è possibile mantenere due visualizzazioni nella stessa pagina affiancate utilizzando la funzionalità **Apri in nuova finestra**. Quasi tutte le pagine di questo tipo hanno un elenco di navigazione da utilizzare per passare tra i record e raggiungere un simile esperienza.

Prima di utilizzare la funzionalità **Apri in nuova finestra**, è necessario configurare il blocco popup del browser per consentire i popup provenienti dall'URL del sito. Ad esempio, è possibile consentire i popup provenienti da  "\*.dynamics.com".

La funzionalità **Apri in nuova finestra** è disponibile solo quando sono presenti più pagine aperte nella finestra. Inoltre, la finestra popup si chiude automaticamente quando non sono presenti più pagine aperte (ovvero quando viene chiusa l'ultima pagina nella finestra). Il sistema chiude anche le pagine aperte quando si esplora un'area diversa dell'applicazione. Di conseguenza, se le finestre popup sono aperte e si esplora un'area diversa dell'applicazione, le finestre popup sono automaticamente chiuse perché le pagine in quelle finestre sono state chiuse dal sistema.

La barra superiore nelle finestre popup visualizza le informazioni sulla società in cui è stata aperta la pagina ed è di sola lettura. Le finestre popup si basano anche sulla finestra principale del browser. Se la finestra principale è chiusa o aggiornata, tutte le finestre popup aperte diventeranno di sola lettura. Se ciò dovesse accadere, è comunque possibile visualizzare le informazioni in queste finestre, ma non sarà possibile interagire con esse.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
