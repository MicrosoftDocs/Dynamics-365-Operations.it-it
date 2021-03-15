---
title: Progettare le configurazioni per generare documenti che contengono dati dell'applicazione
description: Questo argomento descrive come progettare le configurazioni ER per generare un documento elettronico. (Parte 1 - Importare configurazioni).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 417c419dc6925bac337fe74a2f057395316ec75d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092924"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a>Progettare le configurazioni per generare documenti che contengono dati dell'applicazione

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]