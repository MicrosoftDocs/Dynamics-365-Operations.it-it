---
title: Creare un modello di fattura a testo libero
description: Questa procedura illustra come creare un modello di fattura a testo libero.
author: abruer
ms.date: 02/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7baa29ad341bdf7ff874bd7f69cf483b7afc075a
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8182511"
---
# <a name="create-a-free-text-invoice-template"></a>Creare un modello di fattura a testo libero

[!include [banner](../includes/banner.md)]

Per questa procedura utilizzare la società dimostrativa USMF. Questa procedura è destinata all'utente responsabile della gestione e dell'elaborazione delle fatture di CoCli.

## <a name="create-a-template"></a>Crea un modello

1. Andare a **Contabilità clienti > Fatture > Fatture ricorrenti > Modelli di fattura a testo libero**.
    * Utilizzare questa pagina per creare modelli di fattura a testo libero in cui possono essere incluse righe di fattura, spese, modelli di distribuzione contabile e informazioni sul conto CoGe.  
2. Fare clic su **Nuovo** per creare un nuovo modello di fattura a testo libero.
3. Digitare un valore nel campo **Nome modello**.
    * "Nome modello" identifica in modo univoco un modello di fattura a testo libero. Non due modelli possono avere lo stesso "nome modello".  
4. Nel campo **Descrizione** immettere una descrizione del modello.
5. Espandere la scheda **Righe fattura**.
6. Nel campo **Descrizione** immettere una descrizione della riga fattura.
7. Nel campo **Conto principale** selezionare un conto ricavi.
    * È possibile selezionare il conto transazioni di contropartita di un credito del cliente per l'importo totale della fattura nella pagina **Profili di registrazione cliente**.  
8. Nel campo **Fascia IVA** fare clic sul pulsante a discesa per aprire la ricerca.
    * La fascia IVA per la riga di fattura corrente corrisponde alla fascia IVA predefinita per il conto cliente.  
9. Nell'elenco fare clic sul collegamento nella riga selezionata.
10. Nel campo **Fascia IVA articoli** selezionare la fascia IVA articoli per la riga fattura corrente.
11. Nell'elenco fare clic sul collegamento nella riga selezionata.
12. Nel campo **Prezzo unitario** immettere o visualizzare il prezzo unitario per la riga fattura
    * Questo importo viene moltiplicato per il campo **Quantità** per determinare l'importo della riga di fattura.  
13. Aggiungere una nuova riga al modello di fattura a testo libero.
14. Nel campo **Descrizione** immettere una descrizione della riga fattura.
15. Nel campo **Conto principale** selezionare un conto ricavi.
    * È possibile selezionare il conto transazioni di contropartita di un credito del cliente per l'importo totale della fattura nella pagina **Profili di registrazione cliente**.  
16. Nel campo **Fascia IVA** fare clic sul pulsante a discesa per aprire la ricerca.
    * La fascia IVA per la riga di fattura corrente corrisponde alla fascia IVA predefinita per il conto cliente.  
17. Nell'elenco fare clic sul collegamento nella riga selezionata.
18. Nel campo **Fascia IVA articoli** fare clic sul pulsante a discesa per aprire la ricerca.
    * Fascia IVA articoli per la riga di fattura corrente.  
19. Nell'elenco fare clic sul collegamento nella riga selezionata.
20. Immettere o visualizzare il numero di unità per la riga di fattura.
    * Questo numero viene moltiplicato per il valore del campo Prezzo unitario per determinare l'importo della riga di fattura.  
21. Immettere o visualizzare il prezzo unitario della riga di fattura. 
    * Questo importo viene moltiplicato per il valore del campo **Quantità** per determinare l'importo della riga di fattura.  
22. Consente di visualizzare e modificare le distribuzioni contabili per una singola riga e tutte le righe figlio.
    * Le distribuzioni contabili definiscono il modo in cui un importo verrà conteggiato, ad esempio i ricavi, le tasse o le spese vengono conteggiate in una fattura a testo libero.  
23. Aggiorna le distribuzioni contabili per la riga fattura selezionata.
24. Fare clic su **Chiudi**.

## <a name="save-a-free-text-invoice-as-a-template"></a>Salvare un modello di fattura a testo libero
È inoltre possibile salvare una fattura a testo libero esistente come modello. Quando si seleziona **Salva come modello** dalla scheda **Fattura**, immettere un nome e una descrizione per il modello. Se un modello con il nome è già presente, vedrete una notifica in un modello con il nome esistente. È comunque possibile fare clic su **OK** per sostituirlo. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
