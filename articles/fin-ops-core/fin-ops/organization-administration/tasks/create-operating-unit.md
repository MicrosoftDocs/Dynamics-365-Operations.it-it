---
title: Creare un'unità operativa
description: Un'unità operativa è un'organizzazione utilizzata per dividere il controllo delle risorse economiche e dei processi operativi in un'azienda.
author: sericks007
manager: AnnBe
ms.date: 08/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMOperatingUnit, OMInternalOrganizationSelector
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 164b347e1c929f60762793799a500a7203f0f72f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189892"
---
# <a name="create-an-operating-unit"></a>Creare un'unità operativa

[!include [task guide banner](../../includes/task-guide-banner.md)]

Un'unità operativa è un'organizzazione utilizzata per dividere il controllo delle risorse economiche e dei processi operativi in un'azienda. Le persone in un'unità operativa hanno il compito di ottimizzare l'utilizzo delle risorse meno efficienti, di migliorare i processi e di rendere conto delle loro prestazioni. I tipi di unità operative includono centri di costo, Business Unit, reparti e flussi del valore. Per creare un'unità operativa, attenersi alla seguente procedura. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.

1. Andare a **Pannello di navigazione > Moduli > Amministrazione organizzazione > Organizzazioni > Unità operative**.
2. Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.
3. Nell'elenco trovare e selezionare il record desiderato. Selezionare il tipo di unità operativa che si desidera creare.  
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Digitare un valore nel campo **Nome**.
    + Espandere la sezione **Generale**, se necessario.  
    + Fornire informazioni generali sull'unità operativa, ad esempio il numero di identificazione, il numero DUNS e il manager.    
    + Espandere la sezione **Indirizzi**, se necessario.  
    + Immettere informazioni relative all'indirizzo, quali il nome della via e il numero civico, il codice postale e la città. Fare clic su **Aggiungi** per immettere un nuovo record indirizzo o su Modifica per modificare un record indirizzo esistente.   
    + Espandere la sezione **Informazioni contatto** se necessario.  
    + Immettere informazioni sui metodi di comunicazione, ad esempio indirizzi di posta elettronica, URL e numeri di telefono. Per immettere un nuovo record di comunicazione, fare clic su Nuovo. Per modificare un record di comunicazione esistente, fare clic su **Altre opzioni > Avanzate**.   
6. Se lo si desidera, modificare **Numero unità operativa** come necessario. Da notare che questo numero è un identificatore univoco per il record **Parte** corrispondente e non può essere uguale a qualsiasi altra unità operativa.
7. Selezionare **Salva**.