---
title: Impostare gerarchie organizzative
description: In questo argomento viene descritto come impostare gerarchie organizzative in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 29d4b686cbb66715196fca06e4642fbb8a337ace
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413417"
---
# <a name="set-up-organization-hierarchies"></a>Impostare gerarchie organizzative


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come impostare gerarchie organizzative in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Prima di creare canali, è necessario confermare che le gerarchie organizzative siano state impostate.

È possibile utilizzare gerarchie organizzative per la visualizzazione e il reporting dell'attività aziendale da varie prospettive. È possibile impostare, ad esempio, una gerarchia per una dichiarazione fiscale, legale o statutaria. È quindi possibile impostare un'altra gerarchia per il reporting di informazioni finanziarie non obbligatorio per legge, ma utilizzato per la creazione di report interni.

Prima di creare una gerarchia organizzativa, è necessario creare organizzazioni. Per ulteriori informazioni, vedere [Creare persone giuridiche](channels-legal-entities.md) o [Creare un'unità operativa](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).


Per ulteriori informazioni, vedere i seguenti argomenti:
- [Panoramica organizzazioni e gerarchie organizzative](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [Pianificazione della gerarchia organizzativa](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [Creare una gerarchia organizzativa](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a>Creare una gerarchia organizzativa

Per creare una gerarchia organizzativa, effettuare le seguenti operazioni.

1. Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Gerarchie organizzative**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Nome** immettere un valore.
1. Nella sezione **Scopo**, selezionare **Assegna scopo**.
1. Nell'elenco trovare e selezionare il record desiderato. Selezionare uno scopo da assegnare alla propria gerarchia organizzativa.
1. Nella sezione **Gerarchie assegnate**, selezionare **Aggiungi**.
1. Nell'elenco contrassegnare la riga selezionata. Individuare la gerarchia appena creata.
1. Selezionare **OK**.

L'immagine seguente mostra un esempio di gerarchia organizzativa creata per un gruppo di punti vendita fittizio "Adventure Works".

![Esempio di gerarchie organizzative](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a>Aggiungere organizzazioni a una gerarchia

Per aggiungere organizzazioni a una gerarchia, effettuare le operazioni indicate di seguito.

1. Nell'elenco trovare e selezionare il record desiderato. Selezionare la propria gerarchia.
1. Nel riquadro azioni selezionare **Visualizza**.
1. Aggiungere organizzazioni in base alle necessità.
1. Per aggiungere un'organizzazione, selezionare **Modifica** e quindi selezionare **Inserisci**. Dopo avere apportato le modifiche, è possibile salvare una bozza e pubblicare le modifiche.

L'immagine seguente mostra una persona giuridica aggiunta alla radice della gerarchia con quattro centri di costo aggiunti per i canali "Centro commerciale", "Outlet", "Online" e "Servizio clienti". A ognuno di questi possono quindi essere aggiunti vari canali di vendita al dettaglio, servizio clienti e online.

![Esempio di finestra di progettazione delle gerarchie](media/hierarchy-designer.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica organizzazioni e gerarchie organizzative](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Pianificazione della gerarchia organizzativa](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Creare persone giuridiche](channels-legal-entities.md)

[Creare unità operative](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[Panoramica dei canali](channels-overview.md)

[Prerequisiti di impostazione dei canali](channels-prerequisites.md)
