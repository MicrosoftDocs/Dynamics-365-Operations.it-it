---
title: Progettare le configurazioni per generare report in formato di Office con immagini incorporate
description: Questo argomento descrive come progettare configurazioni che generano documenti elettronici nei formati Excel e Word contenenti le immagini incorporate.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 03a514c5b616d761ef3eb6347e67e645b23eaa1794911775835e77cded4500ac
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719347"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>Progettare le configurazioni per generare report in formato di Office con immagini incorporate

[!include [banner](../../includes/banner.md)]

Per completare i passaggi in questa procedura, prima completare i passaggi della procedura "ER Creare un provider di configurazione e contrassegnarlo come attivo". In questa procedura viene illustrato come progettare le configurazioni ER per generare un documento di Microsoft Excel o Word contenente le immagini incorporate. In questa procedura, verranno create le configurazioni ER necessarie per la società di esempio, Litware, Inc. Questi passaggi possono essere completati mediante il set di dati USMF. Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici. Prima di inziare scaricare e salvare i file seguenti: 

| descrizione                                          | Nome file                   |
|------------------------------------------------------|-----------------------------|
| Configurazione del modello di dati ER                          | [Model for cheques.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| Configurazione di formato ER                              | [Cheques printing format.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| Immagine del logo dell'azienda                                   | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| Immagine della firma                                      | [Signature image.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| Immagine della firma alternativa                          | [Signature image 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Modello di Microsoft Word per la stampa di assegni di pagamento  | [Cheque template Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

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


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
