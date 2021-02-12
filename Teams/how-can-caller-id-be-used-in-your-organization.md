---
title: Como a identificação de chamadas pode ser usada em sua organização
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: A ID de chamadas pode ser controlada para chamadas de entrada e saída para usuários do Sistema telefônico usando uma política chamada CallingLineIdentity.
ms.openlocfilehash: cd2074fec3027f1172b6ea681013f53994963cb5
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255444"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="389d6-103">Como a identificação de chamadas pode ser usada em sua organização</span><span class="sxs-lookup"><span data-stu-id="389d6-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="389d6-104">A ID de chamadas pode ser controlada para chamadas de entrada e saída para usuários do Sistema telefônico usando uma política chamada CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="389d6-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="389d6-105">A funcionalidade de ID de chamadas está disponível para todos os usuários do Sistema Telefônico, independentemente da conectividade PSTN:</span><span class="sxs-lookup"><span data-stu-id="389d6-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>

- <span data-ttu-id="389d6-106">Planos de Chamada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="389d6-106">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="389d6-107">Roteamento Direto do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="389d6-107">Phone System Direct Routing</span></span> 
  
- <span data-ttu-id="389d6-108">Conectividade PSTN Online</span><span class="sxs-lookup"><span data-stu-id="389d6-108">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="389d6-109">Conectividade PSTN local com o Skype for Business Cloud Connector Edition (exige o Cloud Connector Edition 1.4.2 e posterior)</span><span class="sxs-lookup"><span data-stu-id="389d6-109">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="389d6-110">Conectividade PSTN local com o Skype for Business Server (exige o Skype for Business Server 2015 CU5 e posterior)</span><span class="sxs-lookup"><span data-stu-id="389d6-110">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="389d6-111">[!OBSERVAçãO] Esta política não está disponível no Skype for Business 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="389d6-111">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="389d6-112">Identificação de chamada de saída</span><span class="sxs-lookup"><span data-stu-id="389d6-112">Outbound caller ID</span></span>

<span data-ttu-id="389d6-113">Há três opções disponíveis para a ID de chamador PSTN de saída:</span><span class="sxs-lookup"><span data-stu-id="389d6-113">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="389d6-114">O número de telefone atribuído ao usuário, que é o padrão.</span><span class="sxs-lookup"><span data-stu-id="389d6-114">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="389d6-115">Um número de telefone classificado como *serviço* e número *de* chamada gratuita no estoque de números de telefone dos Planos de Chamada.</span><span class="sxs-lookup"><span data-stu-id="389d6-115">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="389d6-116">Geralmente é atribuído a um atendente automático da organização ou a uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="389d6-116">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="389d6-117">Definido como anônimo.</span><span class="sxs-lookup"><span data-stu-id="389d6-117">Set to anonymous.</span></span>
    
<span data-ttu-id="389d6-118">No entanto, você não pode atribuir esses tipos de números de telefone para identificação de chamada de saída:</span><span class="sxs-lookup"><span data-stu-id="389d6-118">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="389d6-119">Todos os números de telefone classificados como usuário  *no inventário*  de números de telefone dos Planos de Chamada</span><span class="sxs-lookup"><span data-stu-id="389d6-119">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="389d6-120">Um número de telefone local do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="389d6-120">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="389d6-121">Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="389d6-121">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="389d6-122">Controle do usuário final da ID de chamada de saída</span><span class="sxs-lookup"><span data-stu-id="389d6-122">End user control of outbound caller ID</span></span>

