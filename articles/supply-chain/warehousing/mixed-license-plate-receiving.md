---
title: Ricevimento targa mista
description: "Questo argomento descrive come utilizzare Ricevimento targa mista per registrare e creare lavoro per più articoli con un dispositivo mobile."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ec3fdff6e1118f4a4ef4146d315fe8c58664f453
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="mixed-license-plate-receiving"></a>Ricevimento targa mista

[!INCLUDE [banner](../includes/banner.md)]

Ricevimento targa mista consente di creare una targa costituita da più articoli prima di registrare e creare lavoro di stoccaggio. 

Una targa costituita da più articoli non deve essere suddivisa alla banchina di entrata per registrare ogni articolo. 

Quando si utilizza un flusso correlato ad articoli per identificare le righe di documenti di origine, è possibile analizzare i codici a barre sul monitoraggio dell'articoloo. Se il codice a barre ha una quantità e un'unità di misura (UOM) configurati, l'articolo e la quantità verranno aggiunti automaticamente alla targa mista e si verrà reindirizzati alla schermata per analizzare un altro articolo. Ciò consente di analizzare rapidamente tutti gli articoli senza dover confermare a ogni passaggio. 

Nel flusso per Ricevimento targa mista, è possibile visualizzare l'elenco degli articoli già analizzati sulla targa e da qui modificare o correggere la quantità di un articolo.

## <a name="where-it-applies"></a>Dove si applica

Ricevimento targa mista è un flusso di ricevimento su dispositivo mobile che consente di registrare e creare lavoro per più righe/articoli contemporaneamente. Questa opzione è utile se si ricevono targhe in entrata con più articoli. 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a>Istruzioni per la configurazione di Ricevimento targa mista
Ricevimento targa mista viene configurato come voce di meno di un dispositivo mobile.

È necessario creare una nuova voce di menu contenente la modalità di lavoro che non utilizza lavoro esistente e utilizza uno dei seguenti metodi:

- Ricevimento targa mista
- Ricevimento e stoccaggio targa mista

Le opzioni per identificare righe di documenti di origine sono articolo ordine fornitore, riga ordine fornitore, ordine di reso, articolo ordine di trasferimento e riga di ordine di trasferimento. Queste opzioni possono modificare l'ordine di ricevimento per una singola targa. L'ultima opzione è per articolo caricato. È possibile aggiungere più articoli alla targa, ma non è possibile passare tra i diversi carichi.

