---
title: Ammortamento del consumo
description: Questo articolo fornisce una panoramica del metodo di ammortamento basato su consumo.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 7fa432ebfc433b6396589df053b2b485b2ec6dbd
ms.lasthandoff: 03/31/2017


---

# <a name="consumption-depreciation"></a>Ammortamento del consumo

Questo articolo fornisce una panoramica del metodo di ammortamento basato su consumo.

Quando si imposta un profilo di ammortamento per i cespiti e si seleziona l'opzione **Consumo** nel campo **Metodo** della pagina **Profili di ammortamento**, l'assegnazione dei cespiti al profilo di ammortamento è basata sul loro utilizzo. Non è necessario impostare le percentuali e gli intervalli nella pagina **Profili di ammortamento**. Dopo avere creato un profilo di ammortamento che utilizza il metodo Consumo, è possibile impostare il metodo in diversi modi.

## <a name="set-up-and-use-consumption-depreciation"></a>Impostare l'ammortamento del consumo
1.  Nella pagina **Profili di ammortamento**, creare il profilo di ammortamento. Per i calcoli del consumo, il profilo di ammortamento deve avere un ID e un nome e **Consumo** deve essere selezionato nel campo **Metodo**.
2.  Nella pagina **Fattori di consumo**, impostare i fattori di consumo. Ogni fattore di consumo deve avere un ID e un nome e un fattore di consumo specificato come percentuale o quantità.
3.  Nella pagina **Unità di consumo**, impostare le unità di consumo. Ogni unità di consumo deve avere un ID e un nome. Le unità di ammortamento vengono utilizzate per calcolare l'ammortamento basato sul consumo nella pagina **Ammortamento consumo**. Esempi di unità sono chilometro (km), chilogrammo (kg) e ora.
4.  Nella pagina **Cespiti**, impostare i singoli cespiti. Per ogni cespite, selezionare modelli di valore e registri beni ammortizzabili con profili di ammortamento. È necessario impostare i modelli di valore o i registri beni ammortizzabili per l'ammortamento del consumo, se si hanno cespiti che utilizzano i profili di ammortamento in base al metodo di Consumo. Questa impostazione viene effettuata nella scheda **Ammortamento** della pagina **Modelli di valore** o nella scheda dettaglio **Generale** della pagina **Profilo di ammortamento**. È possibile utilizzare lo stesso modello di valore per più cespiti. I profili di ammortamento fanno parte del modello di valore o del registro beni ammortizzabili selezionato per ogni cespite. Non è possibile aggiungere o modificare profili di ammortamento direttamente nella pagina **Cespiti**. È possibile modificare i profili di ammortamento solo nella pagina **Registri beni ammortizzabili**.
5.  Nella pagina **Modelli di valore** o **Registro beni ammortizzabili** immettere le informazioni nei seguenti campi del gruppo di campi **Ammortamento consumo**:
    -   Fattore di consumo
    -   Unità
    -   Ammortamento unità
    -   Consumo stimato

    Nel campo** Consumo registrato** è indicato l'ammortamento basato sul consumo, in unità, già registrato per la combinazione di cespite e modello di valore o per il registro beni ammortizzabili. Non è possibile aggiornare manualmente il valore del campo.

## <a name="examples"></a>Esempi
### <a name="example-1"></a>Esempio 1

Viene impostato il seguente fattore di consumo per il 31 gennaio:

-   La quantità è 1.000.
-   Il prezzo di ammortamento di unità specificato per il cespite è 1,5.

La proposta di ammortamento il 31 gennaio è la seguente: I × 1,5 = 1.500 di ammortamento di unità × quantità di 1.000 se il fattore specificato per il cespite è un fattore percentuale, la quantità che viene stimata **Consumo stimato** nel campo per il modello di valore del cespite verranno invece moltiplicati per la percentuale impostata per la data di fine selezionata. Questa quantità verrà suggerita come quantità di ammortamento per il periodo.

### <a name="example-2"></a>Esempio 2

Viene impostato il seguente fattore di ammortamento basato sul consumo per il 31 gennaio:

-   La percentuale è 10%.
-   Il prezzo di ammortamento di unità specificato per il cespite è 1,5.
-   La quantità stimata del cespite è 2.000.

La proposta di ammortamento il 31 gennaio è la seguente: Quantità stimata × Percentuale x Ammortamento unità 2.000 × ,10 × 1,5 = 300


