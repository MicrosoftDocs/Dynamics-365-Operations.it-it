---
title: Immettere contratti di vendita
description: In questo argomento viene descritto come creare un contratto di vendita con cui un cliente si impegna ad acquistare un prodotto per un importo concordato in cambio di sconti speciali.
author: omulvad
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7699f426c102b4ae2610db0851ddd127e514b652
ms.sourcegitcommit: 6545bef4584d72dd7789f2d3935cf00ac8f489b0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "1871031"
---
# <a name="enter-sales-agreements"></a>Immettere contratti di vendita

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questo argomento viene descritto come creare un contratto di vendita con cui un cliente si impegna ad acquistare un prodotto per un importo concordato in cambio di sconti speciali. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.


## <a name="set-up-sales-agreement-header"></a>Impostare l'intestazione del contratto di vendita
1. Nel pannello di navigazione, andare a **Moduli > Vendite e marketing > Contratti di vendita > Contratti di vendita**.
2. Selezionare **Nuovo**.
3. Nel campo **Conto cliente** selezionare il record desiderato nel menu a discesa.
4. Nel campo **Classificazione contratto di vendita** selezionare il record desiderato nel menu a discesa.
5. Espandere la sezione **Generale**.
6. Nel campo **Impegno predefinito**, selezionare **Impegno valore prodotto**. Un tipo di impegno è un criterio obbligatorio che è necessario assegnare al contratto per definire la modalità di evasione del contratto. I quattro tipi predefiniti consentono di impostare la destinazione dell'impegno del cliente, espressa come quantità o valore. Il tipo di impegno di quantità può applicarsi a un solo prodotto specifico, ma i tipi di valore sono applicabili alle vendite di prodotti specifici e non specifici.  
7. Nel campo **Data di scadenza**, impostare una data futura per la scadenza del contratto.
8. Selezionare **OK**.

## <a name="set-up-product-value-commitment-lines"></a>Impostare le righe di impegno valore prodotto
1. Selezionare **Aggiungi riga**.
2. Nel campo **Numero articolo** fare clic sul record desiderato del menu a discesa. Il tipo di impegno scelto per il contratto influisce sul tipo di informazioni che è possibile immettere per le righe del contratto. Ad esempio, per un contratto in base al valore è necessario specificare l'importo netto totale (nella valuta concordata) per il quale il cliente si impegna ad acquistare beni dall'utente. In questo esempio i campi **Unità** e **Quantità** nella riga non sono disponibili perché si sta creando un contratto per cui il cliente compra un valore specifico di un prodotto.   
3. Nel campo **Importo netto**, immettere l'importo monetario che il cliente si è impegnato ad acquistare.
4. Nel campo **Percentuale sconto**, immettere un valore in percentuale da applicare alle righe dell'ordine cliente collegate a questo contratto.
5. Espandere la sezione **Dettagli riga**.
6. Selezionare **Sì** nel campo **Valore massimo applicato**.
    - Selezionare **Valore massimo applicato** per indicare che l'importo totale di tutte le righe ordine cliente che utilizzano i prezzi speciali, gli sconti e/o i termini di pagamento dell'impegno non deve superare l'importo specificato nell'impegno.  
    - Gli importi di rilascio minimo e massimo specificano un intervallo di valori che devono essere venduti in ogni ordine cliente che utilizza il contratto selezionato.   
7. Espandere la sezione **Intestazione contratto di vendita**. A meno che lo stato del contratto non sia impostato su **Validità**, gli ordini cliente non possono essere associati al contratto e pertanto non possono contribuire all'evasione del contratto. È possibile modificare lo stato manualmente in questa fase. Tuttavia, lo stato in genere viene modificato quando si conferma il contratto per il cliente.  
8. Nel riquadro azioni, selezionare **Contratto di vendita**.
9. Selezionare **Conferma**. Verificare che l'opzione **Contrassegna contratto come valido** sia impostata su **Sì**.  
10. Selezionare **Sì** nel campo **Stampa report**.
11. Selezionare **OK**.
12. Chiudere la pagina. Il contratto è ora effettivo. È possibile avviare il collegamento degli ordini cliente al contratto, da compensare a fronte della destinazione impegnata.  

