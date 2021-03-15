---
title: Creare elenchi di attività e aggiungere attività
description: Questo argomento descrive come creare elenchi di attività e aggiungervi le attività in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: cca5e0efd6516d02c372e8a616b6bb0c39f3088c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006212"
---
# <a name="create-task-lists-and-add-tasks"></a>Creare elenchi di attività e aggiungere attività

[!include [banner](includes/banner.md)]

Questo argomento descrive come creare elenchi di attività e aggiungervi le attività in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un'*attività* definisce un lavoro specifico o un'azione che qualcuno deve completare entro una data di scadenza specificata. In Dynamics 365 Commerce, un'attività può includere istruzioni dettagliate e informazioni su una persona di contatto. Può anche includere i collegamenti a operazioni di back-office, operazioni di punti vendita (POS) o pagine del sito, per contribuire a migliorare la produttività e fornire il contesto richiesto dal proprietario dell'attività per completare l'attività in modo efficiente.

Un *elenco delle attività* è una raccolta di attività che devono essere completate come parte di un processo aziendale. Ad esempio, potrebbe esserci un elenco di attività che un nuovo lavoratore deve completare durante l'inserimento, un elenco di attività per cassieri che lavorano in turni serali o un elenco di attività che devono essere completate per preparare il negozio per le prossime festività. In Commerce, ogni elenco di attività che ha una data stabilita può essere assegnata a un numero qualsiasi di negozi o dipendenti e può essere configurata come ricorrente.

Sia i manager che i lavoratori possono creare elenchi di attività nel back office di Commerce e quindi assegnarli a un set di negozi.

## <a name="create-a-task-list"></a>Creare un elenco di attività

Per creare un elenco di attività, completare i passaggi che seguono.

1. Andare a **Retail e Commerce \> Gestione delle attività \> Amministrazione gestione delle attività**.
1. Selezionare **Nuovo**, quindi immettere i valori nei campi **Nome**, **Descrizione** e **Proprietario**.
1. Selezionare **Salva**.

## <a name="add-tasks-to-a-task-list"></a>Aggiungere attività a un elenco di attività

Per aggiungere attività a un elenco di attività, effettuare le operazioni indicate di seguito.
 
1. Nella scheda dettaglio **Attività** di un elenco attività esistente, selezionare **Nuovo** per aggiungere un'attività.
1. Nella finestra di dialogo **Crea una nuova attività**, nel campo **Nome** immettere un nome per l'attività.
1. Nel campo **Offset data di scadenza da data stabilita**, immettere un valore intero positivo o negativo. Ad esempio, immettere **-2** se l'attività deve essere completata due giorni prima della data di scadenza dell'elenco attività.
1. Nel campo **Note** inserire le istruzioni dettagliate.
1. Nel campo **Contatto** immettere il nome di un esperto in materia che il proprietario dell'attività può contattare se ha bisogno di aiuto.
1. Nel campo **Collegamento attività** immettere un collegamento, in base alla natura dell'attività.

> [!TIP]
> Sebbene sia possibile utilizzare il campo **Assegnato a** per assegnare l'attività a qualcuno durante la creazione di un elenco di attività, si consiglia di evitare di assegnare l'attività durante la creazione dell'elenco di attività. Assegnare invece le attività dopo che è stata creata un'istanza dell'elenco per i singoli negozi.

## <a name="use-task-links-to-help-improve-worker-productivity"></a>Utilizzare i collegamenti delle attività per migliorare la produttività dei lavoratori

Commerce consente di collegare attività a specifiche operazioni POS, come l'esecuzione del report sulle vendite, la visualizzazione di un video di formazione online per l'orientamento di nuovi dipendenti o l'esecuzione di un'operazione di back-office. Questa funzione consente ai proprietari di attività di ottenere le informazioni necessarie per completare un'attività in modo efficiente.

Per aggiungere i collegamenti di attività mentre si crea un'attività, attenersi alla seguente procedura.

1. Nella scheda dettaglio **Attività** di un elenco attività esistente, selezionare **Modifica**.
1. Nella finestra di dialogo **Modifica attività**, nel campo **Collegamento attività**, selezionare una o più delle seguenti opzioni:

    - Selezionare **Voce di menu** per configurare un'operazione di back-office, ad esempio "Kit di prodotti".
    - Selezionare **Operazione POS** per configurare un'operazione POS, ad esempio "Report sulle vendite".
    - Selezionare **URL** per configurare un URL assoluto.

La seguente illustrazione mostra la selezione dei collegamenti delle attività nella finestra di dialogo **Modifica attività**.

![Selezione dei collegamenti di attività nella finestra di dialogo Modifica attività](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a>Configurare un'operazione POS in modo che possa essere collegata a un'attività

Per configurare un'operazione POS in modo che possa essere collegata a un'attività, attenersi alla procedura seguente.

1. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> POS \> Operazioni POS**.
1. Selezionare **Modifica**, trovare l'operazione POS e selezionare la casella di controllo **Abilita gestione attività**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della gestione attività](task-mgmt-overview.md)

[Configurare la gestione delle attività](task-mgmt-configure.md)

[Assegnare elenchi di attività a punti vendita o dipendenti](task-mgmt-assign-lists.md)

[Gestione delle attività in POS](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]