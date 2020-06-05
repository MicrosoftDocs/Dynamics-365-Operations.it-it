---
title: Spese interaziendali
description: Un lavoratore assunto da una persona giuridica in un'organizzazione può eseguire il lavoro per un'altra persona giuridica nella stessa organizzazione. In questo caso, è possibile utilizzare la funzionalità interaziendale spese per assegnare le spese del lavoratore alla persona giuridica per la quale è stato eseguito il lavoro.
author: ShylaThompson
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0967f23e4e1f8e0431c55d4d54554e7e90e2451c
ms.sourcegitcommit: 07e425707eb20730f10246a27799f4deeef93f97
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "3390886"
---
# <a name="intercompany-expenses"></a>Spese interaziendali

[!include [banner](../includes/banner.md)]

Un lavoratore assunto da una persona giuridica in un'organizzazione può eseguire il lavoro per un'altra persona giuridica nella stessa organizzazione. In questo caso, è possibile utilizzare la funzionalità interaziendale spese per assegnare le spese del lavoratore alla persona giuridica per la quale è stato eseguito il lavoro. La persona giuridica che impiega il lavoratore è definita persona giuridica offerente. La persona giuridica per cui il lavoratore sostiene le spese viene chiamata persona giuridica richiedente. 

Prima che un lavoratore possa creare e inviare le spese di lavoro eseguito per una persona giuridica diversa, per la persona giuridica offerente. selezionare l'opzione **Consenti righe spese aziendali** nella pagina **Parametri di Gestione spese**. 

## <a name="tax-posting-for-intercompany-expenses"></a>Registrazione imposta per spese interaziendali

[!include [banner](../includes/banner.md)]

Se desideri utilizzare i gruppi fiscali associati all'entità legale (fonte) del prestito anziché all'entità legale (destinazione) del prestito nella nota spese, devi configurarla nell'impostazione dei codici IVA della Contabilità generale. Quando il parametro Contabilità generale, **Persona giuridica per la registrazione dell'IVA interaziendale** è impostato su **Fonte** e **Applica regole di tassazione IVA** è impostato su **No**, verrà utilizzata la combinazione fiscale per l'entità giuridica prestante. Quando lo stesso parametro è impostato su **Destinazione**, verrà utilizzata la combinazione fiscale per l'assunzione dell'entità giuridica. Per le persone giuridiche negli Stati Uniti, quando il parametro è impostato su **Fonte**, il campo **IVA a credito** deve essere anche configurato nella nuova pagina **Gruppi registrazione contabile**. Il motore di contabilità utilizzerà le informazioni da questo campo per l'immissione contabile relativa alle imposte.   
Il comportamento è coerente per le righe di spesa registrate con o senza progetto.  
