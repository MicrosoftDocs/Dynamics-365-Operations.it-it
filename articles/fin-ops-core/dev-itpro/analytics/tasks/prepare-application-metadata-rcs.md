---
title: Preparare i metadati dell'applicazione da utilizzare in RCS
description: In questo articolo viene descritto come creare una nuova configurazione di creazione report che contiene i metadati dell'applicazione.
author: kfend
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ''
ms.openlocfilehash: a9ccbb120be43eaf7a8ae8b5bf8eaafb4850b199
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289976"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a>Preparare i metadati dell'applicazione da utilizzare in RCS
[!include [banner](../../includes/banner.md)]

I passaggi seguenti illustrano come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) che contiene i metadati dell'applicazione per la progettazione di configurazioni del mapping di modello ER in Regulatory Configuration Service (RCS). Questa configurazione verrà utilizzata per la progettazione di una configurazione del mapping di modello ER di esempio per accedere alle transazioni del commercio estero. In questo esempio si creerà una configurazione per la società di esempio Litware, Inc. Questi passaggi possono essere eseguiti in qualsiasi società. Per completare questi passaggi, è necessario dapprima completare i passaggi nell'articolo [Creare provider di configurazione e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md).

## <a name="prerequisites"></a>Prerequisiti
1.    Andare a **Amministrazione organizzazione** > **Aree di lavoro** > **Creazione di report elettronici**. 
2.    Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**. Se questo provider di configurazione non è visualizzato, completare i passaggi nella procedura [Creare provider di configurazioni e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md). 
3.    Fare clic su **Configurazioni dei metadati**. 
4.    Supponiamo che RCS venga utilizzato per progettare una soluzione ER per un'applicazione Finance and Operations che genererà documenti elettronici contenenti informazioni del dominio aziendale per il commercio estero. Per specificare il mapping tra il modello di dati ER e le origini dei dati necessari, in RCS è necessario accedere ai metadati dell'applicazione di Finance and Operations. Di conseguenza, nell'ambito della progettazione della soluzione ER configuriamo una nuova configurazione dei metadati ER contenente tutti i metadati attualmente necessari per generare report ER per il dominio aziendale selezionato. 

## <a name="add-metadata-configuration"></a>Aggiungere una configurazione dei metadati 
1.    Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa. 
2.    Nel campo **Nome**, digitare "Metadati del commercio estero". 
3.    Fare clic su **Crea configurazione**. 
4.    Fare clic su **Progettazione**. 
5.    Scegliere **Aggiungi**. 
  
> [!NOTE]
> È possibile selezionare tutti i metadati per l'intera applicazione o i modelli o i moduli selezionati. Tenere presente che in questo caso i seguenti metadati verranno aggiunti automaticamente: tabelle di record, enumerazioni e tipi di dati estesi. Quando sono necessari tipi aggiuntivi di metadati, devono essere aggiunti manualmente. 
 
Se si selezionano elementi di metadati manualmente, si hanno alcuni metadati relativi alle transazioni del commercio estero. 
  
6.    Fare clic su **Aggiungi origine dati**. 
7.    Fare clic su **Record di tabella**. 
8.    Utilizzare il filtro rapido per filtrare il campo **Nome** in base al valore "Intrastat". 
9.    Selezionare il record di tabella **Intrastat**. 
10.    Fare clic su **OK**.
  
Abbiamo aggiunto informazioni sui metadati relative alla tabella di record Intrastat. 
  
11.    Nella struttura espandere **Record di tabella Intrastat**\>**Relazioni**. 
12.    Nella struttura, selezionare **Record di tabella Intrastat**\>**Relazioni\IntrastatCommodity (Record di tabella EcoResCategory)**.     
13.    Fare clic su **Aggiungi metadati**. 
  
> [!NOTE]
> I metadati relativi alle relazioni necessarie per la tabella di record selezionata devono essere aggiunti manualmente. 
  
16.    Fare clic su **Aggiungi origine dati**. 
17.    Fare clic su **Enumerazione**. 
18.    Utilizzare il filtro rapido per filtrare il campo **Nome** in base al valore "IntrastatDirection". 
19.    Selezionare il record **Enumerazione IntrastatDirection**. 
20.    Fare clic su **OK**. 
21.    Fare clic su **Salva**.  
22.    Chiudere la pagina. 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a>Completare la versione bozza della configurazione dei metadati
1.    Fare clic su **Cambia stato**. 
2.    Fare clic su **Completa**. 
3.    Fare clic su **OK**. 
4.    Selezionare la versione completata **1**. 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a>Esportare la versione completata della configurazione dei metadati dall'applicazione come file XML
1.    Fare clic su **Scambia**. 
2.    Fare clic su **Esporta come file XML**. 
3.    Fare clic su **OK**. 
    
La configurazione dei metadati ER creata è stata salvata come file XML che può essere importato in RCS e utilizzato come origine delle informazioni sui metadati per il dominio aziendale del commercio estero. In base a queste informazioni, possiamo specificare il mapping tra i metadati dell'applicazione e il modello di dati ER.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
