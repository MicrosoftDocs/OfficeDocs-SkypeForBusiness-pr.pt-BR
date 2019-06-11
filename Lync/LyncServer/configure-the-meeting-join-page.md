---
title: Configurar a página de ingresso na reunião
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71e71ef3eafbd1b263d4bb6867c6601e5a7d8047
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="0fb73-102">Configurar a página de ingresso na reunião</span><span class="sxs-lookup"><span data-stu-id="0fb73-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fb73-103">_**Tópico da última modificação:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="0fb73-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="0fb73-104">Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página ingressar na reunião detecta se um cliente do Lync 2013 já está instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="0fb73-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="0fb73-105">Se um cliente já estiver instalado, esse cliente abrirá e ingressará na reunião.</span><span class="sxs-lookup"><span data-stu-id="0fb73-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="0fb73-106">Se um cliente não estiver instalado, por padrão, a versão 2013 do Lync Web App será aberta.</span><span class="sxs-lookup"><span data-stu-id="0fb73-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="0fb73-107">Você pode modificar o comportamento da página de associação de reunião se desejar permitir que os usuários ingressem em reuniões com o Office Communicator 2007 R2 ou o Lync 2010 Attendant.</span><span class="sxs-lookup"><span data-stu-id="0fb73-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="0fb73-108">Essas opções de configuração foram removidas do painel de controle do Lync Server 2013, mas você as configura usando o cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="0fb73-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="0fb73-109">Parâmetros de CsWebServiceConfiguration da página de ingresso na reunião</span><span class="sxs-lookup"><span data-stu-id="0fb73-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0fb73-110">Parâmetro CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="0fb73-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="0fb73-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="0fb73-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0fb73-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="0fb73-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="0fb73-113">Se definido como true, os usuários que ingressam em uma reunião usando um aplicativo cliente que não seja o Lync terão a oportunidade de ingressar na reunião usando o Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="0fb73-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="0fb73-114">O valor padrão é False.</span><span class="sxs-lookup"><span data-stu-id="0fb73-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fb73-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="0fb73-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="0fb73-116">Quando definida como true, as opções alternativas para ingressar em uma conferência online (como o Office Communicator 2007 R2) serão expandidas automaticamente e exibidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="0fb73-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span></span> <span data-ttu-id="0fb73-117">Quando definido como falso (o valor padrão), essas opções estarão disponíveis, mas o usuário precisará exibir a lista de opções para si mesmo.</span><span class="sxs-lookup"><span data-stu-id="0fb73-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="0fb73-118">Para configurar a página ingressar na reunião usando o Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fb73-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="0fb73-119">Inicie o Shell de gerenciamento do Lync Server 2013: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0fb73-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0fb73-120">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0fb73-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="0fb73-121">Esse cmdlet retorna as configurações de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="0fb73-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="0fb73-122">Execute o seguinte comando, com os parâmetros definidos como verdadeiro ou falso, dependendo da sua preferência (para obter detalhes sobre os parâmetros para esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="0fb73-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

