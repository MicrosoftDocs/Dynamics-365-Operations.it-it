---
title: Creare e gestire un blocco scorte
description: Questa procedura illustra come impedire che scorte fisiche disponibili vengano prenotate da altri documenti di origine in uscita tramite il blocco scorte.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 09789dc0b89f8bd36cca9b3e5be366bf17246243
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "322262"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Creare e gestire un blocco scorte

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura illustra come impedire che scorte fisiche disponibili vengano prenotate da altri documenti di origine in uscita tramite il blocco scorte. È possibile eseguire la procedura utilizzando la società di dati dimostrativi USMF con i valori di esempio visualizzati. È necessario disporre di un articolo con scorte disponibili fisiche disponibili prima di iniziare questa procedura.


## <a name="create-an-inventory-blocking"></a>Creare un blocco scorte
1. Andare a Gestione articoli > Attività periodiche > Blocco scorte.
2. Fare clic su Nuovo.
3. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
4. Selezionare dall'elenco l'articolo da scegliere. 
    * Selezionare un numero di articolo con scorte fisiche disponibili che si desidera bloccare. Se si utilizza USMF, è possibile selezionare l'articolo M9201.  
5. Nel campo Quantità immettere un numero.
    * Se si utilizza l'articolo M9201, è necessario selezionare un valore inferiore a 200.  
6. Attivare/disattivare l'espansione della sezione Dimensioni inventariali.
7. Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.
8. Nell'elenco trovare e selezionare il record desiderato.
    * Se si utilizza l'articolo M9201, è possibile selezionare il magazzino 51.  
9. Fare clic su Salva.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Aggiornare le condizioni del blocco scorte
1. Nel campo Quantità immettere un numero.
    * Aggiornare il campo quantità in magazzino in base alla quantità da bloccare.  
2. Nel campo Data prevista immettere una data.
    * Potrebbe essere utile indicare il momento in cui si prevede che le scorte bloccate diventino disponibili per la prenotazione assegnando una data prevista. Se l'opzione Entrate previste è selezionata per il blocco scorte, impostazione predefinita quando si crea manualmente un blocco, tale data verrà visualizzata sulla transazione prevista.  
3. Fare clic su Salva.

## <a name="remove-the-inventory-blocking"></a>Rimuovere il blocco scorte
1. Fare clic su Elimina.
2. Fare clic su Sì.
3. Chiudere la pagina.

