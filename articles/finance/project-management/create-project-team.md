---
title: Creare un team di progetto
description: Questo argomento fornisce informazioni su come creare e gestire i team di progetto.
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
ms.openlocfilehash: 834a6c0a4fcc32a955c1feddf0a6cbbb1f16b869
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760584"
---
# <a name="create-a-project-team"></a>Crea un team di progetto

[!include [banner](../includes/banner.md)]

Per utilizzare i ruoli impostati in precedenza in un progetto, un manager di progetto deve associare i ruoli al progetto. È possibile assegnare molteplici ruoli a un progetto. Per evitare confusione, questi ruoli vengono automaticamente etichettati durante la prenotazione. Ad esempio, se il manager di progetto richiede tre programmatori, vengono generati automaticamente tre ruoli programmatore con le etichette **programmatore 1**, **programmatore 2** e **programmatore 3**. Se per il ruolo sono già state impostate caratteristiche, vengono applicate come filtro durante le ricerche di una risorsa. È possibile aggiungere caratteristiche aggiuntive per ridefinire ulteriormente la ricerca.

Le impostazioni di visualizzazione possono anche essere personalizzate per dare una visione migliore della disponibilità delle risorse. Sono disponibili opzioni per visualizzare la disponibilità oraria, giornaliera, settimanale, mensile, trimestrale e annuale. È anche disponibile un'opzione per mostrare la capacità disponibile e rimanente sulle risorse. Questa opzione è utile per la gestione del tempo quando si stima il tempo disponibile per le attività o la disponibilità delle risorse.

Il manager di progetto può selezionare un ruolo nella pagina e quindi, se sono presenti risorse disponibili in base ai requisiti, prenotare una risorsa per ricoprire il ruolo. Si noti che le risorse non devono essere prenotate a questo punto nella fase di pianificazione. Quando si crea una struttura di suddivisione lavoro, è possibile sostituire i ruoli con risorse con personale per il progetto. Se i ruoli vengono sostituiti con le risorse con personale nella struttura di suddivisione lavoro, l'impostazione della risorsa aggiorna automaticamente la pianificazione e l'elenco del team di progetto.

[![Elenco del team di progetto che include i ruoli e le risorse effettive](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

Il manager di progetto dispone di diverse opzioni per prenotare una risorsa per un progetto, ad esempio **Capacità rimanente**, **Intera capacità**, **Percentuale capacità** e **Specifica ore**. Queste opzioni di prenotazione possono essere annullate in qualsiasi momento se cambiano le assegnazioni delle risorse. Sono supportati due tipi di prenotazione:

- **Prenotazione definitiva**: la prenotazione delle risorse è stata approvata e confermata per l'impegno per la durata specificata.
- **Prenotazione preliminare**: la prenotazione delle risorse è stata impostata per l'impegno per la durata specificata.

La seguente procedura spiega come creare un team di progetto.

## <a name="create-a-project-team"></a>Crea un team di progetto

1. Nella pagina elenco **Tutti i progetti** selezionare un progetto e **Modifica**.
2. Nella scheda **Team progetto e programmazione**, campo **Programma data di fine**, immettere la data di inizio della programmazione più un mese. Ad esempio, se la data di inizio della programmazione è il 24 giugno 2017 (24/06/2017), immettere **24/07/2017**.
3. Selezionare **Aggiungi**.
4. Nel riquadro **Aggiungi ruoli al progetto**, campo **Ruolo**, selezionare **Manager di progetto principale**.
5. Selezionare **Competenze richieste**.
6. Nella pagina **Scegli caratteristiche** le caratteristiche precedentemente impostate per il ruolo di manager di progetto principale vengono selezionate per impostazione predefinita. Selezionare **OK**.
7. Nella pagina **Aggiungi ruoli al progetto**, campo **Numero di risorse**, immettere **1**.
8. Nel campo **Risorsa** la ricerca mostra tutte le risorse con le competenze richieste. Selezionare **Daniel Goldschmidt** e quindi **Crea**.
9. Nella pagina **Progetto** selezionare **Aggiungi**.
10. Nel riquadro **Aggiungi ruoli al progetto**, campo **Ruolo**, selezionare **Membro del team**. Nel campo **Numero di risorse** immettere **5**.
11. Selezionare **Crea**.
12. Nella pagina **Progetti** selezionare **Soddisfa capacità risorsa**.

## <a name="monitor-project-teams"></a>Monitorare i team di progetto
1. Nella pagina **Tutti i progetti**, selezionare il collegamento **ID progetto** per il progetto **Fase 2 di aggiornamento di XYZ**.
2. Nella Scheda dettaglio **Team progetto e programmazione** verificare che le risorse del progetto elencate siano corrette.
