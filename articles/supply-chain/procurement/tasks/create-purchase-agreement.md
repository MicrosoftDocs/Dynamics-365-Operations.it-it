---
title: Creare un contratto di acquisto
description: In questo argomento viene descritta la creazione di un contratto di acquisto
author: mkirknel
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec792ca27bf0245ff25e59cfe28122f17caec7fc
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2019
ms.locfileid: "1866852"
---
# <a name="create-a-purchase-agreement"></a>Creare un contratto di acquisto

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questo argomento viene descritta la creazione di un contratto di acquisto e viene in genere effettuata da un responsabile acquisti. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. È necessario impostare le classificazioni del contratto di acquisto prima di iniziare. Una volta creato un contratto, è possibile utilizzarlo quando si crea un ordine fornitore. In questo modo le condizioni del contratto di acquisto verranno copiate nell'intestazione e in tutte le righe nell'ordine in cui sono interessate dal contratto.


## <a name="create-a-new-purchase-agreement"></a>Creare un nuovo contratto di acquisto
1. Andare a **Pannello di navigazione > Moduli > Approvvigionamento > Contratti di acquisto > Contratti di acquisto**.
2. Fare clic su **Nuovo**.
3. Nel campo **Conto fornitore**, selezionare il menu a discesa e selezionare la riga del record desiderato.
4. Nel campo **Classificazione contratto di acquisto**, selezionare il menu a discesa e selezionare la riga del record desiderato.
5. Espandere la Scheda dettaglio **Generale**.
6. Nel campo **Data di scadenza** immettere una data.

    - La data di scadenza verrà impostata per tutti le righe di impegno e determinerà il periodo di validità di ogni impegno specifico.  

7. Nel campo **Titolo documento** digitare un nome per il contratto di acquisto.

    - Lasciare il campo **Impegno predefinito** impostato su **Impegno quantità prodotto** o modificarlo se non è impostato su tale valore.  
    - Il valore di impegno predefinito determina le opzioni nelle righe del contratto. Se è necessarie un nuovo tipo di impegno durante la creazione delle righe del contratto, è necessario modificare l'impegno predefinito nell'intestazione. Sono presenti i 4 tipi di impegni seguenti. **Impegno quantità prodotto** - per una specifica quantità di prodotto, **Impegno valore prodotto** - per un importo in valuta specifico del prodotto, **Impegno valore categoria prodotto** - per un importo in valuta specifico in una categoria di approvvigionamento in cui l'importo può essere correlato a un articolo del catalogo oppure a un articolo fuori catalogo, **Impegno valore** - per un importo in valuta specifico che può essere soddisfatto da qualsiasi prodotto o da qualsiasi categoria di approvvigionamento.  

8. Selezionare **OK**.

## <a name="add-a-commitment"></a>Aggiungere un impegno
1. Selezionare **Aggiungi riga**.
2. Nel campo **Numero articolo** fare clic sul record desiderato del menu a discesa.
3. Nel campo **Quantità** immettere un numero. Si tratta della quantità totale accettata per l'acquisto dal fornitore.  
4. Immettere un numero nel campo **Prezzo unitario**.
5. Espandere la sezione **Dettagli riga**.
6. Impostare l'opzione **Valore massimo applicato** su **Sì**. L'opzione **Valore massimo applicato** limita l'utilizzo dell'impegno. È possibile acquistare una quantità pari al massimo al valore specificato nel campo **Quantità** per la riga.  

## <a name="add-header-conditions"></a>Aggiungere condizioni di intestazione
1. Nel riquadro azioni selezionare **Opzioni**.
2. Selezionare **Cambia visualizzazione**.
3. Selezionare **Visualizzazione intestazione**.
4. Espandere la sezione **Termini**.
5. Nel campo **Metodo di pagamento** fare clic sul record desiderato del menu a discesa. I termini di pagamento del conto fornitore vengono visualizzati in questo punto per impostazione predefinita.  
6. Nel campo **Modalità di consegna** fare clic sul record desiderato del menu a discesa.
7. Nel campo **Termini di consegna** fare clic sul pulsante a discesa per aprire la ricerca.

## <a name="confirm-and-activate-the-agreement"></a>Confermare e attivare il contratto
1. Nel riquadro azioni fare clic su **Contratto di acquisto**.
2. Selezionare **Conferma**. Impostare l'opzione **Contrassegna contratto come valido** su **Sì**.  
3. Selezionare **OK**.
4. Nel riquadro azioni fare clic su **Contratto di acquisto**.
5. Selezionare **Conferme contratto di acquisto**. L'opzione **Anteprima/Stampa** consente di generare un documento per il contratto di acquisto che successivamente è possibile stampare o inviare al fornitore. Se in seguito si aggiorna il contratto e lo si riconferma, entrambe le versioni verranno visualizzate in questo punto.  
6. Chiudere la pagina.

