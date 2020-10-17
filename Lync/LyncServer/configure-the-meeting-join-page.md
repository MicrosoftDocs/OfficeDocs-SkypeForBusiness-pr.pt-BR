---
title: Configurar a página de ingresso na reunião
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 208f2d24d5617da703b04ea9888dd8b187f31476
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503318"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="1f7e6-102">Configurar a página de ingresso na reunião</span><span class="sxs-lookup"><span data-stu-id="1f7e6-102">Configure the meeting join page</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f7e6-103">_**Última modificação do tópico:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="1f7e6-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="1f7e6-104">Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de ingresso na reunião detecta se um cliente do Lync 2013 já está instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="1f7e6-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="1f7e6-105">Se um cliente já estiver instalado, esse cliente abre e participa da reunião.</span><span class="sxs-lookup"><span data-stu-id="1f7e6-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="1f7e6-106">Se um cliente não estiver instalado, por padrão, a versão 2013 do Lync Web App é aberta.</span><span class="sxs-lookup"><span data-stu-id="1f7e6-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="1f7e6-107">Você pode modificar o comportamento da página de ingresso na reunião se quiser permitir que os usuários ingressem em reuniões com o Office Communicator 2007 R2 ou o Lync 2010 Attendant.</span><span class="sxs-lookup"><span data-stu-id="1f7e6-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="1f7e6-108">Essas opções de configuração foram removidas do painel de controle do Lync Server 2013, mas você as configura usando o cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="1f7e6-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="1f7e6-109">Parâmetros CsWebServiceConfiguration da página de ingresso em reunião</span><span class="sxs-lookup"><span data-stu-id="1f7e6-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f7e6-110">Parâmetro CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="1f7e6-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="1f7e6-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f7e6-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f7e6-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="1f7e6-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="1f7e6-113">Se for definido como true, os usuários que ingressarem em uma reunião usando um aplicativo cliente que não seja o Lync serão considerados a oportunidade de participar da reunião usando o Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1f7e6-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="1f7e6-114">O valor padrão é False.</span><span class="sxs-lookup"><span data-stu-id="1f7e6-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f7e6-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="1f7e6-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="1f7e6-p104">Quando for definido como True, as opções alternativas para ingresso em uma conferência online (como Office Communicator 2007 R2) serão automaticamente expandidas e exibidas aos usuários. Quando for definido como False (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções por conta própria.</span><span class="sxs-lookup"><span data-stu-id="1f7e6-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="1f7e6-118">Para configurar a página de ingresso na reunião usando o Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f7e6-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="1f7e6-119">Inicie o Shell de gerenciamento do Lync Server 2013: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1f7e6-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1f7e6-120">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1f7e6-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="1f7e6-121">Este cmdlet retorna as definições de configurações do serviço da Web.</span><span class="sxs-lookup"><span data-stu-id="1f7e6-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="1f7e6-122">Execute o seguinte comando, com os parâmetros definidos como true ou false, dependendo da sua preferência (para obter detalhes sobre os parâmetros desse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="1f7e6-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

