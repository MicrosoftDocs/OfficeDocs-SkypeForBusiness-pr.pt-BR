---
title: Migrar os números de acesso discado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fcc5b7dac5c9769d92afc86e7036f7e410f2278
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="5df85-102">Migrar os números de acesso discado</span><span class="sxs-lookup"><span data-stu-id="5df85-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5df85-103">_**Última modificação do tópico:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="5df85-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="5df85-104">Migrar números de acesso de discagem requer duas etapas: executar o cmdlet **Import-CsLegacyConfiguration** (concluído anteriormente em [importar políticas e configurações](import-policies-and-settings.md)) para migrar planos de discagem e outras configurações de número de acesso de discagem, e executar o cmdlet **move-CsApplicationEndpoint** para migrar os objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="5df85-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="5df85-105">Para migrar os números de acesso de discagem</span><span class="sxs-lookup"><span data-stu-id="5df85-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="5df85-106">Abra a ferramenta administrativa do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="5df85-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="5df85-107">Na árvore do console, clique com o botão direito do mouse no nó de floresta, clique em **Propriedades** e, em seguida, clique em **Propriedades do Atendedor de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="5df85-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="5df85-108">Na guia **Números de Telefone de Acesso**, clique em **Atendido pelo Pool** para classificar os números de telefone de acesso pelo pool associado e identificar todos os números de acesso para o pool a partir do qual você está migrando.</span><span class="sxs-lookup"><span data-stu-id="5df85-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="5df85-109">Para identificar URI do SIP para cada número de acesso de discagem, clique duas vezes no número de acesso para abrir a caixa de seleção **Editar Número do Atendedor de Conferência** e verifique **URI do SIP**.</span><span class="sxs-lookup"><span data-stu-id="5df85-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="5df85-110">Abra o Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5df85-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="5df85-111">Para mover cada número de acesso de discagem para um pool hospedado no Lync Server 2013, execute:</span><span class="sxs-lookup"><span data-stu-id="5df85-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="5df85-112">Na ferramenta administrativa do Office Communications Server 2007 R2, na guia **números de telefone de acesso** , verifique se os números de acesso de discagem permanecem para o pool do Office Communications Server 2007 R2 a partir do qual você está migrando.</span><span class="sxs-lookup"><span data-stu-id="5df85-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

