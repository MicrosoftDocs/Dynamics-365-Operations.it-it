--- 
title: Eseguire il formato per utilizzare i file di gestione documenti nel formato di output per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 10/31/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 419c3e305dfdd7d8612340b4a8e8e54e13c6362b
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="run-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a>Eseguire il formato per utilizzare i file di gestione documenti nel formato di output per la creazione di report elettronici (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici. Queste operazioni possono essere eseguite nella società DEMF.

Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura 'ER Usare i file di gestione documenti negli output di formato (parte 3: creare il formato)'.

Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a>Aggiungere gli allegati necessari per l'ordine cliente di una singola fattura
1. Andare a Contabilità clienti > Fatture > Fatture cliente aperte.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare in base al campo Fattura con un valore 'CIV-000148'.
    * CIV-000148  
3. Fare clic su per seguire il collegamento della fattura selezionata.
    * CIV-000148  
4. Fare clic per seguire il collegamento nel campo Ordine cliente.
    * 000148  
5. Selezionare l'opzione Intestazione nel campo Righe o intestazione.
    * Selezionare l'intestazione per indicare che sarà la destinazione per l'aggiunta degli allegati.  
6. Fare clic su Allega.
    * Aggiungere alcuni file come allegati per l'ordine cliente. Utilizzare i file dei tipi di documento che sono supportati dalla gestione documenti (con le estensioni di file DOCX, DPF XML, JPG ecc.). Individuare e selezionare i file da allegare e elaborare ulteriormente con la fattura correlata nel messaggio elettronico della creazione di report elettronici.  
7. Fare clic su Nuovo.
8. Fare clic su File.
9. Fare clic su Nuovo.
10. Fare clic su File.
11. Chiudere la pagina.
12. Chiudere la pagina.
13. Chiudere la pagina.
14. Chiudere la pagina.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>Eseguire il report progettato per la fattura selezionata
1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura espandere 'Modello fattura cliente'.
3. Nella struttura espandere 'Modello fattura cliente\Modello fattura cliente (personalizzato)'.
4. Nella struttura selezionare 'Modello fattura cliente\Modello fattura cliente (personalizzato)\Messaggio di esempio fattura elettronica'.
5. Fare clic su Esegui.
6. Espandere la sezione Record da includere ().
7. Fare clic su Filtro.
8. Selezionare la riga del giornale di registrazione fatture cliente e il campo Ordine cliente.
9. Nel campo Criteri digitare '000148'.
    * Nel campo "Ordine cliente" di criteri, digitare il numero di ordine 000148.  
10. Fare clic su OK.
11. Fare clic su OK.
    * Esaminare l'output generato. Tenere presente che per ogni collegato un singolo nodo XML è stato creato. Il contenuto dell'allegato viene popolato nell'output XML in formato testo MIME (base64).  


