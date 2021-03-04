---
title: Creare un nuovo layout di magazzino
description: In questo argomento viene descritto come impostare le informazioni sulle ubicazioni in un magazzino.
author: perlynne
manager: tfehr
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 09666e95cc90913f1bf8555b9ff2c48aa55369ed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431413"
---
# <a name="create-a-new-warehouse-layout"></a>Creare un nuovo layout di magazzino

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come impostare le informazioni sulle ubicazioni in un magazzino. È applicabile solo ai magazzini creati utilizzando "Operazioni di magazzino di base" del modulo Gestione inventario, non ai magazzini creati nel modulo Gestione magazzino. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.


## <a name="set-the-default-location-capacity"></a>Impostare la capacità dell'ubicazione predefinita
1. Nel pannello di navigazione, andare a **Moduli > Gestione magazzino > Impostazione > Parametri di gestione articoli e magazzino**.
2. Selezionare la scheda **Ubicazioni**.
3. Nel campo **Larghezza standard** immettere un numero.
4. Nel campo **Profondità standard** immettere un numero.
5. Nel campo **Altezza standard** immettere un numero.
6. Selezionare **Salva**.
7. Chiudere la pagina.

## <a name="define-the-location-name-format"></a>Definire il formato del nome dell'ubicazione
1. Nel pannello di navigazione andare a **Moduli > Gestione articoli > Impostazione > Attività periodiche > Suddivisione scorte > Magazzini**.
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Magazzino**.
4. Digitare un valore nel campo **Nome**.
5. Nel campo **Sito** selezionare il record desiderato nella ricerca.
6. Attivare/disattivare l'espansione della sezione **Nomi ubicazioni**. Le opzioni di questa sezione definiscono il formato predefinito per i nomi delle ubicazioni. Nel nostro esempio, includeremo il numero di sezione, il numero di scaffale e il numero di ripiano.  
7. Impostare l'opzione **Includi sezione** su **Sì**.
8. Impostare l'opzione **Includi scaffale** su **Sì**. 
9. Nel campo **Formato** digitare un valore per lo scaffale.
10. Impostare l'opzione **Includi ripiano** su **Sì**.
11. Nel campo **Formato** digitare un valore per il ripiano.

## <a name="define-warehouse-locations"></a>Definire le ubicazioni di magazzino
1. Nel riquadro azioni selezionare **Magazzino**.
2. Selezionare **Creazione guidata ubicazione**.
3. Selezionare **Avanti**.
4. Deselezionare l'opzione **Banchine di uscita**.
5. Deselezionare l'opzione **Ubicazioni di stoccaggio**.
6. Selezionare **Avanti** fino a che non viene visualizzato **Fine**.
7. Chiudere la pagina.
8. Aggiorna la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]