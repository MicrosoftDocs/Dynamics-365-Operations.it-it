---
title: 'ER Utilizzare le dimensioni finanziarie come origine dati (Parte 2: mapping del modello)'
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92efd6a0b36471286c292a80542b81cd14a8eff3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551347"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2-model-mapping"></a>ER utilizzare le dimensioni finanziarie come origine dati (parte 2: mapping del modello)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici. Questi passaggi possono essere eseguiti in qualsiasi società.

Per effettuare questi passaggi, è innanzitutto necessario completare i passaggi nella procedura "ER Usare dimensioni finanziarie come origine dati (parte 1: progettare il modello dati".


## <a name="add-required-data-sources-to-model-mapping"></a>Aggiungere le origini dati richieste al mapping del modello
1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura selezionare 'Modello di esempio dimensioni finanziarie'.
3. Fare clic su Progettazione.
4. Fare clic su Mappa modello a origine dati.
5. Fare clic su Nuovo.
6. Selezionare Voce nel campo Definizione.
7. Digitare 'Mapping dati dimensioni' nel campo Nome.
8. Digitare 'Mapping dati dimensioni' nel campo Descrizione.
9. Fare clic su Salva.
10. Fare clic su Progettazione.
11. Nella struttura selezionare 'Dynamics 365 for Operations\Tabella'.
12. Fare clic su Aggiungi radice.
13. Nel campo Nome digitare "Società".
14. Nel campo Tabella digitare "CompanyInfo".
15. Fare clic su OK.
16. Nella struttura selezionare ' 'Funzioni\Dettagli di dimensioni finanziarie'.
17. Fare clic su Aggiungi radice.
    * Questa origine dati specifica come l'ambito delle dimensioni finanziarie verrà definito per qualsiasi report che utilizzerà questo modello come origine dei dati.  
18. Digitare un valore nel campo Nome.
19. Selezionare Sì nel campo Chiedi dimensioni.
    * Selezionare Sì per consentire all'utente di selezionare le dimensioni in fase di esecuzione nella finestra di dialogo utente. Se l'opzione impostata su No, tutte le dimensioni finanziarie dell'istanza corrente verranno utilizzate per impostazione predefinita.  
20. Selezionare 'Persona giuridica' nel campo Selezione dimensioni finanziarie.
    * Selezionare Tutte per consentire all'utente di selezionare le dimensioni desiderate per l'istanza corrente nel campo di ricerca.  Selezionare Persona giuridica per consentire all'utente di selezionare le dimensioni per la società nel campo di ricerca.  Selezionare Dimensione per consentire all'utente di selezionare le dimensioni utilizzando un unico set di dimensioni.  
21. Selezionare Sì nel campo Chiedi conto principale.
    * Impostare 'Chiedi conto principale' su Sì per consentire agli utenti di selezionare il conto principale come parte dell'elenco delle dimensioni.   Se l'opzione impostata su No, il conto principale non verrà incluso nell'elenco delle dimensioni e l'opzione 'Conto principale obbligatorio' è abilitata. Se 'Conto principale obbligatorio' è impostato su Sì, include il conto principale nell'elenco delle dimensioni indipendentemente dalla selezione dell'utente.  
22. Fare clic su OK.
23. Nella struttura selezionare 'Dynamics 365 for Operations\Record di tabella'.
24. Fare clic su Aggiungi radice.
25. Nel campo Nome digitare 'LedgerJournal'.
26. Selezionare Sì nel campo Chiedi query.
27. Nel campo Tabella digitare 'LedgerJournalTable'.
28. Fare clic su OK.

## <a name="map-data-model-elements-to-added-data-sources"></a>Mappare gli elementi del modello dati alle origini dati aggiunte
1. Nella struttura espandere 'Giornale di registrazione'.
2. Nella struttura espandere 'Giornale di registrazione\Transazione'.
3. Nella struttura espandere 'Giornale di registrazione\Transazione\Dati dimensioni'.
4. Nella struttura espandere 'Impostazione dimensioni'.
5. Nella struttura espandere 'LedgerJournal'.
6. Nella struttura espandere 'LedgerJournal\<Relazioni'.
7. Nella struttura espandere 'LedgerJournal\<Relazioni\LedgerJournalTrans'.
8. Nella struttura selezionare 'LedgerJournal\<Relazioni\LedgerJournalTrans\Giustificativo'.
9. Nella struttura selezionare 'Giornale di registrazione\Transazione\Giustificativo'.
10. Fare clic su Associa.
11. Nella struttura selezionare 'LedgerJournal\<Relazioni\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.
    * Tenere presente che per qualsiasi riferimento alle dimensioni finanziarie impostato, ad esempio, su LedgerDimension, un articolo di origine dati corrispondente è disponibile (LedgerDimension.Dimension). Questo articolo di origine dati offre le dimensioni finanziarie di tale set di dimensioni come elenco di record.  
