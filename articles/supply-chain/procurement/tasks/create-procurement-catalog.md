---
title: Creare un catalogo di approvvigionamento
description: In questo argomento viene illustrato come creare un catalogo di approvvigionamento.
author: kamaybac
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 59117df519b7aa525713d3acd70195cc42614b9a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812400"
---
# <a name="create-a-procurement-catalog"></a>Creare un catalogo di approvvigionamento

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come creare un catalogo di approvvigionamento. Questa attività in genere viene svolta da un responsabile degli approvvigionamenti. Inoltre imparerete come i dipendenti possono usare il catalogo quando creano una richiesta. Prima che possiate creare un catalogo, ci deve essere una gerarchia di categorie di approvvigionamento nel vostro sistema. La gerarchia è ereditata dal nuovo catalogo, con tutti i prodotti che sono nella gerarchia. Potete utilizzare questa guida nella società di dati dimostrativi USMF in cui la gerarchia di categorie di approvvigionamento è disponibile, come pure gli esempi utilizzati nei passaggi della procedura.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Assicurarsi che una gerarchia di categorie di approvvigionamento esista
1. Andare a **pannello di navigazione >Moduli > Approvvigionamento > Categorie di approvvigionamento**. Una gerarchia di categorie di approvvigionamento è disponibile nella società di dati dimostrativi USMF e prodotti sono stati aggiunti alla categoria **Office machines/Computers**. Se si esegue la procedura come guida attività, sarà necessario sbloccare la guida per esplorare la categoria. Se una gerarchia non fosse disponibile, bisognerebbe crearla facendo clic su **Nuovo**. Ciò può essere fatto una sola volta.  
2. Chiudere la pagina.

## <a name="create-a-catalog"></a>Creazione di un catalogo
1. Andare a **pannello di navigazione >Moduli > Approvvigionamento > Cataloghi > Cataloghi di approvvigionamento**.
2. Fare clic su **Nuovo catalogo di approvvigionamento** per aprire la finestra di dialogo a discesa.
3. Digitare un valore nel campo **Nome**.
4. Selezionare **OK**.
5. Nella struttura, espandere **CORP PROCUREMENT CATEGORIES**.
6. Nella struttura espandere **OFFICE MACHINES**.
7. Nella struttura selezionare **Computer**.

  - I prodotti dalla categoria di approvvigionamento sono visualizzati nella lista. Se volete aggiungere un prodotto alla categoria dovete fare questo alla pagina **Gerarchia di categorie di approvvigionamento** o alla pagina **Dettagli articolo**.  
  - Il tipo di aggiornamento **predefinito** determina se i nuovi prodotti aggiunti alla gerarchia di categorie di approvvigionamento sono immediatamente visibili nel catalogo. Se il tipo di aggiornamento è impostato su **Dinamico**, i cambiamenti sono immediatamente visibili. Se il tipo di aggiornamento è **Statico**, i nuovi prodotti sono visibili alle persone che usano il catalogo solo dopo che il catalogo è stato ripubblicato. L'azione **Pubblica** è disponibile nel riquadro azioni alla cima della pagina. Se i prodotti vengono rimossi dalla gerarchia di categorie di approvvigionamento, il cambiamento è immediatamente visibile, indipendentemente dal valore nel campo Tipo di aggiornamento **predefinito**.  

8. Nel riquadro azioni, selezionare **Navigazione categoria** e verificare che **Abilita** sia selezionato.
9. Selezionare **Attiva catalogo**.
10. Chiudere la pagina.

## <a name="make-the-catalog-visible"></a>Rendere visibile il catalogo
1. Andare a **pannello di navigazione > Moduli > Approvvigionamento > Impostazioni > Criteri > Criteri di acquisto**.
2. Selezionare i **criteri di approvvigionamento USMF**. Dovete selezionare i criteri di acquisto per la persona giuridica in cui al lavoratore collegato al vostro profilo utente è permesso ordinare i prodotti. Nei dati dimostrativi USMF, l'utente Admin è collegato al lavoratore chiamato **Julia Funderburk**, che ordina i prodotti in USMF per impostazione predefinita.  
3. Selezionare il catalogo appena creato.
4. Selezionare **OK**.

## <a name="use-the-catalog"></a>Usare il catalogo
1. Passare ad **pannello di navigazione > Moduli > Approvvigionamento > Richieste di acquisto > Tutte le richieste di acquisto**.
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Nome**.
4. Selezionare **OK**.
5. Selezionare **Aggiungi prodotti**.
6. Nell'elenco trovare e selezionare il record desiderato. Potete utilizzare la gerarchia di categorie a sinistra o il filtro alla cima della lista per filtrare i prodotti.  
7. Selezionare **Aggiungi a righe**.
8. Selezionare **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]