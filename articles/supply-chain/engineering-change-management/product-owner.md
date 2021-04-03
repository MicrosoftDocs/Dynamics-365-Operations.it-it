---
title: Proprietari del prodotto
description: Vengono fornite le informazioni sui proprietari di prodotto. Un proprietario di prodotto è un gruppo di utenti responsabili di prodotti specifici. Solo i membri del gruppo possono rilasciare questi prodotti. Il proprietario di prodotto può essere utilizzato anche nel flusso di lavoro di approvazione.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: a1c3bc6f77fed83cfbbd502cdd469baa491fd81f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5266129"
---
# <a name="product-owners"></a>Proprietari del prodotto

[!include [banner](../includes/banner.md)]

Il proprietario di prodotto è un gruppo di utenti responsabili di prodotti specifici. Quando un gruppo di proprietari di prodotto viene assegnato a un prodotto, solo i membri di quel gruppo possono rilasciare il prodotto. Il proprietario di prodotto può essere utilizzato nel flusso di lavoro di approvazione nella gestione delle modifiche di progettazione.

I proprietari di prodotto sono impostazioni globali. Pertanto, sono disponibili per tutte le persone giuridiche.

## <a name="create-a-product-owner-group"></a>Creare un gruppo di proprietari di prodotto

Per creare un gruppo di proprietari di prodotto e aggiungervi membri, seguire questi passaggi.

1. Andare a **Gestione modifiche di progettazione \> Impostazione \> Proprietari di prodotti**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **Proprietario di prodotto** immettere un nome per il gruppo.
4. Nel campo **Nome** immettere una descrizione del gruppo.
5. Nella scheda dettaglio **Membri** aggiungere i lavoratori che devono essere membri del gruppo.

## <a name="assign-a-product-owner-to-a-product"></a>Assegnare un proprietario di prodotto a un prodotto

Per assegnare un proprietario di prodotto a un prodotto, attenersi alla procedura seguente.

1. Aprire la pagina **Dettagli prodotto** per il prodotto o la rappresentazione generale prodotto in questione.
1. Nella Scheda dettaglio **Generale** impostare il campo **Proprietario del prodotto** sul nome del gruppo di proprietari di prodotto pertinente.

Mentre un proprietario di prodotto è assegnato a un prodotto, solo i membri del gruppo del proprietario di prodotto possono modificare l'impostazione **Proprietario del prodotto**.

Il proprietario del prodotto è visibile anche nella pagina **Prodotti rilasciati**.

## <a name="product-owners-and-product-releases"></a>Proprietari di prodotto e versioni del prodotto

Solo gli utenti del gruppo di proprietari di un prodotto possono rilasciare quel prodotto. Tuttavia, esiste un'eccezione quando il prodotto è un articolo figlio e il suo elemento padre viene rilasciato dal proprietario dell'elemento padre. In altre parole, se il prodotto fa parte della DBA di un altro prodotto, il sistema non controlla il proprietario del prodotto di ogni articolo nella DBA. Controlla solo il proprietario del prodotto dell'articolo padre.

Ad esempio, il prodotto X è assegnato al gruppo di proprietari di prodotto *Armadi di design*. Il prodotto X fa anche parte della distinta base del prodotto Y, che è assegnato a gruppo di proprietari del prodotto *Altoparlanti di design*. Se un utente del gruppo di proprietari del prodotto *Altoparlanti di design* rilascia il prodotto Y e la relativa distinta base, il prodotto X verrà rilasciato insieme al prodotto Y.

## <a name="product-owners-and-approvals"></a>Proprietari e approvazioni dei prodotti

Poiché i proprietari dei prodotti sanno se modifiche di progettazione specifiche andranno a vantaggio dei loro prodotti, spesso ha senso includerle come parte del processo di approvazione nella gestione delle modifiche di progettazione. È possibile implementare questo approccio impostando i proprietari di prodotto come fornitori partecipanti nei flussi di lavoro utilizzati per la gestione delle modifiche di progettazione. Il sistema assegnerà quindi le attività di approvazione nei flussi di lavoro, in base ai prodotti presenti nelle richieste di modifica di progettazione e negli ordini di modifica di progettazione. Per ulteriori informazioni, vedere [Gestire le modifiche ai prodotti di progettazione](engineering-change-management.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]