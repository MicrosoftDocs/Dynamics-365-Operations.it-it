---
title: Creare e acquisire cespiti dalla contabilità fornitori
description: In questa guida attività verrà illustrata la creazione e l'acquisizione di un cespite con il processo di acquisto.
author: saraschi2
manager: AnnBe
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b27ccc3b4c4f5470d3a5b8ed7347e269c6793b87
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976043"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Creare e acquisire cespiti dalla contabilità fornitori

[!include [banner](../../includes/banner.md)]

In questa guida attività verrà illustrata la creazione e l'acquisizione di un cespite con il processo di acquisto.  Vengono utilizzati l'addetto alla contabilità fornitori e il contabile e la società dimostrativa USMF.


## <a name="set-fixed-assets-parameters"></a>Impostare i parametri per i cespiti
1. Nel **pannello di navigazione**, andare a **Moduli > Cespiti > Impostazione > Parametri cespiti**.
2. Espandere la Scheda dettaglio **Ordini fornitore**.
3. Selezionare la casella di controllo **Consenti acquisizione cespiti da Acquisto**.
4. Selezionare la casella di controllo **Crea cespite durante la registrazione entrata prodotti o fattura**.

## <a name="create-a-new-vendor-invoice"></a>Crea una nuova fattura fornitore
1. Nel **pannello di navigazione** andare a **Moduli > Contabilità fornitori > Aree di lavoro > Inserimento fatture fornitore**.
2. Fare clic su **Nuova fattura fornitore**.
3. Nel campo **Conto fattura** fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Nel campo **Numero**, digitare un valore.
6. Immettere una data nel campo **Data registrazione**.
7. Fare clic su **Aggiungi riga**.
8. Nel campo **Numero articolo** fare clic sul pulsante a discesa per aprire la ricerca. Gli articoli non stoccati o le categorie di approvvigionamento possono essere utilizzati per l'acquisizione dei cespiti.  
9. Nell'elenco fare clic sul collegamento nella riga selezionata.
10. Nel campo **Quantità** immettere un numero. Una riga della fattura creerà solo un cespite, indipendentemente dalla quantità. Il valore del campo Quantità in fattura verrà trasferito in Quantità cespite.  
11. Immettere un numero nel campo **Prezzo unitario**.
12. Espandere la Scheda dettaglio **Dettagli riga**.
13. Fare clic sulla scheda **Cespiti**.
14. Selezionare la casella di controllo **Crea un nuovo cespite**.
15. Nel campo **Gruppo cespite** fare clic sul pulsante a discesa per aprire la ricerca.
16. In questo elenco selezionare il gruppo cespite da utilizzare quando si crea il nuovo cespite.
17. Nell'elenco fare clic sul collegamento nella riga selezionata.
18. Fare clic su **Registra**. Il cespite verrà creato e acquisito quando viene registrata la fattura.  

