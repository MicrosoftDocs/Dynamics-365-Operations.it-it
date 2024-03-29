---
title: EUR-00012 - Emettere un certificato di entrata UE
description: Questa procedura consente di abilitare un certificato di entrata UE, configurando un conto cliente per utilizzare i certificati di entrata e rilasciare un certificato.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, CustTable, SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CustEntryCertificateJour_W, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 41ede621fdb36d39efc79788cd2da77aacfc282895dd84d572b99f4528456643
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768238"
---
# <a name="eur-00012-issue-an-eu-entry-certificate"></a>EUR-00012 - Emettere un certificato di entrata UE

[!include [banner](../../includes/banner.md)]
Questa procedura consente di abilitare un certificato di entrata UE, configurando un conto cliente per utilizzare i certificati di entrata e rilasciare un certificato. Questa procedura è stata creata utilizzando la società di dati dimostrativi DEMF.


## <a name="enable-entry-certificate-management"></a>Abilita gestione certificati di entrata
1. Andare a a Contabilità clienti > Impostazioni > Parametri contabilità clienti.
2. Fare clic sulla scheda Spedizioni.
3. Espandere la sezione Certificato di entrata.
4. Selezionare Sì nel campo Abilita gestione certificati di entrata.
5. Selezionare Sì nel campo Abilita rilascio certificato di entrata.
6. Fare clic sulla scheda Sequenze numeriche.
7. Nell'elenco trovare e selezionare la riga Certificato di entrata.
8. Nel campo Codice sequenza numerica immettere o selezionare un valore.

## <a name="set-up-a-customer"></a>Impostare un cliente
1. Andare a Contabilità clienti > Clienti > Tutti i clienti.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare nel campo Conto con un valore "DE-015".
3. Aprire i dettagli del conto cliente.
4. Fare clic su Modifica.
5. Espandere la sezione Fattura e consegna.
6. Selezionare Sì nel campo Certificato di entrata obbligatorio.
7. Selezionare Sì nel campo Rilascia certificato di entrata.
8. Fare clic su Salva.

## <a name="create-an-eu-entry-certificate-automatically"></a>Creare automaticamente un certificato di entrata UE
1. Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente, immettere o selezionare un valore.
4. Fare clic su OK.
5. Nel campo Numero di articoli immettere o selezionare un valore.
6. Fare clic su Salva.
7. Nel riquadro azioni fare clic su Preleva e imballa.
8. Fare clic su Registra documento di trasporto.
9. Espandere la sezione Parametri.
10. Nel campo Quantità selezionare "Tutto".
11. Deselezionare la casella di controllo Rilascia certificato di entrata.
    * Un certificato di entrata può essere rilasciato durante la registrazione del documento di trasporto o durante la fatturazione dell'ordine. Lasciare la casella di controllo Rilascia certificato di entrata deselezionata per rilasciarlo successivamente.  
12. Fare clic su OK.
13. Fare clic su OK.
14. Nel riquadro azioni fare clic su Fattura.
15. Fare clic su Fattura.
    * Verificare che le caselle di controllo Certificato di entrata obbligatorio e Rilascia certificato di entrata nella sezione Panoramica siano selezionate.  È inoltre possibile selezionare la casella di controllo Stampa certificato di entrata per consentire la stampa del certificato.  
16. Fare clic su OK.
17. Fare clic su OK.
18. Nel riquadro azioni fare clic su Fattura.
19. Fare clic su Fattura.
20. Nel riquadro azioni fare clic su Fattura.
21. Fare clic su Visualizza certificati di entrata rilasciati.
22. Fare clic su Stampa.
23. Chiudere la pagina.
24. Fare clic su Cambia stato.
25. Selezionare un'opzione nel campo Nuovo stato.
26. Fare clic su OK.
27. Chiudere la pagina.

## <a name="create-an-eu-entry-certificate-manually"></a>Creare manualmente un certificato di entrata UE
1. Nel riquadro azioni fare clic su Fattura.
2. Fare clic su Crea certificato di entrata.
3. Fare clic su OK.
4. Nel riquadro azioni fare clic su Fattura.
5. Fare clic su Visualizza certificati di entrata rilasciati.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]