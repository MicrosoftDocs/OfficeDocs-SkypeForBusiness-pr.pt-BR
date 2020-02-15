---
title: Configurar a página de ingresso na reunião
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b0829037377c15f8690c36f29f8775f9e5a56c6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="498bb-102">Configurar a página de ingresso na reunião</span><span class="sxs-lookup"><span data-stu-id="498bb-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="498bb-103">_**Última modificação do tópico:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="498bb-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="498bb-104">Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de ingresso na reunião detecta se um cliente do Lync 2013 já está instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="498bb-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="498bb-105">Se um cliente já estiver instalado, esse cliente abre e participa da reunião.</span><span class="sxs-lookup"><span data-stu-id="498bb-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="498bb-106">Se um cliente não estiver instalado, por padrão, a versão 2013 do Microsoft Lync Web App será aberta.</span><span class="sxs-lookup"><span data-stu-id="498bb-106">If a client is not installed, by default the 2013 version of Microsoft Lync Web App opens.</span></span>

<span data-ttu-id="498bb-107">Você pode modificar o comportamento da página de ingresso na reunião se quiser permitir que os usuários ingressem em reuniões com o Office Communicator 2007 R2 ou o Lync 2010 Attendant.</span><span class="sxs-lookup"><span data-stu-id="498bb-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="498bb-108">Essas opções de configuração foram removidas do painel de controle do Lync Server 2013, mas você as configura usando o cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="498bb-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="498bb-109">Parâmetros CsWebServiceConfiguration da página de ingresso em reunião</span><span class="sxs-lookup"><span data-stu-id="498bb-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="498bb-110">Parâmetro CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="498bb-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="498bb-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="498bb-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="498bb-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="498bb-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="498bb-113">Se for definido como true, os usuários que ingressarem em uma reunião usando um aplicativo cliente que não seja o Lync serão considerados a oportunidade de participar da reunião usando o Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="498bb-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="498bb-114">O valor padrão é False.</span><span class="sxs-lookup"><span data-stu-id="498bb-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="498bb-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="498bb-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="498bb-p104">Quando for definido como True, as opções alternativas para ingresso em uma conferência online (como Office Communicator 2007 R2) serão automaticamente expandidas e exibidas aos usuários. Quando for definido como False (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções por conta própria.</span><span class="sxs-lookup"><span data-stu-id="498bb-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="498bb-118">Para configurar a página de ingresso na reunião usando o Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="498bb-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="498bb-119">Inicie o Shell de gerenciamento do Lync Server 2013: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="498bb-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="498bb-120">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="498bb-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="498bb-121">Este cmdlet retorna as definições de configurações do serviço da Web.</span><span class="sxs-lookup"><span data-stu-id="498bb-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="498bb-122">Execute o seguinte comando, com os parâmetros definidos como true ou false, dependendo da sua preferência (para obter detalhes sobre os parâmetros desse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="498bb-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

