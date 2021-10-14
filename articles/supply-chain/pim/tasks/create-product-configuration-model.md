---
title: Crea un modello di configurazione prodotto
description: Questa procedura mostra come creare un modello di configurazione prodotto e immettere le informazioni di base,ad esempio gli attributi e i sottocomponenti.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca99c0346a3f982164076167c3429587aac18be6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568426"
---
# <a name="create-a-product-configuration-model"></a>Crea un modello di configurazione prodotto

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come creare un modello di configurazione prodotto e immettere le informazioni di base,ad esempio gli attributi e i sottocomponenti. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-a-product-model"></a>Creare un modello prodotto

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.
1. Selezionare **Nuovo**.
1. Digitare un valore nel campo **Nome**.
1. Digitare un valore nel campo **Descrizione**
1. Selezionare un'opzione nel campo **Strategia risolutore**.
    * La strategia risolutore determina come vengono elaborati i vincoli di un modello di configurazione prodotto basata su vincoli. Questa opzione può avere impatto sulle prestazioni del modello di configurazione prodotto.  
1. Digitare un valore nel campo **Nome**.
    * Il componente radice rappresenta il modello di configurazione prodotto, ma può essere utilizzato in altri modelli prodotto.  
1. Selezionare **OK**.
1. Selezionare un'opzione nel campo **Riutilizza configurazioni**.
    * Se il parametro per riutilizzare le configurazioni è impostato su Sì, il sistema cercherà configurazioni identiche dopo ogni sessione di configurazione e riutilizzerà la corrispondenza esatta eventualmente rilevata.  

## <a name="add-attributes"></a>Aggiungi attributi

1. Espandere la sezione **Attributi**.
2. Selezionare **Aggiungi**.
3. Nell'elenco contrassegnare la riga selezionata.
4. Digitare un valore nel campo **Nome**.
5. Digitare un valore nel campo **Nome risolutore**.
    * Il nome risolutore viene utilizzato dal risolutore vincolo della configurazione prodotto. Non deve includere spazi o caratteri speciali, eccetto il carattere _ (sottolineatura).  
6. Digitare un valore nel campo **Descrizione**
    * Il testo di descrizione viene visualizzato all'utente della configurazione e può pertanto essere utilizzato come guida nella selezione del valore di attributo corretto.  
7. Nel campo **Tipo di attributo**, immettere o selezionare un valore.
    * Il tipo di attributo determina i valori disponibili per l'attributo.  
8. Selezionare la casella di controllo **Includi in riutilizzo**.
    * Questa opzione è disponibile solo se è selezionata l'opzione Riutilizza configurazioni. Se si aggiunge l'attributo nella casella di controllo del riutilizzo, questo attributo verrà considerato quando il sistema effettua la ricerca della corrispondenza esatta.  

## <a name="add-subcomponents"></a>Aggiungere sottocomponenti

1. Espandere la sezione **Sottocomponenti**.
2. Selezionare **Aggiungi**.
3. Nell'elenco contrassegnare la riga selezionata.
4. Digitare un valore nel campo **Nome**.
5. Digitare un valore nel campo **Nome risolutore**.
6. Digitare un valore nel campo **Descrizione**
7. Nel campo **Componente** immettere o selezionare un valore.
    * Ogni sottocomponente deve fare riferimento a una definizione di componente. La progettazione supporta i componenti riutilizzabili e garantisce che un componente definito possa essere utilizzato in più modelli prodotto.  
8. Selezionare **Salva**.
9. Selezionare **Dettagli riga DBA**.
    * Il modulo dei dettagli della riga DBA consente all'utente di selezionare le proprietà richieste per il sottocomponente. Per ogni proprietà può essere specificato un valore fisso o sottoposto al mapping a un attributo. Il mapping a un attributo determina che la proprietà riga DBA abbia valori diversi a seconda della selezione della configurazione.  
10. Nel campo **Numero articolo** immettere o selezionare un valore.
    * Ogni sottocomponente rappresenta una rappresentazione generale prodotto configurabile con la tecnologia di configurazione basata su vincoli. Il riferimento viene effettuato tramite il numero di articolo.  
11. Selezionare la casella di controllo **Imposta**.
12. Selezionare **Sì** nel campo **Calcolo**.
    * Impostando l'opzione di calcolo si garantisce che il prodotto venga incluso durante l'esecuzione di un calcolo dei costi per il prodotto.  
13. Seleziona la scheda **Impostazioni**.
14. Selezionare la casella di controllo **Imposta**.
15. Nel campo **Quantità** immettere un numero.
    * Il campo della quantità determina la quantità del prodotto che verrà utilizzata nel prodotto configurato.  
16. Selezionare la casella di controllo **Imposta**.
17. Nel campo **Per serie**, immettere un numero.
18. Selezionare **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]