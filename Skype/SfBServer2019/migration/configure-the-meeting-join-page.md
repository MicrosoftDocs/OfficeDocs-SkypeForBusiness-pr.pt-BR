---
title: Configurar a página de ingresso na reunião
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página ingressar na reunião detecta qual cliente já está instalado no computador do usuário. Se um cliente já estiver instalado, esse cliente abrirá e ingressará na reunião. Se um cliente não estiver instalado, por padrão o aplicativo Web será aberto.
ms.openlocfilehash: 35b8b816d5c01f3061dc697cf7f37a4314a5f083
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813789"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="7e3eb-105">Configurar a página de ingresso na reunião</span><span class="sxs-lookup"><span data-stu-id="7e3eb-105">Configure the meeting join page</span></span>

<span data-ttu-id="7e3eb-106">Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página ingressar na reunião detecta qual cliente já está instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="7e3eb-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="7e3eb-107">Se um cliente já estiver instalado, esse cliente abrirá e ingressará na reunião.</span><span class="sxs-lookup"><span data-stu-id="7e3eb-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="7e3eb-108">Se um cliente não estiver instalado, por padrão o aplicativo Web será aberto.</span><span class="sxs-lookup"><span data-stu-id="7e3eb-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="7e3eb-109">Você pode modificar o comportamento da página de associação de reunião se desejar permitir que os usuários ingressem em reuniões.</span><span class="sxs-lookup"><span data-stu-id="7e3eb-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="7e3eb-110">Essas opções de configuração foram removidas do painel de controle, mas você as configura usando o cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="7e3eb-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="7e3eb-111">**Parâmetros de CsWebServiceConfiguration da página de ingresso na reunião**</span><span class="sxs-lookup"><span data-stu-id="7e3eb-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="7e3eb-112">**Parâmetro CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="7e3eb-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="7e3eb-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7e3eb-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7e3eb-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="7e3eb-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="7e3eb-115">Se definido como verdadeiro, os usuários que ingressam em uma reunião usando um aplicativo cliente que não seja o Lync terão a oportunidade de ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="7e3eb-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="7e3eb-116">O valor padrão é False.</span><span class="sxs-lookup"><span data-stu-id="7e3eb-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="7e3eb-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="7e3eb-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="7e3eb-118">Quando definida como true, as opções alternativas para ingressar em uma conferência online serão expandidas automaticamente e exibidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="7e3eb-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="7e3eb-119">Quando definido como falso (o valor padrão), essas opções estarão disponíveis, mas o usuário precisará exibir a lista de opções para si mesmo.</span><span class="sxs-lookup"><span data-stu-id="7e3eb-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="7e3eb-120">Para configurar a página ingressar na reunião usando o Shell de gerenciamento do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="7e3eb-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="7e3eb-121">Inicie o Shell de gerenciamento do Skype for Business Server 2019: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="7e3eb-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="7e3eb-122">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7e3eb-122">Run the following cmdlet:</span></span> 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="7e3eb-123">Esse cmdlet retorna as configurações de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="7e3eb-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="7e3eb-124">Execute o seguinte comando, com os parâmetros definidos como verdadeiro ou falso, dependendo da sua preferência (para obter detalhes sobre os parâmetros para esse cmdlet, consulte a documentação do [Shell de gerenciamento do Skype for Business Server](../../SfbServer/manage/management-shell.md) ):</span><span class="sxs-lookup"><span data-stu-id="7e3eb-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


