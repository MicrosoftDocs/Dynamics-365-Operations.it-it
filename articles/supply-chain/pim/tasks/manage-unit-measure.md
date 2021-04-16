---
title: Gestire unità di misura
description: Questa procedura illustra come definire un'unità di misura, come fornire conversioni per l'unità e la relativa descrizione e come definire le regole di conversione per le unità correlate.
author: sorenva
ms.date: 07/08/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 966e189e7395bec15d2c62735c6df3df2ab34b8a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817967"
---
# <a name="manage-unit-of-measure"></a>Gestire unità di misura

[!include [banner](../../includes/banner.md)]

Questa procedura illustra come definire un'unità di misura, come fornire conversioni per l'unità e la relativa descrizione e come definire le regole di conversione per le unità correlate. È possibile eseguire questa procedura nella società di dati dimostrativi oppure utilizzando i propri dati.

1. Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Gestione prodotti rilasciati**.
2. Fare clic su **Unità**.

## <a name="create-a-unit-of-measure"></a>Creare un'unità di misura
1. Fare clic su **Nuovo**.
2. Digitare un valore nel campo **Unità**. Immettere l'ID o il simbolo da utilizzare quando si fa riferimento all'unità di misura.  
3. Digitare un valore nel campo **Descrizione** Immettere un nome descrittivo dell'unità di misura specificato nella lingua del sistema.  
4. Selezionare un'opzione nel campo **Classe di unità di misura**. La classe di unità di misura definisce il raggruppamento logico, ad esempio area, massa o quantità, a cui l'unità di misura appartiene.  
5. Nel campo **Precisione decimale** immettere un numero. Specificare il numero di decimali da utilizzare per l'arrotondamento dell'unità di misura convertita dopo il completamento di un calcolo.  
6. Fare clic su **Salva**.

## <a name="define-unit-translations"></a>Definire conversioni unità
1. Nel **riquadro azioni** fai clic su **Testi unità**.
2. Fare clic su **Nuovo**. Utilizzare il testo unità per creare una traduzione dell'ID o di un simbolo che rappresenta l'unità di misura per l'utilizzo in documenti esterni in lingue specifiche del fornitore o del cliente.  
3. Nel campo **Lingua** immettere o selezionare un valore.
4. Digitare un valore nel campo **Testo**.
5. Fare clic su **Salva**.
6. Chiudere la pagina.
7. Nel **riquadro azioni** fai clic su **Descrizioni unità convertite**.
8. Fare clic su **Nuovo**. Definire descrizioni specifiche di una lingua per l'unità di misura.  
9. Nel campo **Lingua** immettere o selezionare un valore.
10. Digitare un valore nel campo **Descrizione**
11. Fare clic su **Salva**.
12. Chiudere la pagina.

## <a name="define-unit-conversion-rules"></a>Definire regole di conversione unità
1. Nel **riquadro azioni** fai clic su **Conversioni unità**. Definire le regole per la conversione dell'unità di misura verso e da altre unità di misura incluse nella classe di unità di misura selezionata.  
2. Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.
3. Nel campo **Fattore** immettere un numero. Fattore di conversione tra Dall'unità e All'unità. Il fattore di conversione, ad esempio, da centimetro a metro è 100 perché in un metro sono presenti 100 centimetri.  
4. Nel campo **All'unità** immettere o selezionare un valore.
5. Selezionare un'opzione nel campo **Arrotondamento**. Definire il modo in cui il valore convertito deve essere arrotondato.  
6. Fare clic su **OK**.
7. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]