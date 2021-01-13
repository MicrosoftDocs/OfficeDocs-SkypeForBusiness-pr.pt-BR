---
title: Planejar linhas telefônicas privadas com o Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planejamento de linhas telefônicas privadas (secundárias) no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 0ae62c4ee56a16583106c89b5ca1b190ee242e2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813591"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a><span data-ttu-id="e17dd-103">Planejar linhas telefônicas privadas com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e17dd-103">Plan for private telephone lines with Skype for Business</span></span>
 
<span data-ttu-id="e17dd-104">Planejamento de linhas telefônicas privadas (secundárias) no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="e17dd-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="e17dd-105">O Skype for Business Server permite que você dê aos usuários uma segunda linha telefônica privada, além da linha telefônica principal.</span><span class="sxs-lookup"><span data-stu-id="e17dd-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="e17dd-106">Linhas telefônicas privadas são frequentemente atribuídas a executivos e a outras pessoas que desejam um número de telefone não esteja listado e através do qual podem ser diretamente contatados.</span><span class="sxs-lookup"><span data-stu-id="e17dd-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="e17dd-107">Linhas telefônicas privadas só podem ser configuradas com o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e17dd-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="e17dd-108">Não é possível configurar linhas telefônicas privadas com o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e17dd-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="e17dd-109">Linhas telefônicas privadas devem ser configuradas apenas em implantações do Skype for Business Server e não em implantações mistas.</span><span class="sxs-lookup"><span data-stu-id="e17dd-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="e17dd-110">Características das linhas telefônicas privadas</span><span class="sxs-lookup"><span data-stu-id="e17dd-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="e17dd-111">Embora o conceito de uma segunda linha telefônica privada seja fundamentalmente simples, é importante compreender as características das linhas privadas e as maneiras nas quais elas são semelhantes e diferentes das linhas telefônicas principais dos usuários.</span><span class="sxs-lookup"><span data-stu-id="e17dd-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="e17dd-112">Características gerais das linhas telefônicas privadas</span><span class="sxs-lookup"><span data-stu-id="e17dd-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="e17dd-113">Um usuário pode ter somente uma linha telefônica privada.</span><span class="sxs-lookup"><span data-stu-id="e17dd-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="e17dd-114">Um usuário com uma linha telefônica privada só possui uma caixa postal e recebe notificações de chamadas perdidas em um único endereço de e-mail.</span><span class="sxs-lookup"><span data-stu-id="e17dd-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="e17dd-115">Um usuário com uma linha telefônica privada não possui um segundo endereço SIP e uma linha telefônica privada secundária não dá a ele uma segunda presença na rede (como uma segunda identidade no sistema de mensagens instantâneas).</span><span class="sxs-lookup"><span data-stu-id="e17dd-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="e17dd-116">Linhas telefônicas privadas estão disponíveis somente para implantações locais.</span><span class="sxs-lookup"><span data-stu-id="e17dd-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="e17dd-117">Eles não estão disponíveis com implantações hospedadas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e17dd-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="e17dd-118">Como linhas telefônicas privadas diferem de linhas telefônicas principais</span><span class="sxs-lookup"><span data-stu-id="e17dd-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="e17dd-119">Os números de telefone para linhas telefônicas privadas não aparecem nos diretórios telefônicos ou listas de Contatos derivados dos Serviços de Domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e17dd-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="e17dd-120">Nenhum dos seguintes recursos está disponível com uma linha telefônica privada: encaminhamento de chamadas, chamada de equipe, delegação, anel de equipe, Atendimento de Chamadas em Grupo e Aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="e17dd-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="e17dd-121">Chamadas para uma linha telefônica privada possuem um toque especial e a notificação do sistema para as chamadas diz ao usuário que a chamada de entrada está em sua linha privada.</span><span class="sxs-lookup"><span data-stu-id="e17dd-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="e17dd-p104">Chamadas para a linha telefônica privada sempre tocam. Elas não seguem as regras "não incomodar".</span><span class="sxs-lookup"><span data-stu-id="e17dd-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="e17dd-124">Linhas telefônicas privadas são somente de entrada e não podem ser usadas para fazer chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="e17dd-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="e17dd-125">Quando um usuário com uma linha telefônica privada faz uma chamada, ela se origina da linha telefônica principal do usuário e não oculta o nome do usuário ou o número de telefone principal da pessoa chamada.</span><span class="sxs-lookup"><span data-stu-id="e17dd-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="e17dd-126">Como linhas telefônicas privadas são similares a linhas telefônicas principais</span><span class="sxs-lookup"><span data-stu-id="e17dd-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="e17dd-127">Chamadas não atendidas para uma linha telefônica privada são roteadas para a mesma caixa postal da linha telefônica principal (se a caixa postal estiver habilitada).</span><span class="sxs-lookup"><span data-stu-id="e17dd-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="e17dd-128">O estacionamento de chamada e o atendimento de chamadas funcionam com linhas telefônicas privadas exatamente da mesma maneira que fazem com a linha telefônica principal do usuário.</span><span class="sxs-lookup"><span data-stu-id="e17dd-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="e17dd-129">Quando o toque simultâneo está habilitado na linha telefônica principal de um usuário, ele também é habilitado na linha telefônica privada.</span><span class="sxs-lookup"><span data-stu-id="e17dd-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="e17dd-130">O número de telefone de uma linha telefônica privada é registrado no registro de detalhes da chamada da mesma maneira que o número de telefone da linha telefônica principal de um usuário, mas com uma indicação de que é um número de telefone privado.</span><span class="sxs-lookup"><span data-stu-id="e17dd-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="e17dd-131">Depois que um usuário atende uma chamada em uma linha telefônica privada, ela é tratada da mesma forma que uma chamada na linha telefônica principal do usuário.</span><span class="sxs-lookup"><span data-stu-id="e17dd-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="e17dd-132">Por exemplo, se um usuário que recebe uma chamada em uma linha telefônica privada encaminhar a chamada ou convidar outras pessoas para uma chamada em conferência, o nome do usuário aparecerá no Skype for Business e o número de telefone da linha telefônica principal do usuário aparecerá no ID do chamador.</span><span class="sxs-lookup"><span data-stu-id="e17dd-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="e17dd-133">Um usuário pode desviar uma chamada (redirecionar para outro destino, como um telefone celular ou residencial, antes de atender) a partir da linha telefônica privada da mesma maneira como o faria com uma linha telefônica principal.</span><span class="sxs-lookup"><span data-stu-id="e17dd-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e17dd-134">Quando uma chamada para uma linha privada é roteada para um número de telefone alternativo, o número para a linha telefônica privada é disponibilizado para o número de telefone alternativo e pode ser exibido nos logs para aquele número.</span><span class="sxs-lookup"><span data-stu-id="e17dd-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="e17dd-135">Chamadas de uma conferência para a linha telefônica privada não terão uma indicação  *de*  linha privada na notificação do sistema de entrada.</span><span class="sxs-lookup"><span data-stu-id="e17dd-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="e17dd-136">Como administrar linhas telefônicas privadas</span><span class="sxs-lookup"><span data-stu-id="e17dd-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="e17dd-p107">Além dos aspectos técnicos da criação e gerenciamento de linhas telefônicas privadas, você precisará estabelecer procedimentos administrativos para elas. Isso inclui determinar políticas para quem na organização está elegível para uma linha privada, criar e manter listas de pessoas e suas linhas telefônicas, possivelmente criar um diretório de telefonia privada para executivos, providenciar o treinamento dos usuários e tarefas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="e17dd-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e17dd-p108">A linha telefônica privada é armazenada no Active Directory como um atributo msRTCSIP-PrivateLine no objeto do usuário. Por padrão, qualquer membro do grupo Usuários Autenticados tem acesso de leitura a este atributo.</span><span class="sxs-lookup"><span data-stu-id="e17dd-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="e17dd-141">Como atribuir números de telefone</span><span class="sxs-lookup"><span data-stu-id="e17dd-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="e17dd-142">Contas para novos usuários que precisam de linhas telefônicas privadas são criadas da mesma maneira que contas sem linhas telefônicas privadas, usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e17dd-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="e17dd-143">Use o cmdlet **Set-CsUser** no Shell de Gerenciamento do Skype for Business Server para atribuir um número de telefone a uma linha telefônica privada para um usuário, por exemplo, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span><span class="sxs-lookup"><span data-stu-id="e17dd-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="e17dd-144">Números de telefone para linhas telefônicas privadas podem ter entre 3 e 15 números de comprimento e devem ser precedidas pelo prefixo "TEL:".</span><span class="sxs-lookup"><span data-stu-id="e17dd-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="e17dd-145">Podem ter qualquer código de área e qualquer código de país/região, desde que sua organização tenha discagem interna direta para aquele código de área e código de país/região.</span><span class="sxs-lookup"><span data-stu-id="e17dd-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="e17dd-146">Para obter detalhes sobre cmdlets e o Shell de Gerenciamento do Skype for Business Server, consulte a documentação do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e17dd-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="e17dd-147">Linhas telefônicas privadas em implantações mistas</span><span class="sxs-lookup"><span data-stu-id="e17dd-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="e17dd-148">Linhas telefônicas privadas devem ser configuradas apenas para implantações do Skype for Business Server ou do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e17dd-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="e17dd-149">Em uma implantação na qual há servidores executando versões anteriores do Lync Server, quando um usuário em uma versão anterior tenta ligar para uma linha telefônica privada, o roteamento da chamada falha porque o servidor não pode executar uma busca inversa em uma linha telefônica privada.</span><span class="sxs-lookup"><span data-stu-id="e17dd-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

