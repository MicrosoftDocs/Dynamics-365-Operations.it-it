---
title: Registrare gli articoli per un articolo abilitato a immagazzinaggio base usando un giornale di registrazione arrivi articoli
description: Questa procedura mostra come registrare gli articoli utilizzando il giornale di registrazione arrivi articoli quando si utilizza la funzionalità di "gestione magazzino di base" nel modulo Gestione articoli.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, WMSJournalTable, WMSJournalCreate, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f5f1afae08344a096c582c059e44b7ecf3e29606
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216967"
---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-an-item-arrival-journal"></a>Registrare gli articoli per un articolo abilitato a immagazzinaggio base usando un giornale di registrazione arrivi articoli

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come registrare gli articoli utilizzando il giornale di registrazione arrivi articoli quando si utilizza la funzionalità di "gestione magazzino di base" nel modulo Gestione articoli. Questa operazione viene generalmente effettuata da un addetto al ricevimento. È possibile eseguire questa procedura utilizzando la società di dati dimostrativi USMF con i valori di esempio visualizzati.  Se non si utilizza USMF, è necessario disporre di un ordine fornitore confermato con una riga ordine fornitore aperta prima di iniziare questa guida. L'articolo nella riga deve essere stoccato. L'articolo deve essere associato a un gruppo di dimensioni di immagazzinamento in cui sito e magazzino siano attivi.


## <a name="create-item-arrival-journal-header"></a>Creare un'intestazione di giornale di registrazione arrivi articoli
1. Andare a Gestione articoli > Inserimenti nel giornale di registrazione > Arrivo articoli > Arrivo articoli.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
    * Se si utilizza USMF, è possibile digitare WHS. Se si utilizzano altri dati, il giornale di registrazione di cui è stato scelto il nome deve avere le proprietà Verifica ubicazione prelievo e Gestione quarantena impostate su No.  
4. Digitare un valore nel campo Documento di trasporto.
    * Si tratta dell'ID del documento di trasporto rilasciato dal fornitore. Aggiungere un numero univoco.  
5. Nel campo Numero selezionare l'ordine fornitore.
6. Fare clic su OK.

## <a name="add-lines-to-item-arrival-journal"></a>Aggiungere righe a un giornale di registrazione arrivi articoli
1. Fare clic su Funzioni.
2. Fare clic su Crea righe.
    * Le righe possono essere immesse manualmente nel giornale di registrazione o essere create automaticamente. Verrà indicato come crearle automaticamente.  
3. Selezionare o deselezionare la casella di controllo Inizializza quantità.
    * In questo modo verrà inizializzata la quantità nelle righe del giornale di registrazione con la quantità non registrata dalla riga ordine fornitore.  
4. Fare clic su OK.

## <a name="post-the-journal"></a>Registra il giornale
1. Fare clic su Registra.
2. Fare clic su OK.

## <a name="generate-the-product-receipt"></a>Generare l'entrata prodotti
1. Fare clic su Funzioni.
2. Fare clic su Entrata prodotti.
3. Fare clic su OK.

