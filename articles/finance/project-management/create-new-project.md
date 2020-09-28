---
title: Crea un nuovo progetto
description: Questo argomento fornisce informazioni su come creare un nuovo progetto.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8c52b8c1c86ea2f6e03cf439ba5930f1006ab4f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760583"
---
# <a name="create-a-new-project"></a>Crea un nuovo progetto

[!include [banner](../includes/banner.md)]

Completare i passaggi seguenti per creare un nuovo progetto.

1. Nella pagina **Gestione progetti** selezionare **Nuovo progetto**, quindi immettere i valori seguenti:

    - **Tipo di progetto:** Tempistica e materiali
    - **Nome progetto:** Fase 2 di aggiornamento di XYZ
    - **Gruppo di progetti:** TM\_WIP
    - **ID contratto progetto:** 00000002

2. Selezionare **Crea progetto**.

## <a name="assign-a-resource-to-a-project"></a>Assegnare una risorsa a un progetto

1. Nella pagina **Lavoratori**, nell'elenco **Lavoratori**, selezionare il record per il lavoratore di cui sono state impostate le competenze e aprire il relativo record.
2. Nel riquadro azioni, scheda **Progetto**, gruppo **Impostazione**, selezionare **Assegna progetti**.
3. Nella pagina **Assegnazioni progetto convalida risorse**, nella scheda **Progetti**, nel campo **Aggiungere il progetto ai progetti selezionati**, filtrare in base al progetto **Fase 2 di aggiornamento di XYZ**.
4. Nel riquadro **Progetti rimanenti** selezionare un progetto e fare clic sul pulsante freccia per aggiungerlo al riquadro **Progetti selezionati**.

Se necessario, è anche possibile assegnare categorie per una risorsa. Il tipo di categoria è **Costo** o **Ricavi**. Il tipo di categoria viene determinato dall'organizzazione. Se per una risorsa non vi sono categorie assegnate, Finance cerca la categoria predefinita nei prezzi orari per costi e ricavi.

## <a name="set-up-project-resource-and-role-characteristics"></a>Impostare le caratteristiche dei ruoli e delle risorse del progetto

Un manager di progetto può utilizzare la funzionalità di assegnazione delle risorse al progetto per creare i ruoli necessari per il progetto. I ruoli possono essere utilizzati se le risorse confermate sono ancora sconosciute durante la prenotazione delle risorse. I ruoli possono essere utilizzare per prenotare temporaneamente le risorse come pianificate, in modo da poter continuare le fasi di pianificazione del progetto.

[![Esempio di un ruolo](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Scenario**: Contoso è stato assunto per completare un progetto di tempistica e materiali con uno statuto di progetto approvato. Il secondo manager di progetto sta ancora completando l'ambito del progetto. Il responsabile delle risorse sta al momento identificando le risorse specifiche che verranno prenotare per il nuovo progetto. A causa della natura fondamentale del progetto, uno dei ruoli richiesti dalla sponsor di progetto è Manager di progetto principale. Il responsabile delle risorse deve acquisire la nuova risorsa e definisce il ruolo del sistema, qualora il secondo manager di progetto minore richieda le informazioni sulle risorse durante la pianificazione del progetto.

La procedura seguente mostra come il manager di risorse può impostare il ruolo di manager di progetto principale e associare le caratteristiche delle risorse. Successivamente, il ruolo può essere utilizzato per cercare le risorse disponibili che corrispondono alle competenze delle risorse richieste.

1. Nella pagina **Impostazione ruoli** selezionare **Nuovo progetto**, quindi immettere i valori seguenti:

    - **ID ruolo:** Manager di progetto principale
    - **Descrizione:** Manager di progetto principale

2. Selezionare **Crea**.
3. Selezionare il ruolo **Manager di progetto principale** e quindi **Configurare le caratteristiche**.
4. Nel campo **Tipo caratteristiche** selezionare **Competenza**.
5. Nel campo **Caratteristiche disponibili** immettere la competenza che si sta cercando.
6. Nel campo **Tipo di caratteristica** selezionare **Certificato**.
7. Nel campo **Caratteristiche disponibili** immettere il tipo di certificato che si sta cercando.

## <a name="assign-a-project-resource-to-a-project"></a>Assegnare una risorsa a un progetto

1. Nella pagina **Tutti i progetti**, selezionare il progetto **Fase 2 di aggiornamento di XYZ**.
2. Nella scheda **Team progetto e programmazione**, selezionare **Aggiungi**.
3. Nel campo **Ruolo** selezionare **Membro del team**.
4. Selezionare **Prenota da calendario**.
5. Nella pagina **Disponibilità risorse** selezionare **Impostazioni visualizzazione**.
6. Nella pagina **Modifica impostazioni visualizzazione** immettere i seguenti valori:

    - **Formato per la visualizzazione dell'intervallo di date:** Giorno
    - **Visualizza descrizioni disponibili:** Sì
    - **Visualizza capacità rimanente:** Sì

7. Nell'elenco di risorse, selezionare una risorsa.
8. Selezionare **Prenotazione definitiva** e **Intera capacità**.

## <a name="assign-a-resource-to-a-default-role"></a>Assegnare una risorsa a un ruolo predefinito

Per aiutare i manager di progetto o risorse, è possibile analizzare ulteriormente le risorse prenotabili per un progetto. È possibile associare un ruolo predefinito a una risorsa esistente o una risorsa appena acquisita. Ad esempio, quando Daniel è stato assunto, aveva l'esperienza e le competenze per ricoprire il ruolo di business analyst. Il responsabile delle risorse ha assegnato questo ruolo come ruolo standard a Daniel. Di conseguenza, il responsabile delle risorse ha aggiunto Daniel a un gruppo di business analyst che sono disponibili per lavorare ai progetti.

Durante la prenotazione delle risorse, i manager di progetto possono filtrare le risorse disponibili a lavorare sui progetti. Possono utilizzare queste informazioni come criterio quando eseguono analisi decisionali basate su più criteri per soddisfare la capacità delle risorse. Possono anche aggiungere altre caratteristiche di risorse al filtro per cercare le risorse con competenze, istruzione ed esperienze specifiche per un determinato progetto.

**Scenario:** è stato avviato un progetto approvato e il ruolo di manager di progetto principale è stato prenotato come risorsa pianificata durante la fase di pianificazione del progetto. Il manager delle risorse ha ora acquisito una risorsa per ricoprire il ruolo di manager di progetto principale.

1. Nella pagina **Elenco risorse** selezionare **Daniel Goldschmidt**.
2. Nella pagina **Ruolo risorsa** selezionare **Nuovo**, quindi immettere i valori seguenti:

    - **Validità:** immettere la data corrente.
    - **Scadenza:** immettere **Mai**.
    - **Ruolo:** immettere **Manager di progetto principale**

3. Selezionare **Salva**, quindi chiudere la pagina.
4. Nella scheda **Competenze** aggiungere la competenza **PMP** e il certificato **PMP**.
