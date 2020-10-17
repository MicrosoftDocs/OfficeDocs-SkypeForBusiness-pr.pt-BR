---
title: 'Lync Server 2013: Configurando seu ambiente para o portal da Web administrativo do sistema de salas do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea3269b9594df0597220648313ec79acfa329cf9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502098"
---
# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="5cb58-102">Configurando seu ambiente do Lync Server 2013 para o portal da Web administrativo do sistema de salas do Lync</span><span class="sxs-lookup"><span data-stu-id="5cb58-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cb58-103">_**Última modificação do tópico:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="5cb58-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="5cb58-104">Para usar o portal da Web administrativo do sistema de salas do Lync (LRS), será necessário instalar ou configurar os pré-requisitos a seguir.</span><span class="sxs-lookup"><span data-stu-id="5cb58-104">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5cb58-105">Se o servidor estiver configurado com autenticação Kerberos e NTLM e o LRS estiver em execução em um computador que não ingressou no domínio, a autenticação Kerberos falhará e o usuário não verá o status de LRS no portal administrativo.</span><span class="sxs-lookup"><span data-stu-id="5cb58-105">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="5cb58-106">Para resolver esse problema, configure o servidor com autenticação NTLM ou autenticação NTLM e TLS-DSK (sem Kerberos) ou Ingresse o computador do LRS no domínio.</span><span class="sxs-lookup"><span data-stu-id="5cb58-106">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="5cb58-107">Instale as atualizações cumulativas do Lync Server 2013:2013 de julho na topologia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5cb58-107">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="5cb58-108">Para obter a atualização ou ver o que está incluído nele, consulte [atualizações para o Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).</span><span class="sxs-lookup"><span data-stu-id="5cb58-108">To get the update or see what’s included with it, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="5cb58-109">Criar um usuário do Active Directory habilitado para SIP.</span><span class="sxs-lookup"><span data-stu-id="5cb58-109">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="5cb58-110">O portal da Web administrativo do LRS usa essas credenciais para consultar informações do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5cb58-110">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="5cb58-111">O nome de usuário recomendado é LRSApp.</span><span class="sxs-lookup"><span data-stu-id="5cb58-111">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="5cb58-112">Crie um grupo de segurança do Active Directory com o nome LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="5cb58-112">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="5cb58-113">Crie o grupo com o escopo de grupo como segurança global e tipo de grupo como segurança.</span><span class="sxs-lookup"><span data-stu-id="5cb58-113">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="5cb58-114">Os usuários habilitados para SIP que forem adicionados a esse grupo serão autorizados a ver a lista de salas e executar certos comandos, como coletar logs.</span><span class="sxs-lookup"><span data-stu-id="5cb58-114">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="5cb58-115">Crie um grupo de segurança do Active Directory com o nome LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="5cb58-115">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="5cb58-116">Criar o grupo com o escopo de grupo como global e o tipo de grupo como Security. SIP habilitados para usuários que são adicionados a este grupo são autorizados a usar toda a funcionalidade do portal de administração.</span><span class="sxs-lookup"><span data-stu-id="5cb58-116">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="5cb58-117">![Lista de grupos de administração com a função de grupo de segurança](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Lista de grupos de administração com a função de grupo de segurança")</span><span class="sxs-lookup"><span data-stu-id="5cb58-117">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="5cb58-118">Adicione LRSFullAccessAdminGroup como membro de LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="5cb58-118">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="5cb58-119">![Página Membros de propriedades LRSSupportAdminGroup](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Página Membros de propriedades LRSSupportAdminGroup")</span><span class="sxs-lookup"><span data-stu-id="5cb58-119">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="5cb58-120">Crie um usuário do Active Directory habilitado para SIP com o nome LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="5cb58-120">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="5cb58-121">Adicione este usuário ao LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="5cb58-121">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="5cb58-122">![Página Membros de propriedades LRSSupportAdminGroup](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Página Membros de propriedades LRSSupportAdminGroup")</span><span class="sxs-lookup"><span data-stu-id="5cb58-122">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="5cb58-123">Instale o ASP.NET MVC 4 para o Visual Studio 2010 SP1 e o Visual Web Developer 2010 SP1, disponível no centro de download da Microsoft em [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967) .</span><span class="sxs-lookup"><span data-stu-id="5cb58-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

