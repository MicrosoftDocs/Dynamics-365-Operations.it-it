---
title: Progettare le configurazioni per generare report in formato di Office con immagini incorporate
description: La procedura in questo argomento fornisce informazioni su come progettare le configurazioni ER per generare i documenti elettronici in formati Microsoft Office (Excel e Word) contenenti le immagini incorporate.
author: NickSelin
manager: AnnBe
ms.date: 01/23/2018
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
ms.openlocfilehash: 6d292d028ebc87892760524dbd7709e8f181fc5d
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141812"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>Progettare le configurazioni per generare report in formato di Office con immagini incorporate

[!include [banner](../../includes/banner.md)]

Per completare i passaggi in questa procedura, prima completare i passaggi della procedura "ER Creare un provider di configurazione e contrassegnarlo come attivo". In questa procedura viene illustrato come progettare le configurazioni ER per generare un documento di Microsoft Excel o Word contenente le immagini incorporate. In questa procedura, verranno create le configurazioni ER necessarie per la società di esempio, Litware, Inc. Questi passaggi possono essere completati mediante il set di dati USMF. Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici. Prima di iniziare, scaricare e salvare i file elencati nell'argomento della Guida: [Incorporare immagini e forme nei documenti generati utilizzando ER](../electronic-reporting-embed-images-shapes.md). I file sono: Model for cheques.xml, Cheques printing format.xml, Company logo.png, Signature image.png, Signature image 2.png e Cheque template Word.docx.

## <a name="verify-prerequisites"></a>Verificare i prerequisiti  
 1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.  
 2. Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come attivo. Se il provider di configurazione non è visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".   
 3. Fare clic su Configurazioni report.  
 
## <a name="add-a-new-er-model-configuration"></a>Aggiungere una nuova configurazione del modello ER  
 1. Anziché creare un nuovo modello, è possibile caricare il file di configurazione del modello ER (Model for cheques.xml) salvato in precedenza. Questo file contiene il modello dati di esempio per gli assegni di pagamento e il mapping del modello dati ai dati componenti dell'applicazione Dynamics 365 for Operations.   
 2. Nella scheda dettaglio Versioni fare clic su Scambia.   
 3. Fare clic su Carica da file XML.  
 4. Fare clic su Sfoglia quindi selezionare Model for cheques.xml.   
 5. Fare clic su OK.  
 6. Il modello caricato verrà utilizzato come origine dati delle informazioni per generare i documenti contenenti le immagini in Excel e Word.  

## <a name="add-a-new-er-format-configuration"></a>Aggiungere una nuova configurazione di formato ER  
 1. Anziché creare un nuovo formato, è possibile caricare il file di configurazione del formato ER (Cheques printing format.xml) salvato in precedenza. Questo file contiene il layout di esempio del formato per stampare gli assegni utilizzando il modulo prestampato e il mapping di questo formato al modello di dati per assegni.   
 2. Fare clic su Scambia.  
 3. Fare clic su Carica da file XML.  
 4. Fare clic su Sfoglia e selezionare il file Cheques printing format.xml.   
 5. Fare clic su OK.  
 6. Nella struttura espandere "Model for cheques".  
 7. Nella struttura selezionare "Model for cheques\Cheques printing format".  
 8. Il formato caricato verrà utilizzato per generare i documenti contenenti le immagini in Excel e Word.   

## <a name="configure-er-user-parameters"></a>Configurare i parametri utente ER  
 1. Nel riquadro azioni, fare clic su Configurazioni.  
 2. Fare clic su Parametri utente.  
 3. Selezionare Sì nel campo Esegui impostazioni.  
  Attivare il flag "Esegui bozza" per avviare la versione bozza del formato selezionato anziché di quello completato.  
 4. Fare clic su OK.  

## <a name="configure-cash--bank-management-parameters"></a>Configurare i Parametri di gestione cassa e banche  
 1. Andare a Gestione cassa e banche > Conti bancari > Conti bancari.  
 2. Utilizzare il filtro rapido per applicare un filtro al campo Conto bancario in base al valore "USMF OPER".  
 3. Nel riquadro azioni, fare clic su Imposta.  
 4. Fare clic su Verifica.  
 5. Espandere la sezione Impostazione.  
 6. Fare clic su Modifica.  
 7. Selezionare Sì nel campo Logo società.  
 8. Fare clic su il logo della società.  
 9. Fare clic su Modifica.  
 10. Fare clic su Sfoglia e selezionare il file scaricato in precedenza, Company logo.png.   
 11. Fare clic su Salva.  
 12. Chiudere la pagina.  
 13. Espandere la sezione Firma.  
 14. Selezionare Sì nel campo Stampa prima firma.  
 15. Fare clic su Modifica.  
 16. Fare clic su Sfoglia e selezionare il file scaricato in precedenza, Signature image.png.   
 17. Espandere la sezione Copie.  
 18. Nel campo Filigrana selezionare un'opzione.  
 19. Selezionare Sì nel campo Formato esportazione elettronica generica.  
 20. Selezionare la configurazione 'Cheques printing format'.  
 21. Ora il formato ER selezionato verrà utilizzato per la stampa degli assegni.  
 22. Fare clic su Allega.  
 23. Fare clic su Nuovo.  
 24. Fare clic su File.  
 25. Fare clic su Sfoglia e selezionare il file scaricato in precedenza, Signature image 2.png.   
 26. Chiudere la pagina.  
 27. Chiudere la pagina.  
 28. Chiudere la pagina.  
 29. Andare a Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche.  
 30. Selezionare Sì nel campo Consenti creazione notifica anticipata su conti bancari inattivi.  
 31. Fare clic su Salva.  
 32. Chiudere la pagina.  
