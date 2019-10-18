---
title: Como a identificação de chamadas pode ser usada em sua organização
author: CarolynRowe
ms.author: crowe
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
f1keywords: ms.teamsadmincenter.voice.callerid.overview
ms.custom:
- Calling Plans
description: A identificação de chamadas pode ser controlada para chamadas de entrada e de saída para usuários do sistema telefônico usando uma política chamada CallingLineIdentity.
ms.openlocfilehash: 671ee484cbb5cccd78f6512d714a4dd0954524b0
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570744"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="2a6f9-103">Como a identificação de chamadas pode ser usada em sua organização</span><span class="sxs-lookup"><span data-stu-id="2a6f9-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="2a6f9-104">A identificação de chamadas pode ser controlada para chamadas de entrada e de saída para usuários do sistema telefônico usando uma política chamada CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="2a6f9-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="2a6f9-105">A funcionalidade de identificação de chamadas está disponível para todos os usuários do sistema telefônico independentemente da conectividade PSTN:</span><span class="sxs-lookup"><span data-stu-id="2a6f9-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="2a6f9-106">Conectividade PSTN Online</span><span class="sxs-lookup"><span data-stu-id="2a6f9-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="2a6f9-107">Conectividade PSTN local com o Skype for Business Cloud Connector Edition (exige o Cloud Connector Edition 1.4.2 e posterior)</span><span class="sxs-lookup"><span data-stu-id="2a6f9-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="2a6f9-108">Conectividade PSTN local com o Skype for Business Server (exige o Skype for Business Server 2015 CU5 e posterior)</span><span class="sxs-lookup"><span data-stu-id="2a6f9-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="2a6f9-109">[!OBSERVAçãO] Esta política não está disponível no Skype for Business 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="2a6f9-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="2a6f9-110">Identificação de chamada de saída</span><span class="sxs-lookup"><span data-stu-id="2a6f9-110">Outbound caller ID</span></span>

<span data-ttu-id="2a6f9-111">Existem três opções disponíveis para a identificação de chamada PSTN de saída:</span><span class="sxs-lookup"><span data-stu-id="2a6f9-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="2a6f9-112">O número de telefone atribuído ao usuário, que é o padrão.</span><span class="sxs-lookup"><span data-stu-id="2a6f9-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="2a6f9-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span><span class="sxs-lookup"><span data-stu-id="2a6f9-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="2a6f9-115">Definido como anônimo.</span><span class="sxs-lookup"><span data-stu-id="2a6f9-115">Set to anonymous.</span></span>
    
<span data-ttu-id="2a6f9-116">No entanto, você não pode atribuir esses tipos de números de telefone para identificação de chamada de saída:</span><span class="sxs-lookup"><span data-stu-id="2a6f9-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="2a6f9-117">Qualquer número de telefone classificado como um *usuário* em seu plano de número de telefone de planos de chamadas</span><span class="sxs-lookup"><span data-stu-id="2a6f9-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="2a6f9-118">Um número de telefone local do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2a6f9-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="2a6f9-119">Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="2a6f9-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="2a6f9-120">Controle de usuário final de identificação de chamada de saída</span><span class="sxs-lookup"><span data-stu-id="2a6f9-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="2a6f9-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span><span class="sxs-lookup"><span data-stu-id="2a6f9-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="2a6f9-124">Seus usuários finais podem definir a identificação de chamadas como **anônimas** usando a guia **configurações** no cliente da área de trabalho do Skype for Business, selecionar **chamadas para um usuário final** (se habilitado pelo administrador), selecionar \*\*ocultar meu número de telefone e informações de perfil para todas as chamadas \*\*.</span><span class="sxs-lookup"><span data-stu-id="2a6f9-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="2a6f9-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="2a6f9-125">**Windows**</span></span> <br/> |<span data-ttu-id="2a6f9-126">**Versão**</span><span class="sxs-lookup"><span data-stu-id="2a6f9-126">**Version**</span></span> <br/> |<span data-ttu-id="2a6f9-127">**Compatível**</span><span class="sxs-lookup"><span data-stu-id="2a6f9-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="2a6f9-128">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="2a6f9-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="2a6f9-129">CC (Current Channel) lançado em 6 de dezembro de 2016 - versão 1611 (Compilação 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="2a6f9-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="2a6f9-130">Sim</span><span class="sxs-lookup"><span data-stu-id="2a6f9-130">Yes</span></span>  <br/> |
|<span data-ttu-id="2a6f9-131">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="2a6f9-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="2a6f9-132">CC (Current Channel) lançado em 22 de fevereiro de 2017 - versão 1701 (Compilação 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="2a6f9-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="2a6f9-133">Sim</span><span class="sxs-lookup"><span data-stu-id="2a6f9-133">Yes</span></span>  <br/> |
|<span data-ttu-id="2a6f9-134">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="2a6f9-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="2a6f9-135">Canal Adiado lançado em 13 de junho de 2017 - versão 1701 (Compilação 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="2a6f9-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="2a6f9-136">Sim</span><span class="sxs-lookup"><span data-stu-id="2a6f9-136">Yes</span></span>  <br/> |
|<span data-ttu-id="2a6f9-137">MSI</span><span class="sxs-lookup"><span data-stu-id="2a6f9-137">MSI</span></span>  <br/> |<span data-ttu-id="2a6f9-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2a6f9-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="2a6f9-139">Não</span><span class="sxs-lookup"><span data-stu-id="2a6f9-139">No</span></span>  <br/> |
|<span data-ttu-id="2a6f9-140">Mac</span><span class="sxs-lookup"><span data-stu-id="2a6f9-140">Mac</span></span>  <br/> |<span data-ttu-id="2a6f9-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2a6f9-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="2a6f9-142">Não</span><span class="sxs-lookup"><span data-stu-id="2a6f9-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="2a6f9-143">Identificação de chamada de entrada</span><span class="sxs-lookup"><span data-stu-id="2a6f9-143">Inbound Caller ID</span></span>

<span data-ttu-id="2a6f9-144">O sistema de telefonia mostrará a ID chamada para um número de telefone externo se o número estiver associado a um usuário no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2a6f9-144">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="2a6f9-145">Se o número de telefone não estiver no Azure AD, o nome de exibição fornecido pela Telco será exibido se estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="2a6f9-145">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="2a6f9-146">O atributo BlockIncomingCallerID permite o bloqueio da identificação de chamada nas chamadas PSTN de entrada.</span><span class="sxs-lookup"><span data-stu-id="2a6f9-146">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="2a6f9-147">Você pode definir esse atributo, mas ele não está disponível para os usuários finais na página Configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="2a6f9-147">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="2a6f9-148">E ele está disponível atualmente apenas com a conectividade PSTN Online.</span><span class="sxs-lookup"><span data-stu-id="2a6f9-148">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="2a6f9-149">Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="2a6f9-149">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2a6f9-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2a6f9-150">Related topics</span></span>
[<span data-ttu-id="2a6f9-151">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="2a6f9-151">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="2a6f9-152">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="2a6f9-152">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="2a6f9-153">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="2a6f9-153">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="2a6f9-154">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="2a6f9-154">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="2a6f9-155">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="2a6f9-155">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
