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
ms.openlocfilehash: 104f5a06395de236c280d083e6211decaaa62b35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="8878f-102">Configurar a página de ingresso na reunião</span><span class="sxs-lookup"><span data-stu-id="8878f-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8878f-103">_**Tópico da última modificação:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="8878f-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="8878f-104">Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página ingressar na reunião detecta se um cliente do Lync 2013 já está instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="8878f-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="8878f-105">Se um cliente já estiver instalado, esse cliente abrirá e ingressará na reunião.</span><span class="sxs-lookup"><span data-stu-id="8878f-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="8878f-106">Se um cliente não estiver instalado, por padrão, a versão 2013 do Microsoft Lync Web App será aberta.</span><span class="sxs-lookup"><span data-stu-id="8878f-106">If a client is not installed, by default the 2013 version of Microsoft Lync Web App opens.</span></span>

<span data-ttu-id="8878f-107">Você pode modificar o comportamento da página de associação de reunião se desejar permitir que os usuários ingressem em reuniões com o Office Communicator 2007 R2 ou o Lync 2010 Attendant.</span><span class="sxs-lookup"><span data-stu-id="8878f-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="8878f-108">Essas opções de configuração foram removidas do painel de controle do Lync Server 2013, mas você as configura usando o cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="8878f-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="8878f-109">Parâmetros de CsWebServiceConfiguration da página de ingresso na reunião</span><span class="sxs-lookup"><span data-stu-id="8878f-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8878f-110">Parâmetro CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="8878f-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="8878f-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="8878f-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8878f-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="8878f-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="8878f-113">Se definido como true, os usuários que ingressam em uma reunião usando um aplicativo cliente que não seja o Lync terão a oportunidade de ingressar na reunião usando o Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8878f-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="8878f-114">O valor padrão é False.</span><span class="sxs-lookup"><span data-stu-id="8878f-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8878f-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="8878f-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="8878f-116">Quando definida como true, as opções alternativas para ingressar em uma conferência online (como o Office Communicator 2007 R2) serão expandidas automaticamente e exibidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="8878f-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span></span> <span data-ttu-id="8878f-117">Quando definido como falso (o valor padrão), essas opções estarão disponíveis, mas o usuário precisará exibir a lista de opções para si mesmo.</span><span class="sxs-lookup"><span data-stu-id="8878f-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="8878f-118">Para configurar a página ingressar na reunião usando o Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8878f-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="8878f-119">Inicie o Shell de gerenciamento do Lync Server 2013: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8878f-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8878f-120">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8878f-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="8878f-121">Esse cmdlet retorna as configurações de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="8878f-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="8878f-122">Execute o seguinte comando, com os parâmetros definidos como verdadeiro ou falso, dependendo da sua preferência (para obter detalhes sobre os parâmetros para esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="8878f-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

