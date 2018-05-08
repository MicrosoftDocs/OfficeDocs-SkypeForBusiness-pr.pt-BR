---
title: Como a identificação de chamadas pode ser usada em sua organização
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: ID do chamador pode ser controlado para chamadas de entrada e saídas dos usuários de sistema telefônico usando uma política denominada CallingLineIdentity.
ms.openlocfilehash: a1a809805b96152e4b205c8f38b3c8409014eb55
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="70f7d-103">Como a identificação de chamadas pode ser usada em sua organização</span><span class="sxs-lookup"><span data-stu-id="70f7d-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="70f7d-104">ID do chamador pode ser controlado para chamadas de entrada e saídas dos usuários de sistema telefônico usando uma política denominada CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="70f7d-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="70f7d-105">A funcionalidade de ID do chamador está disponível para todos os usuários de sistema telefônico, independentemente de conectividade PSTN:</span><span class="sxs-lookup"><span data-stu-id="70f7d-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="70f7d-106">Conectividade PSTN Online</span><span class="sxs-lookup"><span data-stu-id="70f7d-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="70f7d-107">Conectividade PSTN local com o Skype for Business Cloud Connector Edition (exige o Cloud Connector Edition 1.4.2 e posterior)</span><span class="sxs-lookup"><span data-stu-id="70f7d-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="70f7d-108">Conectividade PSTN local com o Skype for Business Server (exige o Skype for Business Server 2015 CU5 e posterior)</span><span class="sxs-lookup"><span data-stu-id="70f7d-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="70f7d-109">[!OBSERVAçãO] Esta política não está disponível no Skype for Business 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="70f7d-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="70f7d-110">Identificação de chamada de saída</span><span class="sxs-lookup"><span data-stu-id="70f7d-110">Outbound caller ID</span></span>

<span data-ttu-id="70f7d-111">Existem três opções disponíveis para a identificação de chamada PSTN de saída:</span><span class="sxs-lookup"><span data-stu-id="70f7d-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="70f7d-112">O número de telefone atribuído ao usuário, que é o padrão.</span><span class="sxs-lookup"><span data-stu-id="70f7d-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="70f7d-113">Inventário de número em um número de telefone que é classificado como um *serviço* e número de *chamada gratuita* em seus planos chamar no telefone do Office 365.</span><span class="sxs-lookup"><span data-stu-id="70f7d-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="70f7d-114">Geralmente, ela é atribuída a uma fila de chamada e atendente automático organizacional.</span><span class="sxs-lookup"><span data-stu-id="70f7d-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="70f7d-115">Definido como anônimo.</span><span class="sxs-lookup"><span data-stu-id="70f7d-115">Set to anonymous.</span></span>
    
<span data-ttu-id="70f7d-116">No entanto, você não pode atribuir esses tipos de números de telefone para identificação de chamada de saída:</span><span class="sxs-lookup"><span data-stu-id="70f7d-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="70f7d-117">Inventário de número de qualquer números de telefone que são classificados como um *usuário* no seu telefone de planos de chamada</span><span class="sxs-lookup"><span data-stu-id="70f7d-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="70f7d-118">Um número de telefone local do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="70f7d-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="70f7d-119">Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="70f7d-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="70f7d-120">Controle de usuário final de identificação de chamada de saída</span><span class="sxs-lookup"><span data-stu-id="70f7d-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="70f7d-121">O atributo EnableUserOverride permite que um ou vários usuários alterem sua configuração de ID de chamador como **anônimo**.</span><span class="sxs-lookup"><span data-stu-id="70f7d-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="70f7d-122">Isso se aplica apenas quando uma política de CallingLineIdentity é configurada com um parâmetro de CallingIDSubstitute de LineURI ou substituto.</span><span class="sxs-lookup"><span data-stu-id="70f7d-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="70f7d-123">O valor padrão de EnableUserOverride é False.</span><span class="sxs-lookup"><span data-stu-id="70f7d-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="70f7d-124">Os usuários finais pode definir sua ID de chamador como **anônimo** usando a guia **Chamada encaminhar configurações** no Skype para o cliente de desktop de negócios.</span><span class="sxs-lookup"><span data-stu-id="70f7d-124">Your end users can set their caller ID to **Anonymous** by using the **Call Forward Settings** tab in the Skype for Business desktop client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="70f7d-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="70f7d-125">**Windows**</span></span> <br/> |<span data-ttu-id="70f7d-126">**Versão**</span><span class="sxs-lookup"><span data-stu-id="70f7d-126">**Version**</span></span> <br/> |<span data-ttu-id="70f7d-127">**Compatível**</span><span class="sxs-lookup"><span data-stu-id="70f7d-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="70f7d-128">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="70f7d-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="70f7d-129">CC (Current Channel) lançado em 6 de dezembro de 2016 - versão 1611 (Compilação 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="70f7d-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="70f7d-130">Sim</span><span class="sxs-lookup"><span data-stu-id="70f7d-130">Yes</span></span>  <br/> |
|<span data-ttu-id="70f7d-131">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="70f7d-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="70f7d-132">CC (Current Channel) lançado em 22 de fevereiro de 2017 - versão 1701 (Compilação 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="70f7d-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="70f7d-133">Sim</span><span class="sxs-lookup"><span data-stu-id="70f7d-133">Yes</span></span>  <br/> |
|<span data-ttu-id="70f7d-134">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="70f7d-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="70f7d-135">Adiada canal lançada em 13 de junho de 2017 - versão 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="70f7d-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="70f7d-136">Sim</span><span class="sxs-lookup"><span data-stu-id="70f7d-136">Yes</span></span>  <br/> |
|<span data-ttu-id="70f7d-137">MSI</span><span class="sxs-lookup"><span data-stu-id="70f7d-137">MSI</span></span>  <br/> |<span data-ttu-id="70f7d-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="70f7d-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="70f7d-139">Não</span><span class="sxs-lookup"><span data-stu-id="70f7d-139">No</span></span>  <br/> |
|<span data-ttu-id="70f7d-140">Mac</span><span class="sxs-lookup"><span data-stu-id="70f7d-140">Mac</span></span>  <br/> |<span data-ttu-id="70f7d-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="70f7d-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="70f7d-142">Não</span><span class="sxs-lookup"><span data-stu-id="70f7d-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="70f7d-143">Identificação de chamada de entrada</span><span class="sxs-lookup"><span data-stu-id="70f7d-143">Inbound Caller ID</span></span>

<span data-ttu-id="70f7d-144">O atributo BlockIncomingCallerID permite bloquear a ID de chamador nas chamadas PSTN de entrada.</span><span class="sxs-lookup"><span data-stu-id="70f7d-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="70f7d-145">Você pode definir esse atributo, mas ele não está disponível para seus usuários finais na página de configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="70f7d-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="70f7d-146">E ele está disponível atualmente apenas com a conectividade PSTN Online.</span><span class="sxs-lookup"><span data-stu-id="70f7d-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="70f7d-147">Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="70f7d-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="70f7d-148">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="70f7d-148">Related topics</span></span>
[<span data-ttu-id="70f7d-149">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="70f7d-149">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="70f7d-150">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="70f7d-150">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="70f7d-151">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="70f7d-151">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="70f7d-152">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="70f7d-152">Emergency calling terms and conditions</span></span>](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

<span data-ttu-id="70f7d-153">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="70f7d-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 