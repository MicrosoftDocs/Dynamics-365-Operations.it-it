--- 
title: Immettere contratti di vendita
description: In questa procedura vengono descritti i passaggi per creare un contratto di vendita con cui un cliente si impegna ad acquistare un prodotto per un importo concordato in cambio di sconti speciali.
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a1c4b7623f3409d4474adcd04fb1331b944b9fbb
ms.openlocfilehash: a0d49068d2c6a62bf7912c2fd7cccd53308bd196
ms.contentlocale: it-it
ms.lasthandoff: 02/13/2018

---
# <a name="enter-sales-agreements"></a>Immettere contratti di vendita

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per creare un contratto di vendita con cui un cliente si impegna ad acquistare un prodotto per un importo concordato in cambio di sconti speciali. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.


## <a name="set-up-sales-agreement-header"></a>Impostare l'intestazione del contratto di vendita
1. Passare a Vendite e marketing > Contratti di vendita > Contratti di vendita.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.
4. Trovare e selezionare il record desiderato nell'elenco.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Nel campo Classificazione contratto di vendita fare clic sul pulsante a discesa per aprire la ricerca.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Espandere la sezione Generale.
9. Nel campo Impegno predefinito, selezionare 'Impegno valore prodotto'.
    * Un tipo di impegno è un criterio obbligatorio che è necessario assegnare al contratto per definire la modalità di evasione del contratto. I quattro tipi predefiniti consentono di impostare la destinazione dell'impegno del cliente, espressa come quantità o valore. Il tipo di impegno di quantità può applicarsi a un solo prodotto specifico, ma i tipi di valore sono applicabili alle vendite di prodotti specifici e non specifici.  
10. Nel campo Data di scadenza, impostare una data futura per la scadenza del contratto.
11. Fare clic su OK.

## <a name="set-up-product-value-commitment-lines"></a>Impostare le righe di impegno valore prodotto
1. Fare clic su Aggiungi riga.
2. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
3. Nell'elenco trovare e selezionare il record desiderato.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Il tipo di impegno scelto per il contratto influisce sul tipo di informazioni che è possibile immettere per le righe del contratto. Ad esempio, per un contratto in base al valore è necessario specificare l'importo netto totale (nella valuta concordata) per il quale il cliente si impegna ad acquistare beni dall'utente. In questo esempio i campi Unità e Quantità nella riga non sono disponibili perché si sta creando un contratto per cui il cliente compra un valore specifico di un prodotto.   
5. Nel campo Importo netto, immettere l'importo monetario che il cliente si è impegnato ad acquistare.
6. Nel campo Percentuale sconto, immettere un valore in percentuale da applicare alle righe dell'ordine cliente collegate a questo contratto.
7. Espandere la sezione Dettagli riga.
8. Selezionare Sì nel campo Valore massimo applicato.
    * Selezionare Valore massimo applicato per indicare che l'importo totale di tutte le righe ordine cliente che utilizzano i prezzi speciali, gli sconti e/o i termini di pagamento dell'impegno non deve superare l'importo specificato nell'impegno.  
    * Gli importi di rilascio minimo e massimo specificano un intervallo di valori che devono essere venduti in ogni ordine cliente che utilizza il contratto selezionato.   
9. Espandere la sezione Intestazione contratto di vendita.
    * A meno che lo stato del contratto non sia impostato su Validità, gli ordini cliente non possono essere associati al contratto e pertanto non possono contribuire all'evasione del contratto. È possibile modificare lo stato manualmente in questa fase. Tuttavia, lo stato in genere viene modificato quando si conferma il contratto per il cliente.  
10. Nel riquadro azioni, fare clic su Contratto di vendita.
11. Fare clic su Conferma.
    * Verificare che l'opzione Contrassegna contratto come valido sia impostata su Sì.  
12. Selezionare Sì nel campo Stampa report.
13. Fare clic su OK.
14. Chiudere la pagina.
    * Il contratto è ora effettivo ed è possibile avviare il collegamento degli ordini cliente al contratto, da compensare a fronte della destinazione impegnata.  


