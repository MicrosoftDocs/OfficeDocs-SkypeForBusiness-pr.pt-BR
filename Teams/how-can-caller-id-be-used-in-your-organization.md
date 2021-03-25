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
description: A ID do chamador pode ser controlada para chamadas de entrada e de saída para usuários do Sistema de Telefonia usando uma política chamada CallingLineIdentity.
ms.openlocfilehash: e723311b2780dd1d43bad4874b72133e09ff4fc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120672"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="5c6a2-103">Como a identificação de chamadas pode ser usada em sua organização</span><span class="sxs-lookup"><span data-stu-id="5c6a2-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="5c6a2-104">A ID do chamador pode ser controlada para chamadas de entrada e de saída para usuários do Sistema de Telefonia usando uma política chamada CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="5c6a2-105">A funcionalidade de ID do chamador está disponível para todos os usuários do Sistema de Telefonia, independentemente da conectividade PSTN:</span><span class="sxs-lookup"><span data-stu-id="5c6a2-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>

- <span data-ttu-id="5c6a2-106">Planos de Chamada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="5c6a2-106">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="5c6a2-107">Roteamento Direto do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="5c6a2-107">Phone System Direct Routing</span></span> 
  
- <span data-ttu-id="5c6a2-108">Conectividade PSTN Online</span><span class="sxs-lookup"><span data-stu-id="5c6a2-108">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="5c6a2-109">Conectividade PSTN local com o Skype for Business Cloud Connector Edition (exige o Cloud Connector Edition 1.4.2 e posterior)</span><span class="sxs-lookup"><span data-stu-id="5c6a2-109">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="5c6a2-110">Conectividade PSTN local com o Skype for Business Server (exige o Skype for Business Server 2015 CU5 e posterior)</span><span class="sxs-lookup"><span data-stu-id="5c6a2-110">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="5c6a2-111">[!OBSERVAçãO] Esta política não está disponível no Skype for Business 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-111">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="5c6a2-112">Identificação de chamada de saída</span><span class="sxs-lookup"><span data-stu-id="5c6a2-112">Outbound caller ID</span></span>

<span data-ttu-id="5c6a2-113">Há três opções disponíveis para a ID do chamador PSTN de saída:</span><span class="sxs-lookup"><span data-stu-id="5c6a2-113">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="5c6a2-114">O número de telefone atribuído ao usuário, que é o padrão.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-114">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="5c6a2-115">Um número de telefone que é classificado como um *número de* *serviço* e de chamada gratuita no inventário de números de telefone de Planos de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-115">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="5c6a2-116">Geralmente é atribuído a um atendente automático da organização ou a uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-116">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="5c6a2-117">Definido como anônimo.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-117">Set to anonymous.</span></span>
    
<span data-ttu-id="5c6a2-118">No entanto, você não pode atribuir esses tipos de números de telefone para identificação de chamada de saída:</span><span class="sxs-lookup"><span data-stu-id="5c6a2-118">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="5c6a2-119">Todos os números de telefone que são classificados como um  *usuário no*  inventário de números de telefone de Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="5c6a2-119">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="5c6a2-120">Um número de telefone local do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5c6a2-120">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="5c6a2-121">Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](./set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="5c6a2-121">To set the outbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="5c6a2-122">Controle do usuário final da ID do chamador de saída</span><span class="sxs-lookup"><span data-stu-id="5c6a2-122">End user control of outbound caller ID</span></span>

