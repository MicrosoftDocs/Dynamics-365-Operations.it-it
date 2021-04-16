---
title: Progettare le configurazioni di ER per analizzare i documenti in entrata
description: Questa procedura indica come progettare le configurazioni ER per analizzare un documento elettronico in entrata.
author: NickSelin
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5b503c17b395c2ef45ca4d74c8573d859509c503
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745063"
---
# <a name="design-er-configurations-to-parse-incoming-documents"></a>Progettare le configurazioni di ER per analizzare i documenti in entrata

[!include [banner](../../includes/banner.md)]

Questa procedura indica come progettare le configurazioni ER per analizzare un documento elettronico in entrata. In questa procedura, le configurazioni ER necessarie create per la società di esempio Litware, Inc. saranno importate e utilizzate per analizzare documenti elettronici in entrata. Per completare i passaggi in questa procedura, è necessario prima completare i passaggi della procedura "ER Creare un provider di configurazione e contrassegnarlo come attivo".

Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.

Tali passaggi possono essere completati mediante un set di dati. Prima di iniziare, scaricare e salvare i file elencati nell'argomento "Analizzare i documenti in entrata per aggiornare i dati dell'applicazione" ([Analizzare i documenti in entrata](../parse-incoming-electronic-documents.md)). I file sono i seguenti: EFSTA model.xml, EFSTA format.xml, Response1.xml, Response2.xml, Response3.xml, Response4.xml.

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come attivo. Se il provider di configurazione non è visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".
2. Selezionare Configurazioni report.
    * Il seguente scenario verrà utilizzato per visualizzare le capacità dell'analisi dei documenti elettronici in entrata in formato XML: l'applicazione ERP richiede i dati dal servizio Web (ad esempio [efsta](http://efsta.org/) fiscal service) e analizza le risposte ricevute per aggiornare i dati dell'applicazione di conseguenza. Per analizzare nel modo più efficiente, viene utilizzato un solo formato ER nonostante la struttura diversa dei documenti in entrata previsti nel formato XML.

## <a name="import-and-review-er-configurations"></a>Importare ed esaminare le configurazioni ER

Importare la configurazione del modello ER contenente il modello dati di esempio progettato per archiviare i dettagli del file in entrata.

1. Selezionare Scambia.
2. Selezionare Carica da file XML.
    * Selezionare Sfoglia e selezionare il file EFSTA model.xml.
3. Selezionare OK.
4. Nella struttura selezionare 'EFSTA model'.
5. Selezionare Progettazione.
    * Verificare la struttura del modello dati importato. È definita l'enumerazione enumType per riconoscere i seguenti tipi di risposte del servizio: per ottenere conferma sull'invio della transazione, per ottenere informazioni sull'ultima transazione inviata e per riconoscere i tipi di risposte non supportati.
6. Nella struttura espandere 'Response'.
    * L'elemento radice "Risposta" è definito per specificare il tipo di dati che deve essere prelevato da una risposta del servizio supporto per aggiornare di conseguenza i dati dell'applicazione.
7. Chiudere la pagina.
    * Verrà importata la configurazione del formato ER che specifica la modalità di analisi dei documenti in entrata per archiviare i dati nel modello dati ER.
8. Selezionare Scambia.
9. Selezionare Carica da file XML.
    * Selezionare Sfoglia e selezionare il file EFSTA format.xml.
10. Selezionare OK.
11. Nella struttura espandere 'EFSTA model'.
12. Nella struttura selezionare 'EFSTA model\EFSTA format'.
13. Selezionare Progettazione.
14. Selezionare Espandi/Comprimi.
    * L'elemento del formato CASE viene utilizzato come radice e contiene tre elementi FILE nidificati, pertanto il formato è stato progettato per analizzare i file in entrata di diversi formati.
15. Nella struttura selezionare 'Responses\Transaction completion\TraC'.
    * La risposta sulla transazione inviata inizia dall'elemento radice "TraC".
16. Nella struttura selezionare 'Responses\Last transaction request\Tra'.
    * La risposta sull'ultima transazione inviata inizia dall'elemento radice "Era".
17. Nella struttura selezionare 'Responses\Unexpected response\Text'.
    * Il terzo elemento FILE con l'elemento TEXT nidificato è stato aggiunto per riconoscere qualsiasi altro tipo di risposta che differisce da quando indicato in precedenza.
18. Selezionare Mapping formato a modello.
    * Il mapping del modello contiene la definizione del flusso di dati per archiviare i dettagli del documento in arrivo analizzato utilizzando gli elementi del modello dati.
19. Selezionare Progettazione.
20. Nella struttura espandere "format".
21. Nella struttura selezionare 'format\Responses: Case(Responses)'.
    * Verificare la struttura dell'origine dati "formato". Tutti e tre i tipi di risposta sono offerti separatamente.
22. Nella struttura selezionare 'format\Responses: Case(Responses)\aType'.
    * L'elemento dell'origine dati "aType" è stato aggiunto per indicare il tipo di risposta ed è associato all'elemento del modello dati "Type".
23. Selezionare la scheda Convalide.
24. Nella struttura, selezionare 'Type = format.Responses.aType'.
    * La convalida ER è stata configurata per informare l'utente sulla situazione quando la struttura di risposta non corrisponde alla conferma relativa all'invio della transazione o alle informazioni sull'ultima transazione inviata (caso di risposta non supportato).
25. Chiudere la pagina.

## <a name="run-model-mapping-of-er-format-configured-for-parsing-incoming-files"></a>Eseguire il mapping di modello del formato ER configurato per l'analisi dei file in entrata

Verrà eseguito il mapping di modello creato a scopo di verifica per vedere come il formato ER configurato analizzerà le risposte del servizio in entrata. In questo passaggio vengono utilizzati diversi file XML per simulare i diversi tipi di risposte del servizio Web.

1. Aprire il file Response1.xml in un lettore xml, ad esempio un Web browser. Questo file contiene i dettagli di conferma relativi alla transazione completata ("TraC" è l'elemento radice).
2. Selezionare Esegui.
    * Selezionare Sfoglia e selezionare il file Response1.xml.
3. Selezionare OK.
    * Esaminare l'output generato. Il tipo di risposta è stato riconosciuto e analizzato correttamente (`ERModelEnumDataSourceHandler#EFSTA model#enumType#C` significa caso di completamento della transazione).
    * Aprire il file Response2.xml in un lettore XML. Questo file contiene le informazioni relative all'ultima transazione inviata (`Tra` è l'elemento radice).
4. Selezionare Esegui.
    * Selezionare Sfoglia e selezionare il file Response2.xml.
5. Selezionare OK.
    * Esaminare l'output generato. Il tipo di risposta è stato riconosciuto e analizzato correttamente (`ERModelEnumDataSourceHandler#EFSTA model#enumType#R` significa caso di riavvio del sistema).
    * Aprire il file Response3.xml in un lettore XML. Questo file viene avviato dall'elemento radice TraZ e la struttura non è configurata utilizzando il formato ER.
6. Selezionare Esegui.
    * Selezionare Sfoglia e selezionare il file Response3.xml.
7. Selezionare OK.
    * Esaminare l'output generato. Il tipo di risposta è stato correttamente riconosciuto come non supportato (`ERModelEnumDataSourceHandler#EFSTA model#enumType#U`). Il messaggio corrispondente viene inserito nel Registro informazioni in base alle impostazioni di convalida ER e la maggior parte del modello dati non è stato compilato.
    * Aprire il file Response4.xml in un lettore XML. La struttura del file è quasi la stessa del file Response1.xml correttamente analizzato, ad eccezione della sequenza degli elementi annidati dell'elemento radice "TraC".
8. Selezionare Esegui.
    * Selezionare Sfoglia e selezionare il file Response4.xml.
9. Selezionare OK.
    * Esaminare l'output generato. Il tipo di risposta è stato correttamente riconosciuto come non supportato (`ERModelEnumDataSourceHandler#EFSTA model#enumType#U`)). Il messaggio corrispondente viene inserito nel Registro informazioni e la maggior parte del modello dati non è stato compilato. Questo comportamento è dato dal fatto che l'impostazione corrente del formato ER assume una determinata sequenza di elementi annidati dell'elemento radice del file in entrata.
10. Chiudere la pagina.
11. Nella struttura selezionare 'Responses\Transaction completion\TraC'.
12. Nel campo Analisi ordine di elementi nidificati, selezionare "Qualsiasi".
    * Selezionare Qualsiasi nel campo "Analisi ordine di elementi nidificati" per consentire qualsiasi sequenza di elementi nidificati per l'elemento XML radice.
13. Selezionare Salva.
14. Selezionare Mapping formato a modello.
15. Selezionare Esegui.
    * Selezionare Sfoglia e selezionare il file Response4.xml.
16. Selezionare OK.
    * Esaminare l'output generato. Il tipo di risposta è stato riconosciuto correttamente come uguale per il file Response1.xml.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]