<span data-ttu-id="389d6-123">O atributo EnableUserOverride permite que um ou vários usuários alterem a configuração da ID de chamada para **Anônimo.**</span><span class="sxs-lookup"><span data-stu-id="389d6-123">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="389d6-124">Isso é aplicável apenas quando uma política CallingLineIdentity é configurada com um parâmetro CallingIDSubstitute da LineURI ou Substitute.</span><span class="sxs-lookup"><span data-stu-id="389d6-124">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="389d6-125">O valor padrão do EnableUserOverride é False.</span><span class="sxs-lookup"><span data-stu-id="389d6-125">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="389d6-126">Os usuários finais podem definir a ID  de chamadas como **Anônimo** usando a guia Configurações no cliente de área de trabalho do Skype for Business, selecionar Chamar um Usuário Final **(se** habilitado pelo administrador) e, em seguida, selecionar Ocultar meu número de telefone e informações de perfil para todas as **chamadas.**</span><span class="sxs-lookup"><span data-stu-id="389d6-126">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="389d6-127">No Teams, os usuários podem ir para a imagem do perfil no canto superior direito, selecionar Configurações de Chamadas e, em seguida, em  >   **ID** do Chamador, selecionar Ocultar meu número de telefone e informações de perfil para todas as chamadas. </span><span class="sxs-lookup"><span data-stu-id="389d6-127">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="389d6-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="389d6-128">**Windows**</span></span> <br/> |<span data-ttu-id="389d6-129">**Versão**</span><span class="sxs-lookup"><span data-stu-id="389d6-129">**Version**</span></span> <br/> |<span data-ttu-id="389d6-130">**Compatível**</span><span class="sxs-lookup"><span data-stu-id="389d6-130">**Supported**</span></span> <br/> |
|<span data-ttu-id="389d6-131">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="389d6-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="389d6-132">CC (Current Channel) lançado em 6 de dezembro de 2016 - versão 1611 (Compilação 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="389d6-132">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="389d6-133">Sim</span><span class="sxs-lookup"><span data-stu-id="389d6-133">Yes</span></span>  <br/> |
|<span data-ttu-id="389d6-134">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="389d6-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="389d6-135">CC (Current Channel) lançado em 22 de fevereiro de 2017 - versão 1701 (Compilação 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="389d6-135">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="389d6-136">Sim</span><span class="sxs-lookup"><span data-stu-id="389d6-136">Yes</span></span>  <br/> |
|<span data-ttu-id="389d6-137">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="389d6-137">Click-to-Run</span></span>  <br/> |<span data-ttu-id="389d6-138">Canal Adiado lançado em 13 de junho de 2017 - versão 1701 (Compilação 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="389d6-138">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="389d6-139">Sim</span><span class="sxs-lookup"><span data-stu-id="389d6-139">Yes</span></span>  <br/> |
|<span data-ttu-id="389d6-140">MSI</span><span class="sxs-lookup"><span data-stu-id="389d6-140">MSI</span></span>  <br/> |<span data-ttu-id="389d6-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="389d6-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="389d6-142">Não</span><span class="sxs-lookup"><span data-stu-id="389d6-142">No</span></span>  <br/> |
|<span data-ttu-id="389d6-143">Mac</span><span class="sxs-lookup"><span data-stu-id="389d6-143">Mac</span></span>  <br/> |<span data-ttu-id="389d6-144">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="389d6-144">Skype for Business</span></span>  <br/> |<span data-ttu-id="389d6-145">Não</span><span class="sxs-lookup"><span data-stu-id="389d6-145">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="389d6-146">ID de chamador de entrada</span><span class="sxs-lookup"><span data-stu-id="389d6-146">Inbound caller ID</span></span>

<span data-ttu-id="389d6-147">O Sistema telefônico mostrará a ID chamada de um número de telefone externo se o número estiver associado a um usuário no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="389d6-147">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="389d6-148">Se o número de telefone não estiver no Azure AD, o nome de exibição fornecido por telco será mostrado se ele estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="389d6-148">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="389d6-149">O atributo BlockIncomingCallerID permite o bloqueio da identificação de chamada nas chamadas PSTN de entrada.</span><span class="sxs-lookup"><span data-stu-id="389d6-149">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="389d6-150">Você pode definir esse atributo, mas ele não está disponível para os usuários finais na página de configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="389d6-150">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="389d6-151">E ele está disponível atualmente apenas com a conectividade PSTN Online.</span><span class="sxs-lookup"><span data-stu-id="389d6-151">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="389d6-152">Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="389d6-152">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="389d6-153">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="389d6-153">Related topics</span></span>
[<span data-ttu-id="389d6-154">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="389d6-154">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="389d6-155">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="389d6-155">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="389d6-156">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="389d6-156">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="389d6-157">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="389d6-157">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="389d6-158">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="389d6-158">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
