---
title: Elaborare sconti per il pagamento
description: Questa procedura mostra come convertire gli sconti del cliente approvati ed elaborati in note di accredito.
author: omulvad
manager: tfehr
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e2e9af7167e4a4209b708d00493b8866f6d5f7e0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209929"
---
# <a name="process-rebates-for-payment"></a>Elaborare sconti per il pagamento

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come convertire gli sconti del cliente approvati ed elaborati in note di accredito. È possibile utilizzare questa guida nella società dimostrativa USMF. L'assunto per la guida è di avere uno o più richieste di sconto con stato Contrassegna. Se si utilizza USMF, è necessario eseguire la guida "Generare ed elaborare gli sconti cliente" prima di iniziare questa guida.


## <a name="convert-rebate-claims-to-credit-note"></a>Convertire le richieste di sconto in nota di accredito
1. Scegliere Tutti i clienti.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nel riquadro azioni fare clic su Raccolta.
5. Fare clic su Liquida transazioni.
6. Fare clic su Funzioni.
7. Fare clic su Programma sconti.
    * La pagina degli sconti include le richieste di sconto elaborate nel workbench degli sconti del cliente e che sono con stato Contrassegna.    
8. Fare clic su Modifica.
    * Impostare i segni di spunta nel campo Contrassegna per le richieste da includere nella nota di accredito.   
9. Fare clic su Funzioni.
10. Fare clic su Crea nota di accredito.
    * Viene visualizzato un messaggio per informare che è stato registrato un giornale di registrazione (questo è il giornale di registrazione relativo all'utilizzo di Contabilità clienti, come specificato nella pagina dei parametri di Contabilità clienti). Ciò causa il trasferimento dell'importo effettivo di passività (credito) nel saldo del cliente. Significa che sono stati effettuati un accredito sul conto del cliente e un addebito sul conto ratei sconto.  
11. Chiudere la pagina.
12. Scegliere Annulla.
    * In questo modo viene aggiornata la pagina e sono visibili gli aggiornamenti.  
13. Nel riquadro azioni fare clic su Raccolta.
14. Fare clic su Liquida transazioni.
    * Si noti che una transazione dall'importo negativo, rappresentante l'importo totale dello sconto, senza riferimento alla fattura è stata aggiunta al saldo del cliente.   
15. Scegliere Annulla.

