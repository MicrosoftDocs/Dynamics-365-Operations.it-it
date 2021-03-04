---
title: Raggruppamento di sistema in un elenco lavori aperti
description: Questo argomento descrive come filtrare l'elenco lavori aperti in un dispositivo mobile.
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
ms.openlocfilehash: 05b697cce8ecb9ece282fc659ab4d97c4b747c5e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431012"
---
# <a name="system-grouping-on-an-open-work-list"></a>Raggruppamento di sistema in un elenco lavori aperti

[!include [banner](../includes/banner.md)]

Utilizzando un campo di raggruppamento di sistema, è possibile filtrare un elenco lavori aperti senza dover modificare la voce di menu del dispositivo mobile.
Dove applicabile, il raggruppamento di sistema filtra un elenco lavori in un singolo campo intestazione lavoro. Non è possibile utilizzare il raggruppamento di sistema per filtrare i campi a livello di riga.

## <a name="set-up-system-grouping-on-an-open-work-list"></a>Impostare un raggruppamento di sistema su un elenco lavori aperti
Utilizzare questa procedura per impostare un raggruppamento di sistema su un elenco lavori aperti.

-   In una voce di menu del dispositivo mobile, selezionare **Modalità: Indiretta** e **Codice attività: Visualizza elenco lavori aperti**. Diventano disponibili le opzioni seguenti. Queste opzioni sono necessarie per il raggruppamento di sistema in un elenco lavori aperti. 

|        Opzione         |                                                                                                                                                                                                                                                                         descrizione                                                                                                                                                                                                                                                                         |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Consentire il raggruppamento di sistema |                                                                                                                                                                                                                                                 Consente il raggruppamento di sistema per una voce di menu dell'elenco lavoro selezionata.                                                                                                                                                                                                                                                  |
| Campo di raggruppamento sistema | Disponibile solo se <strong>Consenti lavoro di sistema</strong> è impostato su <strong>Sì</strong>. Selezionare il campo che determina la modalità di raggruppamento del lavoro di prelievo per i lavoratori. Ad esempio, se si seleziona il campo <strong>ID spedizione</strong>, il lavoratore esegue la scansione dell'ID spedizione per raggruppare il lavoro di prelievo. Tutto il lavoro di spedizione verrà quindi assegnato al lavoratore. Per questo campo è richiesta la creazione di una voce di menu per utilizzare il lavoro esistente raggruppato dal sistema. Utilizzare il campo <strong>Etichetta di raggruppamento sistema</strong> per indicare al lavoratore gli elementi da scansionare. |
| Etichetta di raggruppamento sistema |                       Disponibile solo se <strong>Consenti lavoro di sistema</strong> è impostato su <strong>Sì</strong>. Immettere le informazioni per il lavoratore relative agli elementi da sottoporre a scansione quando viene raggruppato il lavoro di prelievo. Se ad esempio si utilizza il campo <strong>ID spedizione</strong> per raggruppare il lavoro di prelievo in base alla spedizione, è possibile immettere l'ID spedizione nel campo. Per questo campo è richiesta la creazione di una voce di menu per utilizzare il lavoro esistente raggruppato dal sistema. È inoltre necessario selezionare il campo in base a cui raggruppare nel campo <strong>Raggruppamento sistema</strong>.                       |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]