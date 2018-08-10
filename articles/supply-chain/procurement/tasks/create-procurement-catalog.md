--- 
title: Creare un catalogo di approvvigionamento
description: Questa guida indica come creare un catalogo di approvvigionamento.
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: df844ba3834972441daa61899294b3e95cac96c1
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-procurement-catalog"></a>Creare un catalogo di approvvigionamento

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa guida indica come creare un catalogo di approvvigionamento. Questa attività in genere viene svolta da un responsabile degli approvvigionamenti. Inoltre imparerete come i dipendenti possono usare il catalogo quando creano una richiesta. Prima che possiate creare un catalogo, ci deve essere una gerarchia di categorie di approvvigionamento nel vostro sistema. La gerarchia è ereditata dal nuovo catalogo, con tutti i prodotti che sono nella gerarchia. Potete utilizzare questa guida nella società di dati dimostrativi USMF in cui la gerarchia di categorie di approvvigionamento è disponibile, come pure gli esempi utilizzati nei passaggi della procedura.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Assicurarsi che una gerarchia di categorie di approvvigionamento esista
1. Passare a Approvvigionamento > Categorie di approvvigionamento.
    * Una gerarchia di categorie di approvvigionamento è disponibile nella società di dati dimostrativi USMF e prodotti sono stati aggiunti alla categoria Office machines/Computers. Se si esegue la procedura come guida attività, sarà necessario sbloccare la guida per esplorare la categoria. Se una gerarchia non fosse disponibile, bisognerebbe crearla facendo clic su Nuovo. Ciò può essere fatto una sola volta.  
2. Chiudere la pagina.

## <a name="create-a-catalog"></a>Creazione di un catalogo
1. Andare a Approvvigionamento > Cataloghi > Cataloghi di approvvigionamento.
2. Fare clic su Nuovo catalogo di approvvigionamento per aprire la finestra di dialogo a discesa.
3. Digitare un valore nel campo Nome.
4. Fare clic su OK.
5. Nella struttura, espandere 'CORP PROCUREMENT CATEGORIES'.
6. Nella struttura espandere 'OFFICE MACHINES'.
7. Nella struttura selezionare 'Computer'.
    * I prodotti dalla categoria di approvvigionamento sono visualizzati nella lista. Se volete aggiungere un prodotto alla categoria dovete fare questo alla pagina Gerarchia di categorie di approvvigionamento o alla pagina Dettagli articolo.  
    * Il tipo di aggiornamento predefinito determina se i nuovi prodotti aggiunti alla gerarchia di categorie di approvvigionamento sono immediatamente visibili nel catalogo. Se il tipo di aggiornamento è impostato su Dinamico, i cambiamenti sono immediatamente visibili. Se il tipo di aggiornamento è Statico, i nuovi prodotti sono visibili alle persone che usano il catalogo solo dopo che il catalogo è stato ripubblicato. L'azione Pubblica è disponibile nel riquadro azioni alla cima della pagina. Se i prodotti vengono rimossi dalla gerarchia di categorie di approvvigionamento, il cambiamento è immediatamente visibile, indipendentemente dal valore nel campo Tipo di aggiornamento predefinito.  
8. Nell'elenco trovare e selezionare il record desiderato.
9. Fare clic su Nascondi.
10. Nel riquadro azioni fare clic su Navigazione categoria.
11. Fare clic su Disabilita.
12. Nel riquadro azioni fare clic su Navigazione categoria.
13. Fare clic su Attiva.
14. Fare clic su Attiva catalogo.
15. Chiudere la pagina.

## <a name="make-the-catalog-visible"></a>Rendere visibile il catalogo
1. Andare a Approvvigionamento > Impostazioni > Criteri > Criteri di acquisto.
2. Selezionare i criteri di approvvigionamento USMF.
    * Dovete selezionare i criteri di acquisto per la persona giuridica in cui al lavoratore collegato al vostro profilo utente è permesso ordinare i prodotti. Nei dati dimostrativi USMF, l'utente Admin è collegato al lavoratore chiamato Julia Funderburk, che ordina i prodotti in USMF per impostazione predefinita.  
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Selezionare il catalogo appena creato.
5. Fare clic su OK.
6. Chiudere la pagina.
7. Chiudere la pagina.

## <a name="use-the-catalog"></a>Usare il catalogo
1. Andare a Approvvigionamento > Richieste di acquisto > Tutte le richieste di acquisto.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
4. Fare clic su OK.
5. Fare clic su Aggiungi prodotti.
6. Nell'elenco trovare e selezionare il record desiderato.
    * Potete utilizzare la gerarchia di categorie a sinistra o il filtro alla cima della lista per filtrare i prodotti.  
7. Fare clic su Aggiungi a righe.
8. Nell'elenco trovare e selezionare il record desiderato.
9. Fare clic su Aggiungi a righe.
10. Fare clic su OK.


