---
title: ER Mapping dei componenti del formato creato agli elementi del modello dati (novembre 2016)
description: Nella seguente procedura viene illustrato come un utente con il ruolo di amministratore di sistema o sviluppatore per la creazione di report elettronici può eseguire il mapping di elementi del modello dati ai componenti della configurazione creazione di report elettronici (ER), che definisce un formato di documento elettronico per il dominio aziendale dei pagamenti.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 109a6736196b6ed3d1445a9f1a70c5f2b9d5af58
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684333"
---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a>ER Mapping dei componenti del formato creato agli elementi del modello dati (novembre 2016)

[!include [banner](../../includes/banner.md)]

Nella seguente procedura viene illustrato come un utente con il ruolo di amministratore di sistema o sviluppatore per la creazione di report elettronici può eseguire il mapping di elementi del modello dati ai componenti della configurazione creazione di report elettronici (ER), che definisce un formato di documento elettronico per il dominio aziendale dei pagamenti. Questo formato verrà utilizzato in seguito per generare documenti elettronici per l'elaborazione dei pagamenti. In questo esempio, verrà creata una configurazione di formato per la società di esempio "Litware, Inc.". Queste operazioni possono essere eseguite in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società. Per completare questi passaggi, è necessario aver completato prima i passaggi della guida attività "Creare una configurazione di formato".


## <a name="select-a-format-configuration"></a>Selezionare una configurazione di formato
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Fare clic su Configurazioni report.
3. Nella struttura espandere "Pagamenti (modello semplificato)".
4. Nella struttura selezionare "Pagamenti (modello semplificato)\BACS (fittizia per Regno Unito)".
5. Fare clic su Progettazione.

## <a name="map-format-components-to-data-model-elements"></a>Esegue il mapping dei componenti del formato a elementi del modello dati
1. Fare clic su Espandi/Comprimi.
2. Fare clic sulla scheda Mapping.
3. Nella struttura , espandere il "modello".
4. Nella struttura selezionare 'Xml\Messaggio\ProcessingDate\DateTime'.
5. Nella struttura selezionare 'modello\ProcessingDateTime'.
6. Fare clic su Associa.
7. Nella struttura selezionare 'Xml\Messaggio\MessageId\Stringa'.
8. Nella struttura selezionare 'modello\MessageIdentification'.
9. Fare clic su Associa.
10. Nella struttura espandere "modello\Pagamenti".
11. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Importo\Stringa'.
12. Nella struttura selezionare 'modello\Pagamenti\InstructedAmount'.
13. Fare clic su Associa.
14. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\TransDate\DateTime'.
15. Nella struttura selezionare 'modello\Pagamenti\TransactionDate'.
16. Fare clic su Associa.
17. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Descrizione\Stringa'.
18. Nella struttura selezionare "modello\Pagamenti\Descrizione".
19. Fare clic su Associa.
20. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Valuta\Stringa'.
21. Nella struttura selezionare "modello\Pagamenti\Valuta".
22. Fare clic su Associa.
23. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Id'.
24. Nella struttura selezionare 'modello\Pagamenti\End2EndID'.
25. Fare clic su Associa.
26. Nella struttura espandere "modello\Pagamenti\Creditore".
27. Nella struttura espandere "modello\Pagamenti\Creditore\Conto".
28. Nella struttura espandere "modello\Pagamenti\Creditore\Agente".
29. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Nome\Stringa'.
30. Nella struttura selezionare "modello\Pagamenti\Creditore\Nome".
31. Fare clic su Associa.
32. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\RoutingNumber\Stringa'.
33. Nella struttura selezionare 'modello\Pagamenti\Creditore\Agente\RoutingNumber'.
34. Fare clic su Associa.
35. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\AccountNumber\Stringa'.
36. Nella struttura selezionare "modello\Pagamenti\Creditore\Conto\Numero".
37. Fare clic su Associa.
38. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Pagante\Nome\Stringa'.
39. Nella struttura espandere "modello\Pagamenti\Debitore".
40. Nella struttura espandere "modello\Pagamenti\Debitore\Conto".
41. Nella struttura espandere "modello\Pagamenti\Debitore\Agente".
42. Nella struttura selezionare "modello\Pagamenti\Debitore\Nome".
43. Fare clic su Associa.
44. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\RoutingNumber\Stringa'.
45. Nella struttura selezionare 'modello\Pagamenti\Debtor\Agente\RoutingNumber'.
46. Fare clic su Associa.
47. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\AccountNumber\Stringa'.
48. Nella struttura selezionare "modello\Pagamenti\Debitore\Conto\Numero".
49. Fare clic su Associa.
50. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo'.
51. Nella struttura selezionare "modello\Pagamenti".
52. Fare clic su Associa.
53. Fare clic su Salva.

## <a name="validate-format-mapping"></a>Convalidare il mapping di formato
1. Fare clic su Convalida.
    * Convalidare il nuovo mapping per assicurarsi che tutte le associazioni siano corrette.  
2. Chiudere la pagina.

## <a name="change-status-of-the-current-version-of-format-configuration"></a>Modifica lo stato della versione corrente della configurazione del formato
Nei passaggi seguenti verrà modificato lo stato della configurazione del formato da Bozza a Completato per renderlo disponibile per la generazione di documenti.  
1. Fare clic su Cambia stato.
2. Fare clic su Completa.
3. Nel campo Descrizione digitare un valore.
    * Ad esempio, 'versione 1'.  
4. Fare clic su OK.
5. Selezionare la versione completata della configurazione corrente.
    * Si noti che la configurazione viene salvata come versione completata 1.1: versione 1 del formato in base alla versione 1 del modello dati.  

## <a name="define-effective-date-for-completed-version-of-format"></a>Definisce la data di validità della versione del formato completata
Ciascuna versione del formato può essere configurata come disponibile per l'utilizzo a partire da una determinata data. Quando più versioni di formato sono attive in una determinata data, il formato più recente (in base al numero di versione) verrà selezionato per l'utilizzo. Il valore della data della sessione viene utilizzato per la selezione della versione appropriata.  

## <a name="restrict-access-to-created-format-from-companies"></a>Limitare l'accesso al formato creato da società
1. Espandere la sezione Codici paese ISO.
    * Ogni accesso al formato può essere limitato identificando particolari paesi in cui un formato è applicabile. Se l'elenco dei paesi per il formato specifico è vuoto, il formato può essere utilizzato in qualsiasi società. Quando alcuni codici paese ISO vengono immessi nell'elenco di paesi, il formato può essere utilizzato solo nelle società se nell'indirizzo principale è presente il codice paese.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]