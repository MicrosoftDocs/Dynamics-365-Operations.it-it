--- 
title: Creare una risorsa operativa
description: "Una risorsa operativa esegue le attività di un progetto o di un processo di produzione."
author: sorenva
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: aa80e4b22d116c8f580c9aefe7c114cfe1d19cc8
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---
# <a name="create-an-operations-resource"></a>Creare una risorsa operativa

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Una risorsa operativa esegue le attività di un progetto o di un processo di produzione. In questa procedura viene illustrato come definire una risorsa operativa. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.

1. Fare clic su Risorse.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Risorsa.
4. Nel campo Descrizione digitare un valore.

## <a name="define-capacity-and-consumption-parameters"></a>Definire i parametri di capacità e consumo.
1. Espandere la sezione Operazione.
2. Immettere un numero nel campo Percentuale scarti.
3. Nel campo Categoria tempo di attrezzaggio immettere o selezionare un valore.
    * Specificare la categoria di costi che determina come rappresentare il costo di attrezzaggio.  
4. Nel campo Categoria tempo di esecuzione immettere o selezionare un valore.
    * Specificare la categoria di costi che determina come rappresentare il tempo di esecuzione.  
5. Nel campo Categoria quantità immettere o selezionare un valore.
    * Specificare la categoria di costi che determina come rappresentare il costo delle risorse in base alla quantità di output.  
6. Selezionare un'opzione nel campo Unità di capacità.
    * Specificare l'unità in cui esprimere la capacità della risorsa operativa.  
7. Immettere un numero nel campo Capacità.
8. Immettere un numero nel campo Percentuale efficienza.
    * Specificare l'efficienza che ci si attende dalla risorsa operativa. La percentuale di efficienza consente di rettificare la produttività di una risorsa operativa e influisce sul tempo riservato per la risorsa.  
9. Nel campo Percentuale programmazione operazioni, immettere un numero.
    * Specificare la percentuale massima di capacità della risorsa operativa che si desidera utilizzare nella programmazione delle operazioni.  
10. Selezionare Sì nel campo Capacità limitata.
    * Impostare questa opzione su Sì se la risorsa operativa deve essere programmata in base all'effettiva capacità disponibile e se devono essere considerate le prenotazioni esistenti della capacità. Se l'opzione è impostata su No, si presuppone che la risorsa operativa abbia una capacità infinita e la risorsa può essere prenotata in eccesso.  
11. Selezionare Sì nel campo Risorsa collo di bottiglia.

## <a name="define-working-times"></a>Definire gli orari di lavoro
1. Espandere la sezione Calendari.
2. Scegliere Aggiungi.
3. Nel campo Calendario immettere o selezionare un valore.
    * Specificare il calendario dell'orario di lavoro che definisce la capacità (in ore) della risorsa.  
4. Nell'elenco trovare e selezionare il record desiderato.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="define-resource-capabilities"></a>Definire le capacità delle risorse
1. Espandere la sezione Capacità.
2. Scegliere Aggiungi.
    * Si definisce capacità l'idoneità di una risorsa operativa di eseguire un'attività specifica. Il motore di programmazione alloca le risorse abbinando i requisiti risorsa di ogni attività alle capacità delle risorse operative disponibili.  
3. Nel campo Capacità immettere o selezionare un valore.
4. Nel campo Livello immettere un numero.
    * Specificare il livello di competenza in base al quale la risorsa elabora la capacità.  
5. Nel campo Priorità immettere un numero.
    * Specificare la priorità della risorsa operativa in relazione alla capacità. Nella programmazione in base alla priorità, viene selezionata per prima la risorsa operativa con la priorità più alta (valore numerico più basso).  

## <a name="assign-resource-to-resource-group"></a>Assegna risorsa al gruppo di risorse
1. Espandere la sezione Gruppi di risorse.
2. Scegliere Aggiungi.
    * Il gruppo di risorse definisce il contesto di sito, unità di produzione e magazzino per le risorse operative. La risorsa operativa può essere programmata solo quando è assegnata a un gruppo di risorse e solo sul sito in cui si trova il gruppo.  
3. Nel campo Gruppo di risorse immettere o selezionare un valore.
4. Nel campo Ubicazione di input immettere o selezionare un valore.
    * Specificare il percorso del magazzino da cui la risorsa operativa sta utilizzando i materiali.  


