---
title: 'Lync Server 2013: Configurando a página de ingresso na reunião'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 872e95c1d5254830a80b8a0d0dd84b233f2d1813
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="86bc0-102">Configurando a página de ingresso na reunião no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86bc0-102">Configuring the meeting join page in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86bc0-103">_**Última modificação do tópico:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="86bc0-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="86bc0-104">Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de ingresso na reunião detecta se um cliente do Lync 2013 já está instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="86bc0-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="86bc0-105">Se um cliente já estiver instalado, ele abre e participa da reunião.</span><span class="sxs-lookup"><span data-stu-id="86bc0-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="86bc0-106">Se um cliente não estiver instalado, por padrão, a versão 2013 do Lync Web App é aberta.</span><span class="sxs-lookup"><span data-stu-id="86bc0-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="86bc0-107">Você pode modificar o comportamento da página de ingresso na reunião se quiser permitir que os usuários ingressem em reuniões com o Office Communicator 2007 R2 ou o Lync 2010 Attendant.</span><span class="sxs-lookup"><span data-stu-id="86bc0-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="86bc0-108">Essas opções de configuração foram removidas do painel de controle do Lync Server 2013, mas você as configura usando o cmdlet Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="86bc0-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="86bc0-109">Parâmetros do Set-CsWebServiceConfiguration da página de participação de reunião</span><span class="sxs-lookup"><span data-stu-id="86bc0-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86bc0-110">Parâmetro Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="86bc0-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="86bc0-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="86bc0-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86bc0-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="86bc0-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="86bc0-113">Se for definido como true, os usuários que ingressarem em uma reunião usando um aplicativo cliente que não seja o Lync serão considerados a oportunidade de participar da reunião usando o Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="86bc0-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="86bc0-114">O valor padrão é False.</span><span class="sxs-lookup"><span data-stu-id="86bc0-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86bc0-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="86bc0-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="86bc0-p104">Quando for definido como True, as opções alternativas para ingresso em uma conferência online (como Office Communicator 2007 R2) serão automaticamente expandidas e exibidas aos usuários. Quando for definido como False (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções por conta própria.</span><span class="sxs-lookup"><span data-stu-id="86bc0-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="86bc0-118">Para configurar a página de ingresso na reunião usando o Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86bc0-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="86bc0-119">Inicie o Shell de gerenciamento do Lync Server 2013: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="86bc0-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="86bc0-120">Para visualizar as definições de configuração do serviço da web, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="86bc0-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="86bc0-121">Execute o comando a seguir, com os parâmetros definidos como true ou false, dependendo da sua preferência (para obter detalhes sobre os parâmetros desse cmdlet, consulte [set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) na documentação do Shell de gerenciamento do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="86bc0-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="86bc0-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="86bc0-122">See Also</span></span>


[<span data-ttu-id="86bc0-123">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="86bc0-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

