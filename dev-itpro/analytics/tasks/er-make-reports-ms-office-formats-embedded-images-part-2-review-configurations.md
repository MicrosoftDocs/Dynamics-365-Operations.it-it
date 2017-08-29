--- 
title: Verificare le configurazioni per creare i report nei formati Microsoft Office con immagini incorporate per la creazione di report elettronici (ER)
description: "Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella guida attività \"ER Creare report in formati di Microsoft Office con immagini incluse (Parte 1: Generare i report)\"."
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 21e73f9e7e3fbab4c62786e689f72127598d1961
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="review-configurations-to-make-reports-in-microsoft-office-formats-with-embedded-images-for-electronic-reporting-er"></a>Verificare le configurazioni per creare i report nei formati Microsoft Office con immagini incorporate per la creazione di report elettronici (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella guida attività "ER Creare report in formati di Microsoft Office con immagini incluse (Parte 1: Generare i report)".

In questa procedura viene illustrato come progettare le configurazioni ER per generare i documenti elettronici contenenti le immagini incorporate in Microsoft Excel e Microsoft Word. In questo esempio verranno esaminate le configurazioni ER per la società di esempio Litware, Inc. 

Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici. I passaggi possono essere completati mediante il set di dati USMF.


## <a name="review-the-imported-data-model"></a>Esaminare il modello dati importato
1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura selezionare "Model for cheques".
3. Fare clic su Progettazione.
    * Questo modello è progettato per rappresentare gli assegni di pagamento da un punto di vista aziendale e il mapping del modello alle origini dati dell'applicazione. Far esaminare il modello dal progettista delle operazioni ER. Si notino gli attributi degli elementi del modello presentati, ovvero struttura, nome, descrizione, tipo di dati e così via.   
4. Nella struttura espandere "root".
5. Nella struttura selezionare "root\cheques".
6. Nella struttura espandere "root\cheques".
7. Nella struttura espandere "root\cheques\attributes".
8. Nella struttura espandere "root\payer".
9. Nella struttura selezionare "root\istestrun".
10. Nella struttura selezionare "root\layout".
    * L'elemento layout del modello rappresenta i dettagli del layout del modulo dell'assegno di stampa per il conto bancario selezionato. Sono inoltre inclusi due nodi del tipo di dati Container per archiviare immagini.   
11. Nella struttura espandere "root\layout".
12. Nella struttura selezionare "root\layout\company logo".
13. Nella struttura espandere "root\layout\company logo".
14. Nella struttura selezionare "root\layout\company logo\image".
15. Nella struttura selezionare "root\layout\company logo\isprinted".
16. Nella struttura selezionare "root\layout\signature".
17. Nella struttura espandere "root\layout\signature".
18. Nella struttura selezionare "root\layout\signature\image".
19. Nella struttura selezionare "root\layout\signature\isprinted".
    * Si noti che due elementi del modello dati dell'immagine sono associati ai campi delle tabelle contenenti le immagini del logo della società e la firma della persona autorizzata in formato binario.  
20. Nella struttura espandere "root\layout\watermark".
21. Fare clic su Mappa modello a origine dati.
22. Fare clic su Progettazione.
23. Nella struttura espandere "chequesselected".
24. Nella struttura espandere "layout".
25. Nella struttura espandere "layout\company logo".
26. Nella struttura espandere "layout\signature".
27. Nella struttura espandere "layout\watermark".
28. Attivare 'Mostra dettagli'.
    * Si noti che l'elemento del modello dati degli assegni è associato alla tabella TmpChequePrintout che, in fase di esecuzione, contiene i record per gli assegni che l'utente ha selezionato per la stampa.   
29. Chiudere la pagina.
30. Chiudere la pagina.
31. Chiudere la pagina.

## <a name="review-the-imported-format"></a>Esaminare il formato importato
1. Nella struttura espandere "Model for cheques".
2. Nella struttura selezionare "Model for cheques\Cheques printing format".
3. Fare clic su Progettazione.
4. Fare clic su Allegati.
5. Fare clic su Apri.
    * Aprire il modello di report allegato in Excel.  
    * Esaminare il modello di Excel del report allegato che verrà utilizzato per stampare gli assegni. Il modello contiene due assegni per pagina ed è progettato per stampare gli assegni nel modulo prestampato. Si noti che sono incorporate due immagini vuote per il logo della società e la firma della persona che autorizza un pagamento. Verificare che le immagini siano denominate CompLogo e SignatureImage, rispettivamente, in Excel.   
6. Chiudere la pagina.
7. Nella struttura espandere "Report".
8. Nella struttura espandere "Report\ChequeLines".
9. Nella struttura selezionare "Report\ChequeLines\CompLogo".
10. Attivare 'Mostra dettagli'.
    * Si noti che l'elemento della cella in formato "CompLogo" rappresenta l'elemento di Excel utilizzato per inserire l'immagine del logo della società nel report. Questo elemento di formato è associato all'elemento del modello dati che, in fase di esecuzione, contiene un'immagine del logo della società in formato binario.   
11. Fare clic sulla scheda Mapping.
12. Fare clic su Modifica abilitata.
    * Si noti che è possibile creare l'elemento della cella del formato "CompLogo" in modo che non sia più abilitato. In questo caso, l'elemento immagine di Excel associato nasconderà il logo della società nel report generato. Se l'espressione attivata restituisce TRUE e l'associazione definita non è associata ad alcuna immagine, l'elemento immagine di Excel associato visualizzerà un'immagine che è stata salvata nel modello Excel.   
13. Chiudere la pagina.
14. Nella struttura espandere "labels: Container".
    * Alcune etichette presentate nel modulo dell'assegno prestampato verranno incluse nel report quando è creato a scopo di verifica. Tuttavia, le etichette non verranno stampate durante la stampa effettiva in quanto il modulo prestampato le include già.  
15. Chiudere la pagina.


