---
title: Creazione di massa offerte di vendita
description: Questa procedura dimostra la creazione efficientemente delle offerte che offrono un set di prodotti o servizi che devono essere inviati a più clienti.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ea50500ed52069ab9f6aae0dfb2d6cffc47cbff
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006843"
---
# <a name="mass-create-sales-quotations"></a>Creazione di massa offerte di vendita

[!include [banner](../../includes/banner.md)]

Questa procedura dimostra la creazione efficientemente delle offerte che offrono un set di prodotti o servizi che devono essere inviati a più clienti. La creazione di offerta di massa è basata sui modelli di offerta. È possibile eseguire questa procedura sui propri dati o nella società di dati dimostrativi USMF.


## <a name="create-a-quotation-template"></a>Creare un modello di offerta
1. Passare a Vendite e marketing > Impostazione > Offerte > Gruppi di modelli.
2. Fare clic su Nuovo.
3. Nel campo ID gruppo, immettere un ID di propria scelta.
4. Nel campo Descrizione digitare un valore.
5. Fare clic su Salva.
6. Chiudere la pagina.
7. Passare a Vendite e marketing > Offerte di vendita > Tutte le offerte.
8. Fare clic su Nuovo.
9. Nel campo Tipo di conto selezionare "Cliente".
10. Nel campo Conto cliente, immettere o selezionare un valore.
11. Fare clic su OK.
    * Perché un'offerta diventi modello è necessario eseguire i passaggi di configurazione nell'intestazione dell'offerta. Questa operazione deve essere effettuata prima di aggiungere le righe all'offerta.   
12. Nel riquadro azioni fare clic su Opzioni.
13. Fare clic su Cambia visualizzazione.
14. Fare clic su Visualizzazione intestazione.
15. Espandere la sezione Impostazione.
16. Nel campo ID gruppo, immettere o selezionare un valore.
17. Digitare un valore nel campo Nome modello.
18. Selezionare Sì nel campo Attivo.
    * Solo i modelli attivi possono essere utilizzati quando si applica un modello a una nuova offerta di vendita.  
19. Nel riquadro azioni fare clic su Opzioni.
20. Fare clic su Cambia visualizzazione.
21. Fare clic su Visualizzazione riga.
22. Nel campo Articolo immettere o selezionare un valore.
23. Digitare un valore nel campo Articolo.
24. Chiudere la pagina.
25. Nel campo Percentuale sconto immettere un numero.
26. Fare clic su Aggiungi riga.
27. Nel campo Articolo immettere o selezionare un valore.
28. Digitare un valore nel campo Articolo.
29. Chiudere la pagina.
30. Nel campo Prezzo unitario, immettere un nuovo prezzo o modificare quello corrente.
31. Fare clic su Aggiungi riga.
32. Nel campo Articolo immettere o selezionare un valore.
33. Digitare un valore nel campo Articolo.
34. Chiudere la pagina.
35. Nel campo Quantità immettere un numero.
36. Nel campo Sconto, immettere un numero.
37. Fare clic su Salva.

## <a name="apply-the-template-to-create-a-single-quotation"></a>Applicare il modello per creare una singola offerta
1. Passare a Vendite e marketing > Offerte di vendita > Tutte le offerte.
    * Si noti che l'offerta appena creata è contrassegnata come modello.  
2. Fare clic su Nuovo.
3. Nel campo Tipo di conto selezionare "Cliente".
4. Nel campo Conto cliente, immettere o selezionare un valore.
5. Espandere la sezione Modello.
6. Nel campo ID gruppo, immettere o selezionare un valore.
7. Nel campo Nome modello immettere o selezionare un valore.
8. Nel campo Metodo di calcolo, selezionare "In base ai valori del modello".
9. Fare clic su OK.
    * La nuova offerta ora è stata creata in base ai dati e ai termini del modello.  
10. Chiudere la pagina.
11. Chiudere la pagina.

## <a name="apply-the-template-to-mass-create-quotations"></a>Applicare il modello per creare offerte in massa
1. Passare a Vendite e marketing > Offerte di vendita > Aggiornamento offerta > Creazione di massa offerte.
2. Nel campo Tipo di conto selezionare "Cliente".
3. Nel campo ID gruppo, immettere o selezionare un valore.
4. Nel campo Nome modello immettere o selezionare un valore.
5. Nel campo Metodo di calcolo, selezionare "In base ai valori del modello".
6. Espandere la sezione Record da includere.
7. Fare clic su Filtro.
8. Nel campo Criteri, impostare il filtro per coprire un intervallo di clienti che si desidera includere nella creazione di massa offerte. Utilizzare il seguente formato "Customer1..CustomerN.
    * Ad esempio, è possibile impostare il filtro su US-001..US-004  
9. Fare clic su OK.
10. Fare clic su OK.
11. Passare a Vendite e marketing > Offerte di vendita > Tutte le offerte.
    * Verificare che le offerte siano state create per tutti i clienti specificati nella routine di aggiornamento di massa, in base al modello selezionato.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]