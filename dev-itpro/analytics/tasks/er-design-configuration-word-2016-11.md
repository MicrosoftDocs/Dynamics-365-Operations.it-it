--- 
title: Progettare una configurazione per la generazione di report in formato Microsoft Word per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un utente con il ruolo di amministratore di sistema o sviluppatore per la creazione di report elettronici può configurare formati per la creazione di report elettronici (ER) per generare i report elettronici come file di Microsoft Word."
author: NickSelin
manager: AnnBe
ms.date: 12/21/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5adf1d6e6314ac7ea4084cfb3fcde8b83168c7ae
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="design-a-configuration-for-generating-reports-in-microsoft-word-format-for-electronic-reporting-er"></a>Progettare una configurazione per la generazione di report in formato Microsoft Word per la creazione di report elettronici (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con il ruolo di amministratore di sistema o sviluppatore per la creazione di report elettronici può configurare formati per la creazione di report elettronici (ER) per generare i report elettronici come file di Microsoft Word. Queste operazioni possono essere eseguite nella società GBSI.

Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi "Creare una configurazione ER per la generazione di report in formato OPENXML" nella guida attività. In anticipo, è inoltre necessario scaricare e salvare i seguenti modelli localmente per il report di esempio:

http://msdynamics.blob.core.windows.net/media/2016/10/SampleVendPaymDocReport.docx

http://msdynamics.blob.core.windows.net/media/2016/10/SampleVendPaymDocReportBounded.docx

Questa procedura è per una funzionalità che è stata aggiunta in Microsoft Dynamics 365 for Operations versione 1611.


## <a name="select-the-existing-er-report-configuration"></a>Selezionare la configurazione esistente del report ER
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * Assicurarsi che il provider di configurazione 'Litware, Inc.' sia selezionato come attivo.  
2. Fare clic su Configurazioni report.
    * Verrà riutilizzata la configurazione ER esistente originariamente progettata per generare l'output del report in formato OPENXML.  
3. Nella struttura espandere "Modello di pagamento".
4. Nella struttura selezionare "Modello di pagamento\Report foglio di lavoro di esempio".
5. Fare clic su Progettazione.

## <a name="replace-the-excel-template-with-the-word-template"></a>Sostituire il modello di Excel con il modello di Word
    * Attualmente, il documento di Excel viene utilizzato come modello per generare l'output nel formato OPENXML. Il modello di report verrà importato in formato Word.  
1. Fare clic su Allegati.
    * Sostituire il modello esistente di Excel con il modello di Word scaricato in precedenza, SampleVendPaymDocReport.docx. Si noti che il modello contiene solo il layout di documento che si desidera generare come output ER.  
2. Fare clic su Elimina.
3. Fare clic su Sì.
4. Fare clic su Nuovo.
5. Fare clic su File.
6. Fare clic su Sfoglia. Trovare e selezionare SampleVendPaymDocReport.docx in precedenza scaricato. Fare clic su OK.
    * Selezionare il modello scaricato nel passaggio precedente.  
7. Nel campo Modello immettere o selezionare un valore.

## <a name="extend-the-word-template-by-adding-a-custom-xml-part"></a>Estendere il modello di Word aggiungendo una parte XML personalizzata
1. Fare clic su Salva.
    * Oltre ad archiviare le modifiche apportate alla configurazione, l'azione Salva aggiorna anche il modello di Word associato. La struttura del formato previsto viene trasferita al documento Word associato come nuova parte XML personalizzata con il nome 'Report'. Si noti che il modello di Word associato non contiene solo il layout di documento da generare come output ER, ma anche la struttura dei dati che ER inserisce nel modello in fase di esecuzione.  
2. Fare clic su Allegati.
    * Successivamente è necessario associare gli elementi alla parte XML personalizzata 'Report' alle parti del documento di Word.  
    * Se si ha dimestichezza con i documenti Word che possono essere gestiti come moduli contenenti controlli di contenuto associati agli elementi delle parti XML personalizzate, eseguire tutti i passaggi della sottoattività successiva per creare un tipo di documento. Per ulteriori informazioni, vedere questo collegamento https://support.office.com/en-us/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US. In caso contrario, ignorare tutti i passaggi della sottoattività successiva.  

## <a name="get-word-with-custom-xml-part-to-do-data-bindings"></a>Utilizzare Word con la parte XML personalizzata per effettuare le associazioni di dati
    * Aprire il documento in Word e effettuare le seguenti operazioni: - Aprire la scheda Sviluppatore di Word (personalizzare la barra multifunzione se non è ancora attivata).  - Selezionare il riquadro di mapping XML.  - Selezionare la parte XML personalizzata ‘Report’ nella ricerca.  - Eseguire il mapping degli elementi della parte XML personalizzata selezionata e dei controlli di contenuto del documento Word.  - Salvare il documento Word aggiornato in un'unità locale.  

## <a name="upload-the-word-template-with-custom-xml-part-bounded-to-content-controls"></a>Caricare il modello di Word con la parte XML personalizzata associata ai controlli di contenuto
1. Fare clic su Elimina.
2. Fare clic su Sì.
    * Aggiungere un nuovo modello. Se sono stati completati i passaggi nella sottoattività precedente, selezionare il documento Word che è stato preparato e salvato localmente. In caso contrario, selezionare il modello di MS Word SampleVendPaymDocReportBounded.docx scaricato in precedenza.  
3. Fare clic su Nuovo.
4. Fare clic su File.
5. Fare clic su Sfoglia. Trovare e selezionare SampleVendPaymDocReportBounded.docx in precedenza scaricato. Fare clic su OK.
6. Nel campo Modello, selezionare il documento scaricato nel passaggio precedente.
7. Fare clic su Salva.
8. Chiudere la pagina.

## <a name="execute-the-format-to-create-word-output"></a>Eseguire il formato per creare l'output di Word
1. Nel riquadro azioni, fare clic su Configurazioni.
2. Fare clic su Parametri utente.
3. Selezionare Sì nel campo Esegui impostazioni.
4. Fare clic su OK.
5. Fare clic su Modifica.
6. Selezionare Sì nel campo Esegui bozza.
7. Fare clic su Salva.
8. Chiudere la pagina.
9. Chiudere la pagina.
10. Andare a Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.
11. Fare clic su Righe.
12. Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.
13. Fare clic su Stato pagamento.
14. Fare clic su Nessuno.
15. Fare clic su Genera pagamenti.
16. Fare clic su OK.
17. Fare clic su OK.
    * Analizzare l'output generato. Tenere presente che l'output creato viene visualizzato nel formato di Word e contiene i dettagli dei pagamenti elaborati.  


