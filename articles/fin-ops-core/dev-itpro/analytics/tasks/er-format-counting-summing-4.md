---
title: 'ER Configurare il formato per eseguire il conteggio e la sommatoria (Parte 4: eseguire il formato)'
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f37fc3c611e9c5328f4d99be8c7c63ab59b2f08
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684645"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a>ER Configurare il formato per eseguire il conteggio e la sommatoria (Parte 4: eseguire il formato)

[!include [banner](../../includes/banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato. Queste operazioni possono essere eseguite nella società DEMF.

Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella "procedura ER Configurare il formato per eseguire conteggi e somme (parte 3: usare i calcoli per creare l'output)".

Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a>Verificare la configurazione per la generazione di report Intrastat
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Fare clic su Configurazioni report.
3. Nella struttura espandere 'Modello Intrastat'.
4. Nella struttura, espandere 'Modello Intrastat\Intrastat (DE)'.
5. Nella struttura selezionare 'Modello Intrastat\Intrastat (DE)\Intrastat (DE) con conteggio e somma'.
6. Nel riquadro azioni, fare clic su Configurazioni.
7. Fare clic su Parametri utente.
8. Selezionare Sì nel campo Esegui impostazioni.
9. Fare clic su OK.
10. Fare clic su Modifica.
11. Selezionare Sì nel campo Esegui bozza.
12. Fare clic su Salva.
13. Passare a Imposta > Impostazione > Commercio estero > Parametri per il commercio estero.
14. Espandere la sezione Creazione di report elettronici.
15. Selezionare la configurazione "Intrastat (DE) con conteggio e somma".
16. Selezionare la configurazione "Intrastat (DE) con conteggio e somma".
17. Fare clic su Salva.
18. Chiudere la pagina.
19. Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.
20. Fare clic su Output.
21. Fare clic su Report.
    * Eseguire il processo di generazione report Intrastat.  
22. Nel campo Data iniziale impostare la data su "01-01-2000".
    * Definire le date di inizio e fine del periodo di reporting che includono le transazioni esistenti nel modulo.  
23. Nel campo Data finale impostare la data su "31-12-2022".
    * Definire le date di inizio e fine del periodo di reporting che includono le transazioni esistenti nel modulo.  
24. Selezionare 'Arrivi' nel campo Direzione.
25. Selezionare Sì nel campo Genera file.
26. Fare clic su OK.
    * Esaminare l'output creato con le righe di riepilogo alla fine.  
27. Fare clic su Nuovo.
28. Nell'elenco contrassegnare la riga selezionata.
29. Selezionare 'Spedizioni' nel campo Direzione.
30. Nel campo Numero di articoli immettere o selezionare un valore.
31. Nel campo Voce doganale immettere o selezionare un valore.
32. Impostare Peso su '10'.
33. Impostare Importo fattura su '10000'.
34. Impostare Importo statistico su '10000'.
35. Fare clic su Output.
36. Fare clic su Report.
37. Selezionare 'Spedizioni' nel campo Direzione.
38. Fare clic su OK.
    * Esaminare l'output creato con le righe di riepilogo alla fine. Tenere presente che è stato modificato rispetto alla prima esecuzione.  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a>Eseguire la configurazione in modalità di debug per esaminare i dati di conteggio e somma raccolti
1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura espandere 'Modello Intrastat'.
3. Nella struttura, espandere 'Modello Intrastat\Intrastat (DE)'.
4. Nella struttura selezionare 'Modello Intrastat\Intrastat (DE)\Intrastat (DE) con conteggio e somma'.
5. Nel riquadro azioni, fare clic su Configurazioni.
6. Fare clic su Parametri utente.
7. Selezionare Sì nel campo Esegui in modalità di debug.
8. Fare clic su OK.
9. Chiudere la pagina.
10. Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.
11. Fare clic su Output.
12. Fare clic su Report.
13. Fare clic su OK.
14. Chiudere la pagina.
15. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
16. Nella struttura espandere 'Modello Intrastat'.
17. Nella struttura, espandere 'Modello Intrastat\Intrastat (DE)'.
18. Nella struttura selezionare 'Modello Intrastat\Intrastat (DE)\Intrastat (DE) con conteggio e somma'.
19. Fare clic su Registri debug.
    * Tenere presente che un record del registro di debug è stato creato per il processo di esecuzione della configurazione selezionata.  
20. Fare clic su Allega.
21. Fare clic su Apri.
    * Esaminare il file XML creato che contiene i dettagli di conteggio e somma che sono stati raccolti durante l'esecuzione della configurazione selezionata.  

