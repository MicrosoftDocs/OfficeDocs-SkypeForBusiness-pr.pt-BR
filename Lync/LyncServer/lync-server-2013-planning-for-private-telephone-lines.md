---
title: 'Lync Server 2013: planejamento para linhas telefônicas privadas'
description: 'Lync Server 2013: planejamento para linhas telefônicas privadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 120c1804bc3ce58e8746f68cbda9c66f02568ccb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549307"
---
# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a><span data-ttu-id="7a8c5-103">Planejamento de linhas telefônicas privadas com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a8c5-103">Planning for private telephone lines with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a8c5-104">_**Última modificação do tópico:** 2013-02-11_</span><span class="sxs-lookup"><span data-stu-id="7a8c5-104">_**Topic Last Modified:** 2013-02-11_</span></span>

<span data-ttu-id="7a8c5-105">O Lync Server 2013 introduz a capacidade de fornecer aos usuários uma segunda linha telefônica privada, além da linha telefônica principal.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-105">Lync Server 2013 introduces the ability to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="7a8c5-106">Linhas telefônicas privadas são frequentemente atribuídas a executivos e a outras pessoas que desejam um número de telefone não esteja listado e através do qual podem ser diretamente contatados.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>

<span data-ttu-id="7a8c5-107">As linhas telefônicas privadas só podem ser configuradas com o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-107">Private telephone lines can only be configured with the Lync Server Management Shell.</span></span> <span data-ttu-id="7a8c5-108">Você não pode configurar linhas telefônicas privadas com o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-108">You cannot configure private telephone lines with the Lync Server Control Panel.</span></span> <span data-ttu-id="7a8c5-109">As linhas telefônicas privadas devem ser configuradas somente em implantações do Lync Server e não em implantações mistas.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-109">Private telephone lines should be configured only in deployments of Lync Server and not in mixed deployments.</span></span>

<div>

## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="7a8c5-110">Características das linhas telefônicas privadas</span><span class="sxs-lookup"><span data-stu-id="7a8c5-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="7a8c5-111">Embora o conceito de uma linha telefônica privada, secundária, seja fundamentalmente simples, é importante compreender as características das linhas privadas e as formas em que são similares e diferentes das linhas telefônicas principais dos usuários.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users’ primary telephone lines.</span></span>

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="7a8c5-112">Características gerais das linhas telefônicas privadas</span><span class="sxs-lookup"><span data-stu-id="7a8c5-112">General Characteristics of Private Telephone Lines</span></span>

  - <span data-ttu-id="7a8c5-113">Um usuário pode ter somente uma linha telefônica privada.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-113">A user can have only one private telephone line.</span></span>

  - <span data-ttu-id="7a8c5-114">Um usuário com uma linha telefônica privada só possui uma caixa postal e recebe notificações de chamadas perdidas em um único endereço de e-mail.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>

  - <span data-ttu-id="7a8c5-115">Um usuário com uma linha telefônica privada não possui um segundo endereço SIP e uma linha telefônica privada secundária não dá a ele uma segunda presença na rede (como uma segunda identidade no sistema de mensagens instantâneas).</span><span class="sxs-lookup"><span data-stu-id="7a8c5-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span>

  - <span data-ttu-id="7a8c5-116">Linhas telefônicas privadas estão disponíveis somente para implantações locais.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="7a8c5-117">Eles não estão disponíveis com implantações hospedadas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-117">They are not available with hosted deployments of Lync Server.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="7a8c5-118">Como linhas telefônicas privadas diferem de linhas telefônicas principais</span><span class="sxs-lookup"><span data-stu-id="7a8c5-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

  - <span data-ttu-id="7a8c5-119">Os números de telefone para linhas telefônicas privadas não aparecem nos diretórios telefônicos ou listas de Contatos derivados dos Serviços de Domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="7a8c5-120">Nenhum dos recursos a seguir está disponível com uma linha telefônica privada: encaminhamento de chamadas, chamada de equipe, delegação, toque de equipe, recebimento de chamadas de grupo e aplicativo de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>

  - <span data-ttu-id="7a8c5-121">Chamadas para uma linha telefônica privada possuem um toque especial e a notificação do sistema para as chamadas diz ao usuário que a chamada de entrada está em sua linha privada.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>

  - <span data-ttu-id="7a8c5-p104">Chamadas para a linha telefônica privada sempre tocam. Elas não seguem as regras "não incomodar".</span><span class="sxs-lookup"><span data-stu-id="7a8c5-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>

  - <span data-ttu-id="7a8c5-p105">Linhas telefônicas privadas são somente de entrada e não podem ser usadas para fazer chamadas de saída. Quando um usuário com uma linha telefônica privada faz uma ligação, a chamada é originada na linha telefônica principal e não oculta do receptor da chamada o nome ou o número de telefone principal do usuário.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-p105">Private telephone lines are inbound only and cannot be used to make outgoing calls. When a user with a private telephone line makes a call, the call originates from the user’s primary telephone line and does not hide the user’s name or the user’s primary telephone number from the person called.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="7a8c5-126">Como linhas telefônicas privadas são similares a linhas telefônicas principais</span><span class="sxs-lookup"><span data-stu-id="7a8c5-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

  - <span data-ttu-id="7a8c5-127">Chamadas não atendidas para uma linha telefônica privada são roteadas para a mesma caixa postal da linha telefônica principal (se a caixa postal estiver habilitada).</span><span class="sxs-lookup"><span data-stu-id="7a8c5-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>

  - <span data-ttu-id="7a8c5-128">O estacionamento e o recebimento de chamadas funcionam com linhas telefônicas privadas exatamente da mesma forma como na linha telefônica principal do usuário.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user’s primary telephone line.</span></span>

  - <span data-ttu-id="7a8c5-129">Quando o toque simultâneo está habilitado na linha telefônica principal de um usuário, também está habilitado na linha telefônica privada.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-129">When simultaneous ringing is enabled on a user’s primary telephone line, it is also enabled on the private telephone line.</span></span>

  - <span data-ttu-id="7a8c5-130">O número de telefone para uma linha telefônica privada é gravado no registro de detalhes de chamada da mesma maneira que o número de telefone para a linha telefônica principal de um usuário, mas com uma indicação de que é um número telefônico privado.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user’s primary telephone line, but with an indication that it is a private telephone number.</span></span>

  - <span data-ttu-id="7a8c5-131">Depois que o usuário atende uma chamada na linha telefônica privada, ela é tratada da mesma forma como se estivesse na linha telefônica principal.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user’s primary telephone line.</span></span> <span data-ttu-id="7a8c5-132">Por exemplo, se um usuário que recebe uma chamada em uma linha telefônica privada encaminha a chamada ou convida outras pessoas para uma chamada em conferência, o nome do usuário aparece no Lync 2013, e o número de telefone da linha telefônica principal do usuário aparece na ID do chamador.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user’s name appears in Lync 2013, and the telephone number for the user’s primary telephone line appears in caller ID.</span></span>

  - <span data-ttu-id="7a8c5-133">Um usuário pode desviar uma chamada (redirecionar para outro destino, como um telefone celular ou residencial, antes de atender) a partir da linha telefônica privada da mesma maneira como o faria com uma linha telefônica principal.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a8c5-134">Quando uma chamada para uma linha privada é roteada para um número de telefone alternativo, o número para a linha telefônica privada é disponibilizado para o número de telefone alternativo e pode ser exibido nos logs para aquele número.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a8c5-135">Chamadas a partir de uma conferência para a linha telefônica privada não terão uma indicação de <EM>linha privada</EM> na notificação do sistema de entrada.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-135">Calls from a conference to the private telephone line will not have a <EM>private-line</EM> indication in the incoming system notification.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a><span data-ttu-id="7a8c5-136">Como administrar linhas telefônicas privadas</span><span class="sxs-lookup"><span data-stu-id="7a8c5-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="7a8c5-p107">Além dos aspectos técnicos da criação e gerenciamento de linhas telefônicas privadas, você precisará estabelecer procedimentos administrativos para elas. Isso inclui determinar políticas para quem na organização está elegível para uma linha privada, criar e manter listas de pessoas e suas linhas telefônicas, possivelmente criar um diretório de telefonia privada para executivos, providenciar o treinamento dos usuários e tarefas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a8c5-p108">A linha telefônica privada é armazenada no Active Directory como um atributo msRTCSIP-PrivateLine no objeto do usuário. Por padrão, qualquer membro do grupo Usuários Autenticados tem acesso de leitura a este atributo.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span>



