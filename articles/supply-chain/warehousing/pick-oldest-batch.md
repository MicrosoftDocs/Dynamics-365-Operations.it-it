---
title: Prelevare il batch meno recente su un dispositivo mobile
description: In questo argomento viene descritto come impostare e applicare le opzioni per prelevare il batch meno recente da un dispositivo mobile.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f235c34d6369c6f0584a7bac1c1be75f3d84c9c0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431028"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a>Prelevare il batch meno recente su un dispositivo mobile

[!include [banner](../includes/banner.md)]

È possibile accedere alla configurazione **Preleva batch meno recente** tramite un menu del dispositivo mobile e forzare o avvertire gli addetti del magazzino a prelevare il batch meno recente per l'ubicazione corrente.  

## <a name="where-it-applies"></a>Dove si applica
L'opzione Preleva batch meno recente è configurata nelle voci di menu del dispositivo mobile e ha impatto sul prelievo di batch degli articoli seguenti.

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a>Come impostare la configurazione per Preleva batch meno recente 
Per gli articoli impostati per utilizzare il lavoro esistente, **Preleva batch meno recente** può essere impostata su **Nessuno**, **Avvisa** o **Forza** dal menu del dispositivo mobile.

**Nessuno**: i lavoratori non riceveranno messaggi e potranno prelevare qualsiasi batch nella loro ubicazione.

**Avvisa** e **Forza**: un elenco di batch con la data di scadenza meno recente verrà visualizzato sopra il controllo del batch quando il lavoratore seleziona un batch. Se l'ubicazione è controllata mediante targa, un elenco delle targhe con il batch meno recente verrà visualizzato sopra il controllo della targa. 
-   **Avvisa**: se un lavoratore sceglie una targa o un batch che non appaiono nell'elenco, il controllo verrà lasciato vuoto e verrà visualizzato un avviso che indica la presenza di un batch meno recente da selezionare. Per continuare il lavoro, il lavoratore può selezionare nuovamente la stessa targa o batch.  
-   **Forza**: i lavoratori continueranno a ricevere il messaggio che indica la presenza di un batch meno recente da prelevare.
