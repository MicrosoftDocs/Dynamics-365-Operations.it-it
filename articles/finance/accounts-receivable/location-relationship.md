---
title: Aggiungere tipi di relazione tra ruolo ubicazione e parte
description: In questo articolo viene descritto come aggiungere un nuovo tipo di relazione tra ruolo ubicazione e parte.
author: ShivamPandey-msft
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 2aaf16fac658d26dc2d2a389fd5c1dbb9cbb7649
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874756"
---
# <a name="add-location-and-party-relationship-types"></a>Aggiungere tipi di relazione tra ruolo ubicazione e parte 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a>Aggiungi ruoli ubicazioni

Sono disponibili due modi per aggiungere nuovi ruoli ubicazione per le informazioni su indirizzo e contatto:

-  Aggiungerlo tramite la pagina **Tipo informazioni contatto e indirizzo**. Il nuovo ruolo verrà salvato nella tabella **LogisticsLocationRole** con tipo = 0, che indica che il ruolo non è un ruolo di sistema definito nell'enumerazione **LogisticsLocationRoleType** e le relative estensioni. Un utente potrà utilizzare questo ruolo durante la creazione delle informazioni su indirizzo o contatto.

    ![Scopo informazioni contenuto e indirizzo.](media/Address-Contact.PNG)

-  Aggiungerlo all'estensione di enumerazione **LogisticsLocationRoleType** e popolarlo automaticamente tramite il processo di sincronizzazione del database.

    1.  Creare un'estensione all'enumerazione **LogisticsLocationRoleType** e aggiungere il nuovo ruolo nell'estensione. 
  
        ![Estensione all'enumerazione LogisticsLocationRoleType.](media/Logistics.PNG)

    2. Creare un nuovo file di risorse per il nuovo ruolo e quindi assegnare un valore per le relative proprietà.
     
     ![Nuovo file di risorse.](media/Resource.PNG)
        
    3.  Creare una classe di popolamento dati e immettere un metodo di gestore per popolare il nuovo ruolo. 

        ![Popolamento dati.](media/Dirdata.PNG)

    4.  Per testare il popolamento del nuovo ruolo ubicazione, è possibile creare una classe eseguibile e richiamare DirDataPopulation::insertLogisticsLocationRoles() in Main(). Al termine del processo, di dovrebbe vedere il nuovo ruolo popolato nella tabella **LogisticsLocationRole** con tipo \> 0. Il nuovo ruolo verrà visualizzato nella pagina **Tipo informazioni contatto e indirizzo**.

        ![Inserire nuova ubicazione.](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a>Aggiungere tipi di relazione parte 

Sono disponibili due modi per aggiungere un nuovo tipo di relazione:

-   Aggiungerlo tramite la pagina **Tipi di relazione**. La nuova relazione verrà salvata in **DirRelationshipTypeTable** con systemtype = 0.

    ![Tipi di relazione.](media/Relationship.PNG)

-  Aggiungerlo all'estensione dell'enumerazione **DirSystemRelationshipType** e popolarlo automaticamente tramite il processo di sincronizzazione del database.

    1.  Creare un'estensione all'enumerazione **DirSystemRelationshipType** e aggiungere il nuovo tipo di relazione.

    2. Creare un inizializzatore per questo nuovo tipo. È possibile trovare molti esempi nel codice di base, uno di questi è **DirRelationshipTypeChildInitialize**. Si tratta di una classe di inizializzatore per il tipo di relazione della parte "figlio". È possibile iniziare con l'inizializzatore copiando e incollando questo codice e quindi aggiornare le aree evidenziate.
    
    ![Inizializzatore DirRelationshipChild.](media/DirRelationship.PNG)

    3.  Per testare il popolamento del nuovo tipo di relazione, è possibile creare una classe eseguibile e richiamare DirDataPopulation::insertDirRelationshipTypes() in Main(). Si dovrebbe visualizzare il nuovo tipo di relazione in **DirRelationshipTypeTable** e il nuovo tipo di relazione sarà disponibile nella pagina **Tipi di relazione**.

        ![Classe eseguibile.](media/Runnable.PNG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
