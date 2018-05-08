--- 
title: Crea una fattura a testo libero
description: "Questa guida attività dimostra la generazione di una fattura a testo libero."
author: mikefalkner
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ef3cad6538d9efbd1c1881f4b7d771382d9b1ba8
ms.openlocfilehash: 87e293008fd748aa0dcc6b3caa94a4889bed35de
ms.contentlocale: it-it
ms.lasthandoff: 10/26/2017

---
# <a name="create-a-free-text-invoice"></a>Crea una fattura a testo libero

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa guida attività dimostra la generazione di una fattura a testo libero. In questa attività viene utilizzata la società dimostrativa USMF.

1. Andare a Contabilità clienti > Fatture > Tutte le fatture a testo libero.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente selezionare un valore.
    * Il conto fatture verrà impostato sul conto utilizzato per il conto cliente.   
    * Lo stato iniziale della contabilità è In corso se la fattura non è registrata.   
    * Il numero fattura viene assegnato al momento della registrazione della fattura.  
    * Se si utilizzano i mandati SEPA, il mandato di addebito diretto verrà automaticamente popolato con un mandato, quando si seleziona il conto cliente.  
4. Nel campo Descrizione digitare un valore.
5. Nel campo Conto principale, specificare un numero di conto senza dimensioni.
    * È anche possibile immettere uno o più caratteri per il conto principale e utilizzare la ricerca per trovare il conto. Le dimensioni verranno immesse successivamente nella guida.  
6. Espandere la scheda dettaglio Dettagli riga in modo da poter aggiungere dimensioni al conto principale.
7. Fare clic sulla scheda Riga dimensioni finanziarie.
    * Le dimensioni sono relative solo alla riga selezionata.    
    * La fascia IVA viene popolata dal cliente. Se il cliente non dispone di una fascia IVA, viene utilizzata la fascia IVA del conto principale.  
    * La fascia IVA articoli viene popolata dal conto principale. Se il conto principale non dispone di una fascia IVA articoli, viene utilizzata quella dei parametri IVA di contabilità generale.    
8. Nel campo Quantità immettere un numero.
    * La quantità è facoltativa.  
9. Nel campo Prezzo unitario immettere un numero.
    * Il prezzo unitario è facoltativo.  
    * L'importo è calcolato come quantità per prezzo unitario. Tuttavia è possibile ignorare questo calcolo e immettere un importo.  
10. Fare clic su IVA per visualizzare l'IVA calcolata per la fattura.
    * Visualizzare gli importi IVA nella pagina o ignorare gli importi nella scheda Rettifica.  
11. Fare clic su OK.
12. Fare clic su Spese per aggiungere una spesa alla fattura. 
13. Digitare un valore nel campo Codice spese.
14. Nel campo Valore spese immettere un numero.
15. Chiudere la pagina.
16. Fare clic su Totali per visualizzare il riepilogo dei totali e dei dettagli della fattura.
17. Fare clic su Chiudi.
18. Scegliere Registra per registrare la fattura. Sarà possibile annullare prima di registrare.
    * Per modificare il tempo di stampa delle fatture: selezionare Corrente per stampare ciascuna fattura non appena viene aggiornata oppure selezionare Dopo per stampare dopo che tutte le fatture sono state aggiornate.  
    * Se si desidera modificare la modalità in cui il limite di credito del cliente viene verificato prima della registrazione, modificare il tipo di limite di credito.  
    * Se si desidera stampare la fattura, selezionare Sì.  
    * Se si desidera registrare la fattura selezionare Sì. È possibile stampare la fattura senza registrare.  
19. Fare clic su OK.


