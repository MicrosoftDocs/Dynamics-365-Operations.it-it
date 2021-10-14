---
title: Impostare criteri per le gerarchie di categorie di approvvigionamento
description: Utilizzare questa procedura per impostare le regole per ordinare prodotti in una categoria.
author: Henrikan
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicy, ProcCategoryAccessPolicyRule, ProcCategoryPolicyRule, EcoResCategorySingleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee056d7c2a8bdc9bcd2f5a0f4b96a7bf69c8c862
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577098"
---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a>Impostare criteri per le gerarchie di categorie di approvvigionamento

[!include [banner](../../includes/banner.md)]

Utilizzare questa procedura per impostare le regole per ordinare prodotti in una categoria. Le regole vengono definite per criteri di acquisto specifici. La regola di accesso alle categorie determina le categorie di approvvigionamento a cui i dipendenti hanno accesso quando creano una richiesta. Quando viene creata una richiesta, i criteri di acquisto e la regola di accesso alle categorie da applicare vengono determinati dalla persona giuridica e dall'unità operativa a cui il dipendente appartiene. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF. In genere questa attività sarà svolta da un responsabile acquisti.


## <a name="find-the-procurement-policy"></a>Trovare i criteri di approvvigionamento
1. Nel pannello di navigazione andare a **Moduli > Approvvigionamento > Impostazioni > Criteri > Criteri di acquisto**.
2. Fare clic sul collegamento dei criteri di approvvigionamento USMF. Questi sono i criteri a cui aggiungerete una regola. Devono essere criteri attivi.  

## <a name="create-a-category-access-rule"></a>Creare una regola di accesso alla categoria
1. Espandere la Scheda dettaglio **Regole dei criteri**.
2. Nell'elenco **Tipo di regola dei criteri**, selezionare **Regola dei criteri di accesso alle categorie**. Se il pulsante **Crea regola dei criteri** è disattivato, è perché c'è già una regola dei criteri attiva per l'accesso alle categorie. Controllare i campi **Validità** e **Scadenza** per determinare quale è, quindi selezionarlo e fare clic su **Ritira regola dei criteri**. Se il pulsante **Crea regola dei criteri** è disponibile, non dovete fare nulla.  
3. Fare clic su **Crea regola dei criteri**.
4. Nel campo **Data di validità** immettere una data e un'ora. Il tempo non deve sovrapporsi con un'altra regola che è già attiva.  
5. Selezionare una categoria a cui la regola si applicherà. Prendere nota di quale categoria questa è – l'informazione sarà necessaria successivamente. Quando si seleziona una categoria, anche le relative categorie padre verranno aggiunte all'elenco Categorie selezionate. Selezionare la casella di controllo **Includi sottocategorie** per applicare la regola a tutte le sottocategorie della categoria selezionata.
6. Fare clic sulla freccia destra per aggiungere all'elenco **Categorie selezionate**.  
4. Fare clic su **OK**. Se si imposta l'opzione **Includi regola padre** su Sì, la regola dei criteri definita per una categoria padre verrà assegnata anche alle categorie figlio se non è stata definita una regola dei criteri per le categorie figlio.

## <a name="create-a-category-policy-rule"></a>Crea una regola dei criteri categorie
1. Nell'elenco **Tipo di regola dei criteri**, selezionare **Regola dei criteri categorie**. Se il pulsante **Crea regola dei criteri** è disattivato, selezionare la regola dei criteri attiva e poi fare clic su **Ritira regola dei criteri**.  
2. Fare clic su **Crea regola dei criteri**.
3. Nel campo **Data di validità** immettere una data e un'ora.
4. Scegliere **Aggiungi**.
5. Nel campo **Categoria** selezionare la stessa categoria usata per la **regola di accesso alle categorie**.
6. Selezionare un'opzione nel campo **Selezione fornitore**. Selezionare una regola per controllare il tipo di fornitori che può essere selezionato per la categoria quando le richieste vengono create.  
7. Fare clic su **Chiudi**. Le regole dei criteri definite sono state per le richieste di tipo Consumo. Se voleste definire criteri per le richieste di tipo Rifornimento, dovreste creare una regola per Tipo di regola dei criteri chiamata "Regola dei criteri di accesso alle categorie di rifornimento".  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]