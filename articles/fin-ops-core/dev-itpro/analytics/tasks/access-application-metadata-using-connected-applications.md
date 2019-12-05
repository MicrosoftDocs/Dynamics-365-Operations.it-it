---
title: Accedere ai metadati dell'applicazione utilizzando applicazioni connesse
description: I passaggi in questo argomento descrivono come un utente di Regulatory Configuration Service (RCS) può progettare un nuovo mapping di modello per la creazione di report elettronici (ER) utilizzando i metadati in Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5020b523ca5d76d36f7436a8f43e8629c029e3e8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769880"
---
# <a name="access-application-metadata-by-using-connected-applications"></a>Accedere ai metadati dell'applicazione utilizzando applicazioni connesse

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti illustrano come un utente di Regulatory Configuration Service (RCS) con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può progettare un nuovo mapping di modello per la creazione di report elettronici (ER) utilizzando i metadati in Finance and Operations. Per accedere ai metadati dell'applicazione online si utilizza l'applicazione connessa RCS. Il mapping di modello ER di esempio verrà configurato per accedere alle transazioni del commercio estero. Per completare questi passaggi, in RCS è necessario dapprima completare i passaggi nell'argomento [Creare provider di configurazione e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md). Se i passaggi nell'argomento [Accedere ai metadati dell'applicazione utilizzando una configurazione ER](access-application-metadata-er-configuration.md) non sono stati completati, accedere alla [pagina degli esempi di creazione di report elettronici](https://go.microsoft.com/fwlink/?linkid=862266) per scaricare e salvare le seguenti configurazioni ER: Metadati del commercio estero.xml; Modello del commercio estero.xml; Mapping del commercio estero.xml. Completare quindi i passaggi della procedura.

## <a name="prerequisites"></a>Prerequisiti
1. Andare a **Tutte le aree di lavoro** > **Creazione di report elettronici**. 
2. Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**. Se questo provider di configurazione non è visualizzato, completare i passaggi nella procedura [Creare provider di configurazioni e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md). 

## <a name="get-required-er-configurations"></a>Ottenere le configurazioni ER necessarie
1. Fare clic su **Configurazioni report**. 
2. Se i passaggi nella procedura [Accedere ai metadati dell'applicazione utilizzando una configurazione ER](access-application-metadata-er-configuration.md) sono stati completati, si dispone già di tutte le configurazioni ER necessarie (configurazioni di metadati, modello e mapping del commercio estero) nell'istanza di RCS corrente. È possibile ignorare tutti i passaggi rimanenti di questa sottoattività. 
3. Fare clic su **Scambia**. 
4. Fare clic su **Carica da file XML**. 
5. Fare clic **Sfoglia** e selezionare il file **Metadati del commercio estero.xml**. 
6. Fare clic su **OK**. 
7. Fare clic su **Scambia**. 
8. Fare clic su **Carica da file XML**. 
9. Fare clic **Sfoglia** e selezionare il file **Modello del commercio estero.xml**. 
10. Fare clic su **OK**. 
11. Fare clic su **Scambia**. 
12. Fare clic su **Carica da file XML**. 
13. Fare clic **Sfoglia** e selezionare il file **Mapping del commercio estero.xml**. 
14. Fare clic su **OK**. 

## <a name="register-a-connected-application"></a>Registrare un'applicazione connessa
1. Chiudere la pagina. 
2. Chiudere la pagina. 
3. Andare a **Tutte le aree di lavoro** > **Creazione di report elettronici**. 
4. Fare clic su **Applicazioni connesse**. 
5. Assicurarsi che l'applicazione configurata sia basata su Azura e accessibile all'utente RCS corrente. È inoltre necessario che l'utente RCS corrente abbia accesso all'applicazione selezionata, sia stato registrato come utente di questa applicazione e disponga di un ruolo con privilegi di accesso ai metadati dell'applicazione. 
6. Fare clic su **Nuovo**. 
7. Nel campo **Nome** digitare "MiaAppConnessa". 
8. Nel campo **Applicazione**, immettere "https:// miasocietà.operations.dynamics.com". 
9. Nel campo **Tenant**, immettere "miasocietà.onmicrosoft.com". 
10. Fare clic su **Salva**. 
11. Quando si verifica la connessione all'applicazione configurata, nella pagina **Connettersi all'applicazione remota**, fare clic sul collegamento **Fare clic qui per la connessione all'applicazione remota selezionata**. 
12. Fare clic su **Verifica connessione**. 
13. Fare clic su **Chiudi**. 
14. Quando la connessione viene convalidata, i dettagli relativi a tenant e versione verranno aggiornati per l'applicazione configurata nella griglia corrente. 

## <a name="review-existing-model-mapping-configuration"></a>Esaminare una configurazione del mapping di modello ER esistente
1. Chiudere la pagina. 
2. Fare clic su **Configurazioni report**. 
3. Nella struttura espandere **Modello del commercio estero**. 
4. Nella struttura, selezionare **Modello del commercio estero\Mapping del commercio estero**. 
5. Espandere la sezione **Prerequisiti**. 

    > [!NOTE]
    > Attualmente, questo mapping fa riferimento alla configurazione dei metadati. I metadati dell'applicazione di questa configurazione saranno disponibili durante la progettazione di questo mapping di modello. 

6. Fare clic su **Progettazione**. 
7. Fare clic su **Progettazione**. 
8. Nella struttura selezionare **Dynamics 365 for Operations'\Record di tabella**. 
9. Fare clic su **Aggiungi radice**. 
10. Nel campo **Tabella** immettere o selezionare un valore. 

    > [!NOTE]
    > Attualmente, questo mapping fa riferimento alla configurazione dei metadati. I metadati dell'applicazione di questa configurazione saranno disponibili durante la progettazione di questo mapping di modello. 

11. Fare clic su **Annulla**. 
12. Chiudere la pagina. 
13. Chiudere la pagina. 

## <a name="assign-connected-application-to-model-mapping"></a>Assegnare un'applicazione connessa al mapping di modello 
1. Fare clic su **Modifica**. 
2. Selezionare l'applicazione **MiaAppConnessa**. 

    > [!NOTE]
    > Attualmente, questo mapping fa riferimento ai metadati dell'applicazione connessa selezionata. Quando lo stesso mapping fa riferimento contemporaneamente alla configurazione dei metadati e all'applicazione connessa, verranno utilizzati i metadati dell'applicazione connessa. 

3. Fare clic su **Progettazione**. 
4. Fare clic su **Progettazione**. 
5. Nella struttura selezionare **Dynamics 365 for Operations'\Record di tabella**. 
6. Fare clic su **Aggiungi radice**. 
7. Nel campo **Tabella** immettere o selezionare un valore. 

    > [!NOTE]
    > Sono disponibili più di due tabelle dell'applicazione in quanto questo mapping utilizza tutti i metadati dell'applicazione connessa che è stata assegnata agli stessi. 

8. Fare clic su **Annulla**. 
9. Fare clic su **Convalida**. 

    > [!NOTE]
    > Abbiamo associato gli elementi del modello di dati ad articoli delle origini dati descritte utilizzando i dettagli dei metadati dell'applicazione connessa che è stata assegnata a questo mapping. 

10. Chiudere la pagina. 
11. Chiudere la pagina. 

Quando è necessario valutare questo mapping di modello utilizzando i metadati di un'altra versione dell'applicazione, registrare un'altra applicazione connessa, assegnarla a questo mapping di modello e convalidarla in base ai nuovi metadati.
