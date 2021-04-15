---
title: Integrare la gestione cespiti con cespiti
description: Questo argomento spiega come integrare i moduli Cespiti e Gestione cespiti, in modo da poter collegare i cespiti ai cespiti in manutenzione.
author: kamaybac
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: a45bf1f62cdcc8abed2ec157a223e7f3fddec7ce
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809856"
---
# <a name="integrate-asset-management-with-fixed-assets"></a>Integrare la gestione cespiti con cespiti

[!include [banner](../../includes/banner.md)]

Integrando i moduli **Gestione cespiti** e **Cespiti** è possibile collegare i cespiti ai cespiti in manutenzione. Gli utenti di cespiti possono quindi creare un cespite in manutenzione da un cespite nuovo o esistente e gli utenti della gestione cespiti possono associare un cespite in manutenzione con un cespite esistente. Questa funzione consente inoltre agli utenti di cespiti di visualizzare facilmente i costi registrati dagli ordini di lavoro per i relativi cespiti in manutenzione.

> [!NOTE]
> In questo argomento, i *cespiti in manutenzione* si riferiscono ai cespiti del modulo **Gestione cespiti** e i *cespiti* si riferiscono ai cespiti del modulo **Cespiti**.

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a>Impostare un ubicazione predefinita per i nuovi cespiti in manutenzione creati dai cespiti (facoltativo)

Questa configurazione opzionale consente di impostare un'unità funzionale predefinita per i nuovi cespiti in manutenzione creati da cespiti. In genere questa configurazione viene eseguita solo una volta, se la si completa del tutto.

Per completare la configurazione, attenersi alla procedura seguente.

1. Fare clic su **Gestione cespiti \> Impostazione \> Parametri di gestione cespiti**.
1. Nella scheda **Cespiti**, nel campo **Unità funzionale** , selezionare l'unità predefinita.
1. Nel riquadro azioni selezionare **Salva**.

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a>Utilizzare cespiti e cespiti in manutenzione integrati

Questa sezione fornisce una raccolta di procedure che mostrano vari modi per utilizzare le funzionalità di gestione cespiti e cespiti integrate.

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a>Associare un cespite in manutenzione esistente a un cespite

Per associare un cespite in manutenzione esistente a un cespite, effettuare le seguenti operazioni.

1. Andare a **Gestione cespiti \> Cespiti \> Tutti i cespiti** (o **Cespiti attivi**).
1. Selezionare un cespite.
1. Nella scheda dettaglio **Cespiti**, nel campo **Numero cespite**, selezionare un cespite esistente.
1. Nel riquadro azioni selezionare **Salva**.

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a>Visualizzare il cespite associato a un cespite in manutenzione selezionato

Per visualizzare il cespite associato a un cespite in manutenzione selezionato, effettuare le seguenti operazioni.

1. Andare a **Gestione cespiti \> Cespiti \> Tutti i cespiti** (o **Cespiti attivi**).
1. Selezionare un cespite.
1. Nella scheda dettaglio **Cespiti**, nel campo **Numero cespiti**, selezionare il collegamento.

    Viene visualizzata la pagina **Cespiti** per il cespite selezionato. (In genere, questa pagina è disponibile in **Cespiti \> Cespiti \> Cespiti**).

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a>Visualizzare il cespite di manutenzione associato a un cespite selezionato

Per visualizzare il cespite associato a un cespite di manutenzione selezionato, effettuare le seguenti operazioni.

1. Passare a **Cespiti \> Cespiti \> Cespiti**.
1. Selezionare un cespite.
1. Nella scheda **Gestione cespiti** del riquadro azioni, nel gruppo **Visualizza**, selezionare **Cespite in manutenzione**.

    Viene visualizzata la pagina **Cespite in manutenzione** per il cespite associato al cespite selezionato. (In genere, questa pagina è disponibile in **Gestione cespiti \> Cespiti \> Tutti i cespiti**).

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a>Visualizzare i costi di manutenzione associati a un cespite

Gli ordini di lavoro di gestione cespiti possono essere registrati per i cespiti in manutenzione e ognuno di questi ordini di lavoro ha in genere un costo. Quando un cespite è associato a un cespite in manutenzione, è possibile passare direttamente dal cespite per visualizzare i relativi costi.

Per visualizzare i costi di manutenzione associati a un cespite, effettuare le seguenti operazioni.

1. Passare a **Cespiti \> Cespiti \> Cespiti**.
1. Selezionare un cespite.
1. Nella scheda **Gestione cespiti** del riquadro azioni, nel gruppo **Visualizza**, selezionare **Costo di manutenzione**.

    Viene visualizzata la pagina **Costo di manutenzione** con i relativi costi.

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a>Creare un nuovo cespite in manutenzione per un cespite esistente

Per creare un nuovo cespite in manutenzione per un cespite esistente, effettuare le seguenti operazioni.

1. Passare a **Cespiti \> Cespiti \> Cespiti**.
1. Selezionare un cespite.
1. Nella scheda **Gestione cespiti** del riquadro azioni, nel gruppo **Nuovo**, selezionare **Crea cespite in manutenzione**. (Se questa opzione non è disponibile, un cespite in manutenzione potrebbe già essere associato al cespite selezionato).
1. Terminare la creazione del cespite come descritto in [Creare un cespite](../objects/create-an-object.md).

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a>Creare un nuovo cespite e aggiungere un nuovo cespite in manutenzione

Per creare un nuovo cespite e aggiungere un nuovo cespite in manutenzione, effettuare le seguenti operazioni.

1. Passare a **Cespiti \> Cespiti \> Cespiti**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Terminare la creazione del cespite come descritto in [Creare un cespite](../../../finance/fixed-assets/tasks/create-fixed-asset.md).
1. Nella scheda **Gestione cespiti** del riquadro azioni, nel gruppo **Nuovo**, selezionare **Crea cespite in manutenzione**.
1. Terminare la creazione del cespite come descritto in [Creare un cespite](../objects/create-an-object.md).

### <a name="remove-the-association-between-two-assets"></a>Rimuovere l'associazione tra due cespiti

In alcuni casi, potrebbe essere necessario annullare l'associazione di un cespite in manutenzione dal relativo cespite. Ad esempio, se vuoi [creare un nuovo cespite in manutenzione](#new-maintenance-from-fixed) da un cespite, è necessario prima rimuovere qualsiasi associazione esistente.

Per rimuovere un'associazione esistente tra un cespite in manutenzione e un cespite, effettuare le seguenti operazioni.

1. Andare a **Gestione cespiti \> Cespiti \> Tutti i cespiti** (o **Cespiti attivi**).
1. Trovare e aprire il cespite.
1. Nella scheda dettaglio **Cespite** cancellare il valore nel campo **Unità funzionale**.
1. Nel riquadro azioni selezionare **Salva**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]