12. Nella struttura espandere 'LedgerJournal\<Relazioni\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.
13. Nella struttura espandere 'LedgerJournal\<Relazioni\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conto principale e dimensioni'.
14. Nella struttura espandere 'LedgerJournal\<Relazioni\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conto principale e dimensioni\Valore'.
15. Nella struttura espandere 'LedgerJournal\<Relazioni\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conto principale e dimensioni\Definizione'.
16. Nella struttura selezionare 'LedgerJournal\<Relazioni\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conto principale e dimensioni\Definizione\Nome'.
17. Nella struttura selezionare 'Giornale di registrazione\Transazione\Dati dimensioni\Nome'.
18. Fare clic su Associa.
19. Nella struttura selezionare 'LedgerJournal\<Relazioni\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conto principale e dimensioni\Valore\Descrizione'.
20. Nella struttura selezionare 'Giornale di registrazione\Transazione\Dati dimensioni\Descrizione'.
21. Fare clic su Associa.
22. Nella struttura selezionare 'LedgerJournal\<Relazioni\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conto principale e dimensioni\Valore\Codice'.
23. Nella struttura selezionare 'Giornale di registrazione\Transazione\Dati dimensioni\Codice'.
24. Fare clic su Associa.
25. Nella struttura selezionare 'LedgerJournal\<Relazioni\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conto principale e dimensioni'.
26. Nella struttura selezionare 'Giornale di registrazione\Transazione\Dati dimensioni'.
27. Fare clic su Associa.
28. Nella struttura selezionare 'LedgerJournal\<Relazioni\LedgerJournalTrans\Dare(AmountCurDebit)'.
29. Nella struttura selezionare 'Giornale di registrazione\Transazione\Dare'.
30. Fare clic su Associa.
31. Nella struttura selezionare 'LedgerJournal\<Relazioni\LedgerJournalTrans\Data(TransDate)'.
32. Nella struttura selezionare 'Giornale di registrazione\Transazione\Data'.
33. Fare clic su Associa.
34. Nella struttura selezionare 'LedgerJournal\<Relazioni\LedgerJournalTrans\Valuta(CurrencyCode)'.
35. Nella struttura selezionare 'Giornale di registrazione\Transazione\Valuta'.
36. Fare clic su Associa.
37. Nella struttura selezionare 'LedgerJournal\<Relazioni\LedgerJournalTrans\Avere(AmountCurCredit)'.
38. Nella struttura selezionare 'Giornale di registrazione\Transazione\Avere'.
39. Fare clic su Associa.
40. Nella struttura selezionare 'LedgerJournal\<Relazioni\LedgerJournalTrans'.
41. Nella struttura selezionare 'Giornale di registrazione\Transazione'.
42. Fare clic su Associa.
43. Nella struttura selezionare 'LedgerJournal\Numero batch giornale di registrazione(JournalNum)'.
44. Nella struttura selezionare 'Giornale di registrazione\Batch'.
45. Fare clic su Associa.
46. Nella struttura selezionare 'LedgerJournal'.
47. Nella struttura selezionare 'Giornale di registrazione'.
48. Fare clic su Associa.
49. Nella struttura espandere 'Dimensioni'.
50. Nella struttura, espandere 'Dimensioni\Conto principale e dimensioni'.
51. Nella struttura, espandere 'Dimensioni\Conto principale e dimensioni\Definizione'.
52. Nella struttura, selezionare 'Dimensioni\Conto principale e dimensioni\Definizione\Nome'.
53. Nella struttura selezionare 'Impostazione dimensioni\Codice'.
54. Fare clic su Associa.
55. Nella struttura, selezionare 'Dimensioni\Conto principale e dimensioni\Definizione\Nome colonna report'.
56. Nella struttura selezionare 'Impostazione dimensioni\Nome'.
57. Fare clic su Associa.
58. Nella struttura, selezionare 'Dimensioni\Conto principale e dimensioni'.
59. Nella struttura selezionare 'Impostazione dimensioni'.
60. Fare clic su Associa.
61. Nella struttura selezionare 'Società'.
62. Fare clic su Modifica.
63. Nel campo expressionAsStringText immettere 'Company.'find()'.'name()''.
    * Company.'find()'.'name()'  
64. Fare clic su Salva.
65. Chiudere la pagina.
66. Fare clic su Salva.
67. Chiudere la pagina.

## <a name="complete-this-draft-models-version"></a>Completare la versione di questo modello bozza
1. Chiudere la pagina.
2. Chiudere la pagina.
3. Fare clic su Cambia stato.
4. Fare clic su Completa.
5. Fare clic su OK.

