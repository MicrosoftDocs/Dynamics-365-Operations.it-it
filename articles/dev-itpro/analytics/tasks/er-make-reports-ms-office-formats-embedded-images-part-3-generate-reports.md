---
title: Generare report in formato di Office con immagini incorporate
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore di report elettronici può progettare configurazioni ER per generare documenti elettronici in formato MS Office (Excel e Word) contenenti immagini incorporate.
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ef7ec2f8b5b7fdf456ebb71b863e620ae21e6b5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544379"
---
# <a name="generate-reports-in-office-format-that-have-embedded-images"></a>Generare report in formato di Office con immagini incorporate

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore di report elettronici può progettare configurazioni ER per generare documenti elettronici in formato MS Office (Excel e Word) contenenti immagini incorporate.

In questo esempio verranno create configurazioni ER per la società di esempio Litware, Inc.  Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella guida attività "ER Creare report in formati di Microsoft Office con immagini incluse (Parte 2: Esaminare le configurazioni)". Queste operazioni possono essere eseguite nella società "USMF".


## <a name="run-format-with-initial-model-mapping"></a>Eseguire il formato con il mapping di modello iniziale
1. Andare a Gestione cassa e banche > Conti bancari > Conti bancari.
2. Utilizzare il filtro rapido per applicare un filtro al campo Conto bancario in base al valore "USMF OPER".
3. Nel riquadro azioni, fare clic su Imposta.
4. Fare clic su Verifica.
5. Fare clic su Stampa di prova.
    * Eseguire il formato a scopo di verifica.  
6. Selezionare Sì nel campo Formato assegno negoziabile.
7. Fare clic su OK.
    * Esaminare l'output creato. Si noti che il logo della società viene visualizzato nel report così come la firma della persona autorizzata. L'immagine della firma viene ricavata dal tipo di dati "Container" del record del layout dell'assegno associato al conto bancario selezionato.  
8. Espandere la sezione Copie.
9. Fare clic su Modifica.
10. Nel campo Filigrana, immettere "Stampa filigrana come Annulla".
    * Modificare l'impostazione del layout della filigrana per visualizzare il testo della filigrana nella generazione di documenti in un elemento forma di Excel.  
11. Fare clic su Stampa di prova.
12. Fare clic su OK.
    * Esaminare l'output creato. Si noti che la filigrana viene visualizzata nel report creato in base all'opzione selezionata.  
13. Chiudere la pagina.
14. Nel riquadro azioni, fare clic su Gestisci pagamenti.
15. Fare clic su Assegni.
16. Fare clic su Mostra filtri.
17. Applicare i filtri seguenti, immettendo un valore di filtro pari a "381","385","389" nel campo del numero di assegno utilizzando l'operatore "è uno di".
18. Nell'elenco selezionare tutte le righe.
19. Fare clic su Stampa copia assegno.
    * Eseguire il formato per ristampare gli assegni selezionati.  
    * Esaminare l'output creato. Si noti che gli assegni selezionati sono stati ristampati. Il logo e le etichette delle società non verranno stampati perché sono visualizzati nel modulo prestampato.  

## <a name="modify-the-mapping-of-the-imported-data-model"></a>Modificare il mapping del modello dati importato
1. Chiudere la pagina.
2. Chiudere la pagina.
3. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
4. Nella struttura selezionare "Model for cheques".
5. Fare clic su Progettazione.
6. Fare clic su Mappa modello a origine dati.
7. Fare clic su Progettazione.
    * Cambieremo l'associazione dell'elemento di firma del modello dati per ottenere l'immagine della firma del file che è stato collegato al record del layout di assegno associato al conto bancario selezionato.  
8. Disattivare la visualizzazione dei dettagli.
9. Nella struttura espandere "layout".
10. Nella struttura espandere "layout\signature".
11. Nella struttura selezionare "layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp".
12. Nella struttura espandere "chequesaccount".
13. Nella struttura espandere "chequesaccount\<Relations".
14. Nella struttura espandere "chequesaccount\<Relations\BankChequeLayout".
15. Nella struttura espandere "chequesaccount\<Relations\BankChequeLayout\<Relations".
16. Nella struttura espandere "chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents".
17. Nella struttura selezionare "chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()".
18. Fare clic su Associa.
19. Fare clic su Salva.
20. Chiudere la pagina.
21. Chiudere la pagina.
22. Chiudere la pagina.
23. Chiudere la pagina.

## <a name="run-format-using-the-adjusted-model-mapping"></a>Eseguire il formato utilizzando il mapping del modello modificato
1. Andare a Gestione cassa e banche > Conti bancari > Conti bancari.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare nel campo Conto bancario in base a un valore "USMF OPER".
3. Nel riquadro azioni, fare clic su Imposta.
4. Fare clic su Verifica.
5. Fare clic su Stampa di prova.
6. Fare clic su OK.
    * Esaminare l'output creato. Si noti che l'immagine dall'allegato di gestione documenti viene inviata come firma di una persona autorizzata.  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a>Utilizzare il documento di Microsoft Word come modello nel formato importato
1. Chiudere la pagina.
2. Chiudere la pagina.
3. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
4. Nella struttura espandere "Model for cheques".
5. Nella struttura selezionare "Model for cheques\Cheques printing format".
6. Fare clic su Progettazione.
7. Fare clic su Allegati.
8. Fare clic su Elimina.
9. Fare clic su Sì.
10. Fare clic su Nuovo.
11. Fare clic su File.
    * Fare clic su Sfoglia e selezionare il file modello di assegno in formato Word scaricato in precedenza.  
12. Chiudere la pagina.
13. Nel campo Modello immettere o selezionare un valore.
14. Fare clic su Salva.
15. Chiudere la pagina.
16. Fare clic su Modifica.
17. Selezionare Sì nel campo Esegui bozza.
18. Chiudere la pagina.
19. Andare a Gestione cassa e banche > Conti bancari > Conti bancari.
20. Utilizzare il filtro rapido per applicare un filtro al campo Conto bancario in base al valore "USMF OPER".
21. Fare clic su Verifica.
22. Fare clic su Stampa di prova.
23. Fare clic su OK.
    * Esaminare l'output creato. Si noti che l'output è stato generato come documento di Microsoft Word con immagini incorporate che presentano il logo della società, la firma di una persona autorizzata e il testo selezionato della filigrana.  