<span data-ttu-id="5c6a2-123">O atributo EnableUserOverride permite que usuários individuais ou múltiplos alterem a configuração de ID do chamador para **Anonymous**.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-123">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="5c6a2-124">Isso é aplicável apenas quando uma política CallingLineIdentity é configurada com um parâmetro CallingIDSubstitute da LineURI ou Substitute.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-124">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="5c6a2-125">O valor padrão do EnableUserOverride é False.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-125">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="5c6a2-126">Os usuários finais podem definir a ID  do chamador como **Anônimo** usando a guia Configurações no cliente da área de trabalho do Skype for Business, selecione Chamar um Usuário **Final** (se habilitado pelo administrador) e selecione **Ocultar** meu número de telefone e informações de perfil para todas as chamadas .</span><span class="sxs-lookup"><span data-stu-id="5c6a2-126">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="5c6a2-127">No Teams, os usuários podem ir para a imagem de perfil no canto superior direito, selecionar Configurações Chamadas e, em Seguida, em  >   **ID** do Chamador, selecione Ocultar meu número de telefone e informações de perfil para todas as **chamadas**.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-127">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="5c6a2-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="5c6a2-128">**Windows**</span></span> <br/> |<span data-ttu-id="5c6a2-129">**Versão**</span><span class="sxs-lookup"><span data-stu-id="5c6a2-129">**Version**</span></span> <br/> |<span data-ttu-id="5c6a2-130">**Compatível**</span><span class="sxs-lookup"><span data-stu-id="5c6a2-130">**Supported**</span></span> <br/> |
|<span data-ttu-id="5c6a2-131">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="5c6a2-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="5c6a2-132">CC (Current Channel) lançado em 6 de dezembro de 2016 - versão 1611 (Compilação 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="5c6a2-132">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="5c6a2-133">Sim</span><span class="sxs-lookup"><span data-stu-id="5c6a2-133">Yes</span></span>  <br/> |
|<span data-ttu-id="5c6a2-134">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="5c6a2-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="5c6a2-135">CC (Current Channel) lançado em 22 de fevereiro de 2017 - versão 1701 (Compilação 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="5c6a2-135">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="5c6a2-136">Sim</span><span class="sxs-lookup"><span data-stu-id="5c6a2-136">Yes</span></span>  <br/> |
|<span data-ttu-id="5c6a2-137">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="5c6a2-137">Click-to-Run</span></span>  <br/> |<span data-ttu-id="5c6a2-138">Canal Adiado lançado em 13 de junho de 2017 - versão 1701 (Compilação 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="5c6a2-138">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="5c6a2-139">Sim</span><span class="sxs-lookup"><span data-stu-id="5c6a2-139">Yes</span></span>  <br/> |
|<span data-ttu-id="5c6a2-140">MSI</span><span class="sxs-lookup"><span data-stu-id="5c6a2-140">MSI</span></span>  <br/> |<span data-ttu-id="5c6a2-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5c6a2-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="5c6a2-142">Não</span><span class="sxs-lookup"><span data-stu-id="5c6a2-142">No</span></span>  <br/> |
|<span data-ttu-id="5c6a2-143">Mac</span><span class="sxs-lookup"><span data-stu-id="5c6a2-143">Mac</span></span>  <br/> |<span data-ttu-id="5c6a2-144">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5c6a2-144">Skype for Business</span></span>  <br/> |<span data-ttu-id="5c6a2-145">Não</span><span class="sxs-lookup"><span data-stu-id="5c6a2-145">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="5c6a2-146">ID do chamador de entrada</span><span class="sxs-lookup"><span data-stu-id="5c6a2-146">Inbound caller ID</span></span>

<span data-ttu-id="5c6a2-147">O Sistema de Telefonia mostrará a ID chamada para um número de telefone externo se o número estiver associado a um usuário no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-147">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="5c6a2-148">Se o número de telefone não estiver no Azure AD, o nome de exibição fornecido por telco será mostrado se ele estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-148">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="5c6a2-149">O atributo BlockIncomingCallerID permite o bloqueio da identificação de chamada nas chamadas PSTN de entrada.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-149">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="5c6a2-150">Você pode definir esse atributo, mas ele não está disponível para os usuários finais na página de configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-150">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="5c6a2-151">E ele está disponível atualmente apenas com a conectividade PSTN Online.</span><span class="sxs-lookup"><span data-stu-id="5c6a2-151">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="5c6a2-152">Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](./set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="5c6a2-152">To set the outbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5c6a2-153">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5c6a2-153">Related topics</span></span>
[<span data-ttu-id="5c6a2-154">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="5c6a2-154">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="5c6a2-155">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="5c6a2-155">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="5c6a2-156">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="5c6a2-156">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="5c6a2-157">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="5c6a2-157">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="5c6a2-158">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="5c6a2-158">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