</div>

<div>

## <a name="assigning-telephone-numbers"></a><span data-ttu-id="7a8c5-141">Como atribuir números de telefone</span><span class="sxs-lookup"><span data-stu-id="7a8c5-141">Assigning Telephone Numbers</span></span>

<span data-ttu-id="7a8c5-142">As contas para novos usuários que precisam de linhas telefônicas privadas são criadas da mesma maneira que as contas sem linhas telefônicas privadas, usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<span data-ttu-id="7a8c5-143">Use o cmdlet **set-CsUser** no Shell de gerenciamento do Lync Server para atribuir um número de telefone a uma linha telefônica privada para um usuário, por exemplo, **set-CsUser-Identity "SIP:Joe@contoso.com"-Private "Tel: + 14255551212"**.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-143">Use the **Set-CsUser** cmdlet in the Lync Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>

<span data-ttu-id="7a8c5-144">Números de telefone para linhas telefônicas privadas podem ter entre 3 e 15 números por comprimento e devem ser precedidos com o prefixo "TEL:".</span><span class="sxs-lookup"><span data-stu-id="7a8c5-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="7a8c5-145">Podem ter qualquer código de área e qualquer código de país/região, desde que sua organização tenha discagem interna direta para aquele código de área e código de país/região.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span>

<span data-ttu-id="7a8c5-146">Para obter detalhes sobre cmdlets e o Shell de gerenciamento do Lync Server, consulte a documentação do [Shell de gerenciamento do Lync server 2013](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="7a8c5-146">For details about cmdlets and Lync Server Management Shell, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="7a8c5-147">Linhas telefônicas privadas em implantações mistas</span><span class="sxs-lookup"><span data-stu-id="7a8c5-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="7a8c5-148">As linhas telefônicas privadas devem ser configuradas apenas para implantações do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-148">Private telephone lines should be configured only for deployments of Lync Server.</span></span> <span data-ttu-id="7a8c5-149">Em uma implantação na qual existem os servidores Lync Server e Office Communications Server 2007 ou Office Communications Server 2007 R2, quando um usuário em uma versão anterior tenta chamar uma linha telefônica privada, o roteamento da chamada falha porque o servidor não pode executar uma pesquisa de número reverso em uma linha telefônica privada.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-149">In a deployment in which there are both Lync Server and Office Communications Server 2007 or Office Communications Server 2007 R2 servers, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

