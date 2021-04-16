---
title: Crea un modello di configurazione prodotto
description: Questa procedura mostra come creare un modello di configurazione prodotto e immettere le informazioni di base,ad esempio gli attributi e i sottocomponenti.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b87b411ed24f89a674ec3fb7ac44d3ab1d8a720a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819988"
---
# <a name="create-a-product-configuration-model"></a>Crea un modello di configurazione prodotto

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come creare un modello di configurazione prodotto e immettere le informazioni di base,ad esempio gli attributi e i sottocomponenti. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-a-product-model"></a>Creare un modello prodotto
1. Fare clic su Definizione modello di variante prodotto.
2. Fare clic su Modelli di configurazione prodotto.
3. Fare clic su Nuovo.
4. Digitare un valore nel campo Nome.
5. Nel campo Descrizione digitare un valore.
6. Selezionare un'opzione nel campo Strategia risolutore.
    * La strategia risolutore determina come vengono elaborati i vincoli di un modello di configurazione prodotto basata su vincoli. Questa opzione può avere impatto sulle prestazioni del modello di configurazione prodotto.  
7. Digitare un valore nel campo Nome.
    * Il componente radice rappresenta il modello di configurazione prodotto, ma può essere utilizzato in altri modelli prodotto.  
8. Fare clic su OK.
9. Selezionare un'opzione nel campo Riutilizza configurazioni.
    * Se il parametro per riutilizzare le configurazioni è impostato su Sì, il sistema cercherà configurazioni identiche dopo ogni sessione di configurazione e riutilizzerà la corrispondenza esatta eventualmente rilevata.  

## <a name="add-attributes"></a>Aggiungi attributi
1. Espandere la sezione Attributi.
2. Scegliere Aggiungi.
3. Nell'elenco contrassegnare la riga selezionata.
4. Digitare un valore nel campo Nome.
5. Digitare un valore nel campo Nome risolutore.
    * Il nome risolutore viene utilizzato dal risolutore vincolo della configurazione prodotto. Non deve includere spazi o caratteri speciali, eccetto il carattere _ (sottolineatura).  
6. Nel campo Descrizione digitare un valore.
    * Il testo di descrizione viene visualizzato all'utente della configurazione e può pertanto essere utilizzato come guida nella selezione del valore di attributo corretto.  
7. Nel campo Tipo di attributo, immettere o selezionare un valore.
    * Il tipo di attributo determina i valori disponibili per l'attributo.  
8. Selezionare la casella di controllo Includi in riutilizzo.
    * Questa opzione è disponibile solo se è selezionata l'opzione Riutilizza configurazioni. Se si aggiunge l'attributo nella casella di controllo del riutilizzo, questo attributo verrà considerato quando il sistema effettua la ricerca della corrispondenza esatta.  

## <a name="add-subcomponents"></a>Aggiungere sottocomponenti
1. Espandere la sezione Sottocomponenti.
2. Scegliere Aggiungi.
3. Nell'elenco contrassegnare la riga selezionata.
4. Digitare un valore nel campo Nome.
5. Digitare un valore nel campo Nome risolutore.
6. Nel campo Descrizione digitare un valore.
7. Nel campo Componente immettere o selezionare un valore.
    * Ogni sottocomponente deve fare riferimento a una definizione di componente. La progettazione supporta i componenti riutilizzabili e garantisce che un componente definito possa essere utilizzato in più modelli prodotto.  
8. Fare clic su Salva.
9. Fare clic su Dettagli riga DBA.
    * Il modulo dei dettagli della riga DBA consente all'utente di selezionare le proprietà richieste per il sottocomponente. Per ogni proprietà può essere specificato un valore fisso o sottoposto al mapping a un attributo. Il mapping a un attributo determina che la proprietà riga DBA abbia valori diversi a seconda della selezione della configurazione.  
10. Nel campo Numero di articoli immettere o selezionare un valore.
    * Ogni sottocomponente rappresenta una rappresentazione generale prodotto configurabile con la tecnologia di configurazione basata su vincoli. Il riferimento viene effettuato tramite il numero di articolo.  
11. Selezionare la casella di controllo Imposta.
12. Selezionare Sì nel campo Calcolo.
    * Impostando l'opzione di calcolo si garantisce che il prodotto venga incluso durante l'esecuzione di un calcolo dei costi per il prodotto.  
13. Fare clic sulla scheda Impostazioni.
14. Selezionare la casella di controllo Imposta.
15. Nel campo Quantità immettere un numero.
    * Il campo della quantità determina la quantità del prodotto che verrà utilizzata nel prodotto configurato.  
16. Selezionare la casella di controllo Imposta.
17. Nel campo Per serie, immettere un numero.
18. Fare clic su OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]