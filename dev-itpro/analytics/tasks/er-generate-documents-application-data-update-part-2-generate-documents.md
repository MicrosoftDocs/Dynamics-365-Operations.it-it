--- 
title: Generare i documenti con l'aggiornamento dei dati dell'applicazione per la creazione di report elettronici (ER)
description: "Per completare i passaggi di questa procedura, è necessario completare la procedura \"ER Generare documenti con l'aggiornamento dei dati dell'applicazione (Parte 1: Importare configurazioni)."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.openlocfilehash: f10faaaffeb7df5be0b37a9b8dbfa5db5c24d2a2
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="generate-documents-with-application-data-update-for-electronic-reporting-er"></a>Generare i documenti con l'aggiornamento dei dati dell'applicazione per la creazione di report elettronici (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Per completare i passaggi di questa procedura, è necessario completare la procedura "ER Generare documenti con l'aggiornamento dei dati dell'applicazione (Parte 1: Importare configurazioni).



I passaggi di questa procedura descrivono come progettare le configurazioni ER per generare un documento elettronico. In questa procedura verranno eseguite le configurazioni di formati ER importate che sono state create per la società di esempio Litware, Inc. per generare documenti elettronici.



Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici. Tali passaggi possono essere completati mediante il set di dati DEMF. 



Prima di iniziare, modificare il contesto del paese per la società DEMF da DEU (Germania) a BEL (Belgio). Fare clic su Amministrazione organizzazione > Organizzazioni > Persone giuridiche per aggiornare il codice paese nell'indirizzo principale della persona giuridica DEMF. Riavviare l'applicazione.


## <a name="run-imported-er-format"></a>Eseguire il formato ER importato.
1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura espandere "Intrastat (model)".
3. Nella struttura selezionare "Intrastat (model)\Intrastat (format)".
4. Fare clic su Esegui.
    * Eseguire la versione bozza della configurazione dei formati ER per generare il report Intrastat.  
5. Nel campo per immettere il nome del file digitare "intrastat.xml".
    * Specifica il nome del file.  
6. Fare clic su OK.
    * Esaminare il file XML generato.  
7. Chiudere la pagina.
8. Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.
    * Aprire il modulo per visualizzare le transazioni Intrastat incluse nel documento elettronico generato.  
9. Fare clic su archivio Intrastat.
    * Poiché il formato ER eseguito non contiene impostazioni per l'aggiornamento dei dati dell'applicazione, i dettagli del report Intrastat completato non sono stati archiviati.  
10. Chiudere la pagina.
11. Chiudere la pagina.


