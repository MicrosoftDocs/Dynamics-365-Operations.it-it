---
title: Impostare criteri di lavoro del magazzino (Applicazione, maggio 2016)
description: I processi del magazzino non includono sempre il lavoro in magazzino.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy, WMSLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 62fbf2f44216c300af5e092f5dbd05ef2239321b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216783"
---
# <a name="set-up-warehouse-work-policies-application-may-2016"></a>Impostare criteri di lavoro del magazzino (Applicazione, maggio 2016)

[!include [banner](../../includes/banner.md)]

I processi del magazzino non includono sempre il lavoro in magazzino. Definendo i criteri di lavoro, è possibile impedire la creazione di lavoro per il prelievo delle materie prime e lo stoccaggio di prodotti finiti per un set di prodotti in ubicazioni specifiche. La società di dati dimostrativi USMF è stata utilizzata per creare questa registrazione. Questa guida attività richiede l'applicazione Dynamics AX 7.0.1 o versione successiva.

1. Andare a Gestione magazzino > Impostazioni > Lavoro > Criteri di lavoro.
2. Fare clic su Nuovo.
3. Nel campo Nome criteri di lavoro digitare “No lavoro di stoccaggio".
4. Fare clic su Salva.
5. Scegliere Aggiungi.
6. Nell'elenco contrassegnare la riga selezionata.
7. Nel campo Tipo ordine di lavoro selezionare "Stoccaggio prodotti finiti".
8. Scegliere Aggiungi.
9. Nell'elenco contrassegnare la riga selezionata.
10. Nel campo Tipo ordine di lavoro selezionare "Stoccaggio co-prodotti e sottoprodotti".
11. Espandere la sezione Ubicazioni di magazzino.
12. Scegliere Aggiungi.
13. Nell'elenco contrassegnare la riga selezionata.
14. Nell'elenco di magazzino immettere "51".
15. Nel campo Ubicazione immettere o selezionare "001".
16. Espandere la sezione Prodotti.
17. Nel campo Selezione prodotto selezionare "Selezionato".
18. Scegliere Aggiungi.
19. Nell'elenco contrassegnare la riga selezionata.
20. Nel campo Numero articolo immettere o selezionare "L0101".
21. Fare clic su Salva.

