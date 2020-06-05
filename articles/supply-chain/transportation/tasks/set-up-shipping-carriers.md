---
title: Impostare vettori di spedizione
description: In questo argomento viene descritto come impostare un vettore di spedizione e come definire dettagli quali servizio, modalità di spedizione, metodo di pagamento del trasporto, vincoli di trasporto e tariffa di trasporto.
author: ShylaThompson
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d157470527a986ea1c9fe0a9a02e2ba6ee8819e
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383000"
---
# <a name="set-up-shipping-carriers"></a>Impostare vettori di spedizione

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come impostare un vettore di spedizione e come definire dettagli quali servizio, modalità di spedizione, metodo di pagamento del trasporto, vincoli di trasporto e tariffa di trasporto. Un coordinatore dei trasporti può quindi assegnare un vettore di spedizione a un carico in entrata o in uscita.


## <a name="create-a-new-shipping-carrier"></a>Creare un nuovo vettore di spedizione
1. Andare a **Pannello di navigazione > Moduli > Gestione trasporto > Impostazioni > Vettori > Vettori spedizione**.
2. Nel Riquadro azioni seleziona **Nuovo**.
3. Nel campo **Vettore spedizione** digitare un valore.
4. Digitare un valore nel campo **Nome**.
5. Nel campo **Modo**, selezionare un'opzione dal menu a discesa.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>Inserire le informazioni generali per il vettore di spedizione
1. Attivare/disattivare l'espansione della sezione **Panoramica**.
2. Selezionare o deselezionare la casella di controllo **Attiva vettore di spedizione**.
3. Nel campo **Conto fornitore**, selezionare un'opzione dal menu a discesa. Selezionare il conto fornitore a cui assegnare il vettore di spedizione.  
4. Nel campo **Tipo di pagamento trasporto** selezionare un'opzione. Selezionare **Manuale** per utilizzare la pagina Metodo di pagamento trasporto o selezionare **EDI** per aggiornare il metodo di pagamento utilizzando il formato EDI (Electronic Data Interchange).  
5. Selezionare o deselezionare la casella di controllo **Attiva valutazione vettore**.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>Creare i servizi necessari per il vettore di spedizione
1. Attivare/disattivare l'espansione della sezione **Servizi**.
2. Selezionare **Nuovo**.
3. Nel campo **Servizio trasporto** digitare un valore.
4. Digitare un valore nel campo **Nome**.
5. Nel campo **Metodo di trasporto**, selezionare un'opzione dal menu a discesa.

## <a name="set-up-the-address-for-the-carrier-optional"></a>Impostare l'indirizzo del vettore (facoltativo)
1. Attiva/disattiva l'espansione della sezione **Indirizzi**.
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Nome o descrizione**.
4. Nel campo **Paese**, selezionare un'opzione dal menu a discesa.
5. Nel campo **Codice postale (CAP)**, selezionare un'opzione dal menu a discesa.
6. Digitare un valore nel campo **Via**.
7. Selezionare **OK**.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>Impostare il profilo di valutazione per il vettore di spedizione
1. Attivare/disattivare l'espansione della sezione **Profili valutazione**.
2. Selezionare **Nuovo**.
3. Nel campo **Profilo valutazione** digitare un valore.
4. Digitare un valore nel campo **Nome**.
5. Nel campo **Sito**, selezionare un'opzione dal menu a discesa.
6. Nel campo **Magazzino**, selezionare un'opzione dal menu a discesa.
7. Nel campo **Motore tariffe**, selezionare un'opzione dal menu a discesa. Selezionare il motore tariffe in base al contratto stipulato con il vettore.  
8. Nel campo **Tariffa principale**, selezionare un'opzione dal menu a discesa.
9. Nel campo **Motore tempo di transito**, selezionare un'opzione dal menu a discesa.
10. Selezionare **Salva**.

