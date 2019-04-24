---
title: Plano para linhas telefônicas privadas com Skype para negócios
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planejando para linhas telefônicas privadas de (secundário) Skype Business Server Enterprise Voice.
ms.openlocfilehash: 16c5b6e29041280bf92f849bd327d864c7b58e15
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206533"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a><span data-ttu-id="8c7c0-103">Plano para linhas telefônicas privadas com Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="8c7c0-103">Plan for private telephone lines with Skype for Business</span></span>
 
<span data-ttu-id="8c7c0-104">Planejando para linhas telefônicas privadas de (secundário) Skype Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="8c7c0-105">Skype para Business Server permite fornecer aos usuários uma linha telefônica privada, de segunda além dos seu linha telefônica principal.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="8c7c0-106">Linhas telefônicas privadas são frequentemente atribuídas a executivos e a outras pessoas que desejam um número de telefone não listado e através do qual podem ser diretamente contatados.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="8c7c0-107">Linhas telefônicas privadas só podem ser configuradas com o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="8c7c0-108">Você não pode configurar linhas telefônicas privadas com o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="8c7c0-109">Linhas telefônicas privadas devem ser configuradas somente em implantações do Skype para Business Server e não em implantações mistas.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="8c7c0-110">Características das linhas telefônicas privadas</span><span class="sxs-lookup"><span data-stu-id="8c7c0-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="8c7c0-111">Embora o conceito de uma linha telefônica privada, de segunda fundamentalmente simple, é importante compreender as características das linhas privadas e das formas nas quais elas são semelhantes às e diferentes das linhas de telefone principal dos usuários.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="8c7c0-112">Características gerais das linhas telefônicas privadas</span><span class="sxs-lookup"><span data-stu-id="8c7c0-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="8c7c0-113">Um usuário pode ter somente uma linha telefônica privada.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="8c7c0-114">Um usuário com uma linha telefônica privada só possui uma caixa postal e recebe notificações de chamadas perdidas em um único endereço de e-mail.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="8c7c0-115">Um usuário com uma linha telefônica privada não possui um segundo endereço SIP e uma linha telefônica privada secundária não dá a ele uma segunda presença na rede (como uma segunda identidade no sistema de mensagens instantâneas).</span><span class="sxs-lookup"><span data-stu-id="8c7c0-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="8c7c0-116">Linhas telefônicas privadas estão disponíveis somente para implantações locais.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="8c7c0-117">Eles não estão disponíveis com implantações hospedadas do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="8c7c0-118">Como linhas telefônicas privadas diferem de linhas telefônicas principais</span><span class="sxs-lookup"><span data-stu-id="8c7c0-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="8c7c0-119">Os números de telefone para linhas telefônicas privadas não aparecem nos diretórios telefônicos ou listas de Contatos derivados dos Serviços de Domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="8c7c0-120">Nenhum dos recursos a seguir está disponível com uma linha telefônica privada: encaminhamento de chamadas, chamada de equipe, delegação, toque de equipe, recebimento de chamadas de grupo e aplicativo Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="8c7c0-121">Chamadas para uma linha telefônica privada têm um toque especial e a notificação do sistema para as chamadas diz ao usuário que a chamada de entrada está em sua linha privada.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="8c7c0-p104">Chamadas para a linha telefônica privada sempre tocam. Elas não seguem as regras "não incomodar".</span><span class="sxs-lookup"><span data-stu-id="8c7c0-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="8c7c0-124">Linhas telefônicas privadas são somente de entrada e não podem ser usadas para fazer chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="8c7c0-125">Quando um usuário com uma linha telefônica privada faz uma chamada, a chamada for originada da linha de telefone principal do usuário e não oculta o nome do usuário ou número de telefone principal do usuário da pessoa chamada.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="8c7c0-126">Como linhas telefônicas privadas são similares a linhas telefônicas principais</span><span class="sxs-lookup"><span data-stu-id="8c7c0-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="8c7c0-127">Chamadas não atendidas para uma linha telefônica privada são roteadas para a mesma caixa postal da linha telefônica principal (se a caixa postal estiver habilitada).</span><span class="sxs-lookup"><span data-stu-id="8c7c0-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="8c7c0-128">Estacionamento de chamada e o recebimento de chamadas funcionam com linhas telefônicas privadas exatamente da mesma maneira que funcionam com a linha telefônica principal do usuário.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="8c7c0-129">Quando o toque simultâneo está habilitado na linha telefônica principal de um usuário, ele também é habilitado na linha telefônica privada.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="8c7c0-130">O número de telefone para uma linha telefônica privada é registrado no registro de detalhe de chamada da mesma maneira como o número de telefone para a linha telefônica principal de um usuário, mas com uma indicação de que é um número de telefone privada.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="8c7c0-131">Depois que um usuário respostas que uma chamada em uma linha telefônica privada, a chamada é tratada como uma chamada em uma linha telefônica principal do usuário.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="8c7c0-132">Por exemplo, se um usuário que recebe uma chamada em uma linha telefônica privada encaminha a chamada ou convida outras pessoas a uma chamada em conferência, o nome do usuário aparece no Skype para a empresa e o número de telefone para a linha de telefone principal do usuário aparece no chamador ID.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="8c7c0-133">Um usuário pode desviar uma chamada (redirecionar para outro destino, como um telefone celular ou residencial, antes de atender) a partir da linha telefônica privada da mesma maneira como o faria com uma linha telefônica principal.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8c7c0-134">Quando uma chamada para uma linha privada é roteada para um número de telefone alternativo, o número para a linha telefônica privada é disponibilizado para o número de telefone alternativo e pode ser exibido nos logs para aquele número.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="8c7c0-135">Chamadas de uma conferência para a linha telefônica privada não terão uma indicação de *linha privada* na notificação de sistema de entrada.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="8c7c0-136">Como administrar linhas telefônicas privadas</span><span class="sxs-lookup"><span data-stu-id="8c7c0-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="8c7c0-p107">Além dos aspectos técnicos da criação e gerenciamento de linhas telefônicas privadas, você precisará estabelecer procedimentos administrativos para elas. Isso inclui determinar políticas para quem na organização está elegível para uma linha privada, criar e manter listas de pessoas e suas linhas telefônicas, possivelmente criar um diretório de telefonia privada para executivos, providenciar o treinamento dos usuários e tarefas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8c7c0-p108">A linha telefônica privada é armazenada no Active Directory como um atributo msRTCSIP-PrivateLine no objeto do usuário. Por padrão, qualquer membro do grupo Usuários Autenticados tem acesso de leitura a este atributo.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="8c7c0-141">Como atribuir números de telefone</span><span class="sxs-lookup"><span data-stu-id="8c7c0-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="8c7c0-142">Contas para novos usuários que precisam de linhas telefônicas privadas são criadas da mesma maneira como as contas sem linhas telefônicas privadas, usando Skype para painel de controle de servidor de negócios ou Skype para Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="8c7c0-143">Use o cmdlet **Set-CsUser** no Skype para Business Server Management Shell para atribuir um número de telefone a uma linha telefônica privada para um usuário, por exemplo, **Set-CsUser-Identity "sip:joe@contoso.com" - PrivateLine "Tel: + 14255551212"**.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="8c7c0-144">Números de telefone para linhas telefônicas privadas pode estar entre 3 e 15 números de comprimento e deve ser precedidos com o "TEL:" prefixo.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="8c7c0-145">Podem ter qualquer código de área e qualquer código de país/região, desde que sua organização tenha discagem interna direta para aquele código de área e código de país/região.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="8c7c0-146">Para obter detalhes sobre cmdlets e Skype do Shell de gerenciamento do servidor de negócios, consulte o Skype para obter a documentação do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="8c7c0-147">Linhas telefônicas privadas em implantações mistas</span><span class="sxs-lookup"><span data-stu-id="8c7c0-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="8c7c0-148">Linhas telefônicas privadas devem ser configuradas somente para implantações do Skype para Business Server ou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="8c7c0-149">Em uma implantação no qual há servidores que executam versões anteriores do Lync Server, quando um usuário da versão anterior tenta chamar uma linha telefônica privada, roteamento da chamada falha porque o servidor não pode executar uma pesquisa inversa de números em uma linha telefônica privada.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

