---
title: Configurar a página de ingresso na reunião
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Quando um usuário clica em um link da reunião em uma solicitação de reunião, a reunião página de ingresso detecta qual cliente já estiver instalado no computador do usuário. Se um cliente já estiver instalado, o que o cliente abre e participa da reunião. Se um cliente não estiver instalado, por padrão, que o aplicativo Web é aberta.
ms.openlocfilehash: 88ae915318505efef6ae716a17217aaa1e7b12df
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879937"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="d943a-105">Configurar a página de ingresso na reunião</span><span class="sxs-lookup"><span data-stu-id="d943a-105">Configure the meeting join page</span></span>

<span data-ttu-id="d943a-106">Quando um usuário clica em um link da reunião em uma solicitação de reunião, a reunião página de ingresso detecta qual cliente já estiver instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="d943a-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="d943a-107">Se um cliente já estiver instalado, o que o cliente abre e participa da reunião.</span><span class="sxs-lookup"><span data-stu-id="d943a-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="d943a-108">Se um cliente não estiver instalado, por padrão, que o aplicativo Web é aberta.</span><span class="sxs-lookup"><span data-stu-id="d943a-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="d943a-109">Você pode modificar o comportamento de participação da reunião se você quiser permitir que os usuários ingressem em reuniões de página.</span><span class="sxs-lookup"><span data-stu-id="d943a-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="d943a-110">Essas opções de configuração foram removidas do painel de controle, mas você pode configurá-los usando o cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d943a-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="d943a-111">**Parâmetros de CsWebServiceConfiguration da página de participação de reunião**</span><span class="sxs-lookup"><span data-stu-id="d943a-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="d943a-112">**Parâmetro CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="d943a-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="d943a-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d943a-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d943a-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="d943a-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="d943a-115">Se definido como True, usuários participando de uma reunião usando um aplicativo cliente diferente do Lync receberá a oportunidade de ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="d943a-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="d943a-116">O valor padrão é False.</span><span class="sxs-lookup"><span data-stu-id="d943a-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="d943a-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="d943a-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="d943a-118">Quando definido como True, alternados opções para ingressar em uma conferência online será automaticamente expandida e exibido aos usuários.</span><span class="sxs-lookup"><span data-stu-id="d943a-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="d943a-119">Quando definido como False (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções para si próprios.</span><span class="sxs-lookup"><span data-stu-id="d943a-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="d943a-120">Para configurar a reunião página de ingresso usando Skype do Shell de gerenciamento do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d943a-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="d943a-121">Inicie o Skype do Shell de gerenciamento do Business Server 2019: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server 2019**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="d943a-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d943a-122">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d943a-122">Run the following cmdlet:</span></span> 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="d943a-123">Este cmdlet retorna as definições de configuração de serviço de web.</span><span class="sxs-lookup"><span data-stu-id="d943a-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="d943a-124">Execute o seguinte comando, com os parâmetros definidos para verdadeiro ou falso, dependendo da sua preferência (para obter detalhes sobre os parâmetros deste cmdlet, consulte a documentação do [Skype do Shell de gerenciamento do servidor de negócios](../../SfbServer/manage/management-shell.md) ):</span><span class="sxs-lookup"><span data-stu-id="d943a-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


