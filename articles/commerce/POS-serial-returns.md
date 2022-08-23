---
title: Restituire prodotti controllati dal numero di serie in POS
description: Questo articolo descrive le funzionalità per la convalida degli articoli con numero di serie come parte del processo di reso nell'applicazione POS di Microsoft Dynamics 365 Commerce.
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9fa7e47b6d650370afe4b98d7eca01253bd1bc36
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268476"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a>Restituire prodotti controllati dal numero di serie in POS

[!include [banner](includes/banner.md)]

Questo articolo descrive le funzionalità per la convalida degli articoli con numero di serie come parte del processo di reso nell'applicazione POS di Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Nella versione di Commerce 10.0.20 e successive, è disponibile una nuova funzionalità denominata **Esperienza di elaborazione dei resi unificata in POS**. Per utilizzare la convalida del numero di serie durante l'elaborazione degli ordini di reso in POS, è necessario attivare questa funzione. Per informazioni su altre funzionalità fornite da questa funzione quando è attivata, vedere [Creare resi in POS)](POS-returns.md).
>
> Una volta attivata, la funzione non può essere disattivata.

## <a name="options-for-validating-serialized-returns"></a>Opzioni per la convalida dei resi con numero di serie

Quando la funzione **Esperienza di elaborazione dei resi unificata in POS** è attivata, le organizzazioni possono eseguire una convalida sui resi di articoli controllati dal numero di serie tramite POS. Questa funzionalità può avvisare gli utenti se il numero di serie restituito è diverso dal numero di serie originale che è stato venduto. Nella versione di Commerce 10.0.20 e successive, il messaggio che gli utenti ricevono è solo un messaggio di avviso. Gli utenti possono continuare a elaborare un reso in base a un numero di serie diverso dal numero di serie originariamente venduto.

Per configurare la convalida del numero di serie per un'organizzazione dopo l'attivazione della funzione **Esperienza di elaborazione dei resi unificata in POS**, accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri di Commerce** in Commerce Headquarters. Nella scheda **Inventario**, scheda di dettaglio **Operazioni scorte di magazzino**, impostare l'opzione **Abilita convalida dei numeri di serie sui resi POS** su **Sì**.

## <a name="process-returns-for-serialized-items-in-pos"></a>Elaborare resi per articoli con numero di serie in POS

Se l'opzione **Abilita convalida dei numeri di serie sui resi POS** è stata impostata su **Sì**, quando un articolo controllato dal numero di serie viene reso tramite il POS, l'utente può immettere il numero di serie per la riga del reso nel riquadro dei dettagli nella pagina **Prodotti restituibili**. Se il numero di serie immesso non corrisponde al numero di serie originale venduto per la transazione di vendita, l'utente riceve un messaggio di avviso. Tuttavia, l'applicazione non impedisce all'utente di continuare a pubblicare il reso.

> [!NOTE]
> Attualmente, il POS supporta la convalida dei numeri di serie solo sulle righe di reso in cui la quantità ordinata originale non è superiore a uno. Se la riga dell'ordine cliente originale è stata creata in un canale non POS e la quantità ordinata per l'articolo con numero di serie in una determinata riga di vendita è maggiore di uno, l'articolo non può essere restituito correttamente tramite il POS.

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare resi in POS](POS-returns.md)
