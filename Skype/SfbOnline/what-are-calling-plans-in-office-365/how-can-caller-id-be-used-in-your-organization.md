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
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: ID do chamador pode ser controlado para chamadas de entrada e saídas dos usuários de sistema telefônico usando uma política denominada CallingLineIdentity.
ms.openlocfilehash: df6c7c053b5dce4ffb1d121a1adbf829efda9943
ms.sourcegitcommit: 60e8365281ec6d780f1b2439bedef0bd71f002d8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2019
ms.locfileid: "30047893"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="00fce-103">Como a identificação de chamadas pode ser usada em sua organização</span><span class="sxs-lookup"><span data-stu-id="00fce-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="00fce-104">ID do chamador pode ser controlado para chamadas de entrada e saídas dos usuários de sistema telefônico usando uma política denominada CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="00fce-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="00fce-105">A funcionalidade de ID do chamador está disponível para todos os usuários de sistema telefônico, independentemente de conectividade PSTN:</span><span class="sxs-lookup"><span data-stu-id="00fce-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="00fce-106">Conectividade PSTN Online</span><span class="sxs-lookup"><span data-stu-id="00fce-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="00fce-107">Conectividade PSTN local com o Skype for Business Cloud Connector Edition (exige o Cloud Connector Edition 1.4.2 e posterior)</span><span class="sxs-lookup"><span data-stu-id="00fce-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="00fce-108">Conectividade PSTN local com o Skype for Business Server (exige o Skype for Business Server 2015 CU5 e posterior)</span><span class="sxs-lookup"><span data-stu-id="00fce-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="00fce-109">[!OBSERVAçãO] Esta política não está disponível no Skype for Business 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="00fce-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="00fce-110">Identificação de chamada de saída</span><span class="sxs-lookup"><span data-stu-id="00fce-110">Outbound caller ID</span></span>

<span data-ttu-id="00fce-111">Existem três opções disponíveis para a identificação de chamada PSTN de saída:</span><span class="sxs-lookup"><span data-stu-id="00fce-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="00fce-112">O número de telefone atribuído ao usuário, que é o padrão.</span><span class="sxs-lookup"><span data-stu-id="00fce-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="00fce-113">Um número de telefone que é classificado como um *serviço* e número de *chamada gratuita* em seus Planos de Chamada no inventário de números de telefono do Office 365.</span><span class="sxs-lookup"><span data-stu-id="00fce-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="00fce-114">Geralmente é atribuído a um atendente automático da organização ou a uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="00fce-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="00fce-115">Definido como anônimo.</span><span class="sxs-lookup"><span data-stu-id="00fce-115">Set to anonymous.</span></span>
    
<span data-ttu-id="00fce-116">No entanto, você não pode atribuir esses tipos de números de telefone para identificação de chamada de saída:</span><span class="sxs-lookup"><span data-stu-id="00fce-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="00fce-117">Inventário de número de qualquer números de telefone que são classificados como um *usuário* no seu telefone de planos de chamada</span><span class="sxs-lookup"><span data-stu-id="00fce-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="00fce-118">Um número de telefone local do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="00fce-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="00fce-119">Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="00fce-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="00fce-120">Controle de usuário final de identificação de chamada de saída</span><span class="sxs-lookup"><span data-stu-id="00fce-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="00fce-121">O atributo EnableUserOverride permite que um único ou vários usuários alterem a configuração da identificação de chamada para **Anônimo**.</span><span class="sxs-lookup"><span data-stu-id="00fce-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="00fce-122">Isso é aplicável apenas quando uma política CallingLineIdentity é configurada com um parâmetro CallingIDSubstitute da LineURI ou Substitute.</span><span class="sxs-lookup"><span data-stu-id="00fce-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="00fce-123">O valor padrão do EnableUserOverride é False.</span><span class="sxs-lookup"><span data-stu-id="00fce-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="00fce-124">Seus usuários finais podem definido sua ID de chamador como **anônimo** usando a guia **configurações** no Skype para o cliente de desktop de negócios, selecione **chamadas de um usuário final** (se habilitado pelo administrador), selecione informações de número e o perfil \*\*Ocultar meu telefone para todas as chamadas \*\*.</span><span class="sxs-lookup"><span data-stu-id="00fce-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="00fce-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="00fce-125">**Windows**</span></span> <br/> |<span data-ttu-id="00fce-126">**Versão**</span><span class="sxs-lookup"><span data-stu-id="00fce-126">**Version**</span></span> <br/> |<span data-ttu-id="00fce-127">**Compatível**</span><span class="sxs-lookup"><span data-stu-id="00fce-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="00fce-128">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="00fce-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="00fce-129">CC (Current Channel) lançado em 6 de dezembro de 2016 - versão 1611 (Compilação 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="00fce-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="00fce-130">Sim</span><span class="sxs-lookup"><span data-stu-id="00fce-130">Yes</span></span>  <br/> |
|<span data-ttu-id="00fce-131">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="00fce-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="00fce-132">CC (Current Channel) lançado em 22 de fevereiro de 2017 - versão 1701 (Compilação 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="00fce-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="00fce-133">Sim</span><span class="sxs-lookup"><span data-stu-id="00fce-133">Yes</span></span>  <br/> |
|<span data-ttu-id="00fce-134">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="00fce-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="00fce-135">Canal Adiado lançado em 13 de junho de 2017 - versão 1701 (Compilação 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="00fce-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="00fce-136">Sim</span><span class="sxs-lookup"><span data-stu-id="00fce-136">Yes</span></span>  <br/> |
|<span data-ttu-id="00fce-137">MSI</span><span class="sxs-lookup"><span data-stu-id="00fce-137">MSI</span></span>  <br/> |<span data-ttu-id="00fce-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="00fce-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="00fce-139">Não</span><span class="sxs-lookup"><span data-stu-id="00fce-139">No</span></span>  <br/> |
|<span data-ttu-id="00fce-140">Mac</span><span class="sxs-lookup"><span data-stu-id="00fce-140">Mac</span></span>  <br/> |<span data-ttu-id="00fce-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="00fce-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="00fce-142">Não</span><span class="sxs-lookup"><span data-stu-id="00fce-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="00fce-143">Identificação de chamada de entrada</span><span class="sxs-lookup"><span data-stu-id="00fce-143">Inbound Caller ID</span></span>

<span data-ttu-id="00fce-144">O atributo BlockIncomingCallerID permite o bloqueio da identificação de chamada nas chamadas PSTN de entrada.</span><span class="sxs-lookup"><span data-stu-id="00fce-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="00fce-145">Você pode definir esse atributo, mas ele não está disponível para seus usuários finais na página de configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="00fce-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="00fce-146">E ele está disponível atualmente apenas com a conectividade PSTN Online.</span><span class="sxs-lookup"><span data-stu-id="00fce-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="00fce-147">Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="00fce-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="00fce-148">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="00fce-148">Related topics</span></span>
[<span data-ttu-id="00fce-149">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="00fce-149">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="00fce-150">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="00fce-150">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="00fce-151">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="00fce-151">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="00fce-152">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="00fce-152">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="00fce-153">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="00fce-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
