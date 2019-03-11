---
title: Gestisci tipi di codici a barre
description: Questa procedura mostra come impostare una nuova definizione di codice a barre che potrà quindi essere utilizzata come parte del report distinta di prelievo.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a0d7092228f078f528ec1cb9ac56d7034c44bccf
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "349701"
---
# <a name="maintain-barcode-types"></a>Gestisci tipi di codici a barre

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come impostare una nuova definizione di codice a barre che potrà quindi essere utilizzata come parte del report distinta di prelievo. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati. Se si utilizza USMF è possibile utilizzare i valori di esempio visualizzati. Queste attività verranno in genere svolte da un responsabile del magazzino.

1. Passare ai codici a barre.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Impostazione codice a barre.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Tipo di codice a barre selezionare un'opzione.
    * Se si utilizza USMF, è possibile selezionare 'Code 39'.  
6. Nel campo Dimensioni immettere un numero.
7. Nel campo Lunghezza massima immettere un numero.
8. Fare clic su Salva.
9. Chiudere la pagina.
10. Passare a Parametri di gestione articoli e magazzino.
11. Nel campo Impostazione codice a barre immettere o selezionare un valore.
    * Selezionare l'impostazione codice a barre creata prima, ma tenere presente che il formato di codice a barre deve corrispondere al formato dell'identificatore univoco per il tipo di record utilizzato nel processo. Ad esempio, per i cicli di prelievo, il formato di codice a barre deve corrispondere al formato di riferimento del ciclo di prelievo, che è in genere una sequenza numerica.  
12. Fare clic su Salva.
13. Chiudere la pagina.

