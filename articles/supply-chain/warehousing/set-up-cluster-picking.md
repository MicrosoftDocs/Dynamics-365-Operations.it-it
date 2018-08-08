---
title: Imposta prelievo del cluster
description: In questo argomento viene descritto come impostare il prelievo cluster e l'utilizzo della conferma dell'articolo con prelievo cluster.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2ec0890963b2b01407acac8003453faf370894b4
ms.openlocfilehash: 1c23421ddfda8c5f6fa27a31831a00ead6094db9
ms.contentlocale: it-it
ms.lasthandoff: 04/11/2018

---

[!include[banner](../includes/banner.md)]

# <a name="set-up-cluster-picking"></a>Imposta prelievo del cluster

In questo argomento viene descritto come abilitare i lavoratori a utilizzare i propri dispositivi mobili per raggruppare il lavoro di prelievo nei cluster, in modo che possano prelevare gli articoli da un unica ubicazione per più ordini di lavoro contemporaneamente. Questo tipo di azione viene denominato *prelievo del cluster*.

## <a name="about-cluster-picking"></a>Informazioni sul prelievo del cluster

Dopo aver emesso gli ordini di lavoro al magazzino, il lavoratore può utilizzare un dispositivo mobile per assegnare gli ordini a un cluster. Il cluster organizzerà il lavoro di prelievo per il lavoratore. Quando un ordine di lavoro viene assegnato a un cluster, il lavoratore deve utilizzare il prelievo del cluster per eseguire il lavoro di prelievo dell'ordine. Il lavoratore non potrà utilizzare altri metodi di prelievo. Se un ordine di lavoro viene assegnato a un cluster per errore, il lavoratore dovrà interrompere il cluster e quindi ricrearlo.

Se necessario, un lavoratore può passare un cluster a un altro lavoratore. Tale operazione modifica lo stato in Superato. Quando il lavoratore utilizza un dispositivo mobile per indicare il completamento del prelievo e dello stoccaggio, è necessario confermare la spedizione o il carico nel client di Dynamics 365 for Finance and Operations.

## <a name="set-up-cluster-picking"></a>Imposta prelievo del cluster

Per abilitare il prelievo del cluster, è necessario impostare quanto segue:

-   **Profili cluster**: consente di specificare se generare automaticamente gli ID del cluster, il numero di posizioni da utilizzare, quando interrompere i cluster e come ordinare in sequenza e verificare il lavoro di prelievo.

-   **Modelli di lavoro**: consente di definire la modalità di creazione del lavoro di prelievo per il prelievo del cluster.

-   **Direttive ubicazione**: consente di specificare dove prelevare gli articoli e dove inserirli.

-   **Voci di menu del dispositivo mobile**: consente di configurare una voce di menu del dispositivo mobile per utilizzare il lavoro esistente che è diretto dal prelievo del cluster. È quindi necessario aggiungere la voce di menu a un menu del dispositivo mobile in modo che sia visualizzato sui dispositivi mobili.

-   **Parametri di gestione magazzino**: consente di specificare la sequenza numerica da utilizzare se si desidera generare gli identificatori per i cluster.

## <a name="set-up-a-cluster-profile"></a>Impostare un profilo del cluster

Per impostare un profilo del cluster, effettuare le seguenti operazioni:

1.  Fare clic su **Gestione magazzino** \> **Impostazione** \> **Dispositivo mobile** \> **Profili cluster**.

2.  Fare clic su **Nuovo** per creare un nuovo profilo.

3.  Fare clic su **Crea cluster** e in **Ordinamento cluster** fare su **Nuovo** per impostare i criteri di ordinamento per il cluster. I criteri di ordinamento controllano l'ordine in cui il lavoratore eseguirà il lavoro di prelievo. È possibile aggiungere un numero illimitato di criteri.

4.  Nel campo **Numero progressivo** immettere un numero per definire l'ordine in cui verranno elaborati i criteri di ordinamento.

5.  Nel campo **Nome campo** selezionare il campo che determinerà l'ordinamento. Ad esempio, se si seleziona il campo **WMSLocationId** il lavoro verrà ordinato per posizione.

6.  Nel campo **Ordinamento** selezionare una delle seguenti opzioni.

| **Opzione**     | **Descrizione**                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Crescente**  | Il lavoro di prelievo viene ordinato in ordine crescente in base ai criteri di ordinamento. Ad esempio, se si utilizza il campo **WMSLocationId** come criterio di ordinamento e l'ID della posizione è 1, 2, 3 e 4, l'utente preleverà prima dalla posizione 4. |
| **Decrescente** | Il lavoro di prelievo viene ordinato in ordine decrescente in base ai criteri di ordinamento. Ad esempio, se si utilizza il campo **WMSLocationId** come criterio di ordinamento e l'ID della posizione è 1, 2, 3 e 4, l'utente preleverà prima dalla posizione 1. |

## <a name="item-confirmation"></a>Conferma articolo

Quando il prelievo cluster viene applicato, la conferma dell'articolo è essenziale per verificare che gli articoli vengano aggiunti ai cluster. È possibile verificare gli articoli nel prelievo cluster durante il processo di prelievo cluster. L'impostazione dipende dall'impostazione dei codici a barre del prodotto.

### <a name="set-up-item-verification-with-cluster-picking"></a>Impostare la verifica dell'articolo con prelievo cluster

1.  Su una voce di menu del dispositivo mobile, aprire il modulo di impostazione per la conferma di lavoro: **Gestione magazzino** \> **Gestione magazzino** \> **Impostazione** \> **Dispositivo mobile** \> **Voci di menu del dispositivo mobile**.

2.  Dalle voci di menu del dispositivo mobile, aprire la **configurazione della conferma del lavoro**. L'opzione **Conferma prodotto** consente di verificare ogni pezzo di magazzino dal dispositivo mobile sottoposto a scansione.

