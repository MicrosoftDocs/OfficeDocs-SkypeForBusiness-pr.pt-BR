---
title: 'Lync Server 2013: (opcional) verificar configurações de conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bff47410f46516061a5a3be64bce17476b453e7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a><span data-ttu-id="07423-102">Opcion Verificar as configurações de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07423-102">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07423-103">_**Última modificação do tópico:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="07423-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="07423-p101">Como verificação final da configuração da conferência discada, você pode pesquisar planos de discagem com uma região de conferência discada que não seja usada por nenhum número de acesso e números de acesso que não possuem uma região de conferência discada especificada. Essa etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="07423-p101">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region. This step is optional.</span></span>

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="07423-106">Para encontrar planos de discagem com uma região de conferência discada que não seja usada por um número de acesso</span><span class="sxs-lookup"><span data-stu-id="07423-106">To find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1.  <span data-ttu-id="07423-107">Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-ServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="07423-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="07423-108">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="07423-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="07423-109">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="07423-109">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    <span data-ttu-id="07423-110">Este cmdlet retorna todos os planos de discagem que possuem uma região de conferência discada que não é usada por um número de acesso.</span><span class="sxs-lookup"><span data-stu-id="07423-110">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a><span data-ttu-id="07423-111">Para encontrar números de acesso sem regiões atribuídas</span><span class="sxs-lookup"><span data-stu-id="07423-111">To find access numbers without assigned regions</span></span>

1.  <span data-ttu-id="07423-112">Conecte-se ao computador como membro do grupo RTCUniversalServerAdmins ou da função **Cs-ServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="07423-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="07423-113">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="07423-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="07423-114">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="07423-114">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    <span data-ttu-id="07423-115">Este cmdlet retorna todos números de acesso de conferência discada que não estão associados a uma região.</span><span class="sxs-lookup"><span data-stu-id="07423-115">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

