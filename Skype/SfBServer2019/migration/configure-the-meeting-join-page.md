---
title: Configurar a página de ingresso na reunião
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de ingresso na reunião detecta qual cliente já está instalado no computador do usuário. Se um cliente já estiver instalado, esse cliente abre e participa da reunião. Se um cliente não estiver instalado, por padrão, o aplicativo Web será aberto.
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754021"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="26937-105">Configurar a página de ingresso na reunião</span><span class="sxs-lookup"><span data-stu-id="26937-105">Configure the meeting join page</span></span>

<span data-ttu-id="26937-106">Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de ingresso na reunião detecta qual cliente já está instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="26937-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="26937-107">Se um cliente já estiver instalado, esse cliente abre e participa da reunião.</span><span class="sxs-lookup"><span data-stu-id="26937-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="26937-108">Se um cliente não estiver instalado, por padrão, o aplicativo Web será aberto.</span><span class="sxs-lookup"><span data-stu-id="26937-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="26937-109">Você pode modificar o comportamento da página de ingresso na reunião se quiser permitir que os usuários ingressem em reuniões.</span><span class="sxs-lookup"><span data-stu-id="26937-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="26937-110">Essas opções de configuração foram removidas do painel de controle, mas você as configura usando o cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="26937-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="26937-111">**Parâmetros CsWebServiceConfiguration da página de ingresso em reunião**</span><span class="sxs-lookup"><span data-stu-id="26937-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="26937-112">**Parâmetro CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="26937-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="26937-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="26937-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="26937-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="26937-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="26937-115">Se for definido como true, os usuários que ingressarem em uma reunião usando um aplicativo cliente que não seja o Lync terão a oportunidade de participar da reunião.</span><span class="sxs-lookup"><span data-stu-id="26937-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="26937-116">O valor padrão é False.</span><span class="sxs-lookup"><span data-stu-id="26937-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="26937-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="26937-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="26937-118">Quando definido como true, as opções alternativas para ingressar em uma conferência online serão expandidas automaticamente e mostradas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="26937-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="26937-119">Quando definido como false (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções para elas.</span><span class="sxs-lookup"><span data-stu-id="26937-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="26937-120">Para configurar a página de ingresso na reunião usando o Shell de gerenciamento do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="26937-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="26937-121">Inicie o Shell de gerenciamento do Skype for Business Server 2019: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="26937-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="26937-122">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="26937-122">Run the following cmdlet:</span></span> 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="26937-123">Este cmdlet retorna as definições de configurações do serviço da Web.</span><span class="sxs-lookup"><span data-stu-id="26937-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="26937-124">Execute o seguinte comando, com os parâmetros definidos como true ou false, dependendo da sua preferência (para obter detalhes sobre os parâmetros desse cmdlet, consulte a documentação do [Shell de gerenciamento do Skype for Business Server](../../SfbServer/manage/management-shell.md) ):</span><span class="sxs-lookup"><span data-stu-id="26937-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


