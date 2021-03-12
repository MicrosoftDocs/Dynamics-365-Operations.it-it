---
title: Creare una fattura a testo libero
description: In questo argomento viene illustrato come creare le fatture a testo libero.
author: mikefalkner
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 726d4979059417871a00626c55da32fa4286cb53
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991119"
---
# <a name="create-a-free-text-invoice"></a>Creare una fattura a testo libero

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come creare le fatture a testo libero. Per questa procedura viene utilizzata la società dimostrativa **USMF**.

## <a name="create-a-free-text-invoice"></a>Crea una fattura a testo libero

1. Passare a **Contabilità clienti (o contabilità relativa alle vendite) \> Fatture \> Tutte le fatture a testo libero**.
2. Selezionare **Nuovo**.
3. Nel campo **Conto cliente** selezionare un valore.

    * Per impostazione predefinita, il conto che viene selezionato come conto cliente viene utilizzare come conto fatture.
    * Se la fattura non viene registrata, lo stato di contabilità inizia con **In corso**.
    * Il numero fattura viene assegnato al momento della registrazione della fattura.
    * Se si utilizzano i mandati SEPA (Single Euro Payments Area), il mandato per addebito diretto verrà automaticamente immesso quando si seleziona il conto cliente.

4. Nel campo **Descrizione** immettere un valore.
5. Nel campo **Conto principale** specificare il numero di conto che non ha dimensioni. Le dimensioni verranno immesse più avanti in questo argomento.

    È anche possibile immettere uno o più caratteri per il conto principale e utilizzare la ricerca per trovare il conto.

6. Selezionare la Scheda dettaglio **Dettagli riga** per aggiungere dimensioni al conto principale.
7. Selezionare la scheda **Riga dimensioni finanziarie**.

    * Le dimensioni sono relative solo alla riga selezionata.
    * La fascia IVA viene compilata dal cliente. Se il cliente non dispone di una fascia IVA, viene utilizzata quella del conto principale.
    * La fascia IVA articoli viene compilata dal conto principale. Se il conto principale non dispone di una fascia IVA articoli, viene utilizzata quella specificata nei parametri IVA della contabilità generale.

8. Facoltativo: nel campo **Quantità** immettere un numero.
9. Facoltativo: nel campo **Prezzo unitario** immettere un numero.

    L'importo è calcolato come quantità per prezzo unitario. Tuttavia è possibile ignorare questo calcolo immettendo un importo.

10. Selezionare **IVA** per visualizzare l'IVA che viene calcolata per la fattura.

    È possibile visualizzare gli importi IVA in questa pagina o è possibile ignorare gli importi nella scheda **Rettifica**.

11. Selezionare **OK**.
12. Selezionare **Spese** per aggiungere una spesa alla fattura.
13. Nel campo **Codice spese** immettere un valore.
14. Nel campo **Valore spese** immettere un numero.
15. Chiudere la pagina.
16. Selezionare **Totali** per visualizzare un riepilogo dei dettagli e dei totali della fattura.
17. Selezionare **Chiudi**.
18. Selezionare **Registra** per registrare la fattura. Sarà ancora possibile annullare la fattura prima di registrarla.

    * È possibile modificare il tempo di stampa delle fatture. Selezionare **Corrente** per stampare ogni fattura man mano che viene aggiornata. Selezionare **Dopo** per eseguire la stampa dopo che tutte le fatture sono state aggiornate.
    * Per modificare il modo in cui il limite di credito del cliente viene verificato prima che la fattura venga registrata, modificare il valore nel campo **Tipo di limite di credito**.
    * Per stampare la fattura, impostare l'opzione su **Sì**.
    * Per registrare la fattura, impostare l'opzione su **Sì**. È possibile stampare la fattura senza registrarla.

19. Selezionare **OK**.

## <a name="copy-lines"></a>Copia righe
Per copiare le righe in una fattura a testo libero, selezionare una o più righe e quindi selezionare **Copia righe selezionate**. È possibile specificare il numero di copie da eseguire, nonché copiare le note e gli allegati. È possibile copiare le distribuzioni o permettere che vengano ricreate quando si effettua la registrazione.

Dopo aver copiato le righe, è possibile modificare le informazioni secondo le esigenze.

## <a name="create-a-free-text-invoice-from-a-template"></a>Creare una fattura a testo libero da un modello
L'utente può creare una fattura a testo libero da un modello. Quando si seleziona **Nuovo da modello** nella scheda **Fattura**, è possibile selezionare un nome di modello e il conto cliente per la nuova fattura a testo libero. Il cliente può compilare automaticamente i valori predefiniti, ad esempio i termini di pagamento e il metodo di pagamento, oppure è possibile utilizzare i valori che erano stati salvati nel modello.

Viene creata una nuova fattura a testo libero ed è possibile modificare i valori secondo le esigenze.
