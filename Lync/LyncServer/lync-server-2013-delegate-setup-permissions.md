---
title: 'Lync Server 2013: delegar permissões de configuração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453da166895c79cafe9f9637163e93a63ebccd75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504278"
---
# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="36636-102">Delegar permissões de configuração no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36636-102">Delegate setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36636-103">_**Última modificação do tópico:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="36636-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="36636-104">Se não quiser conceder a associação ao grupo Administradores de domínio para usuários ou grupos que estão implantando o Lync Server 2013, você pode habilitar os membros do grupo RTCUniversalServerAdmins para executar o cmdlet **Enable-CsTopology**   do Windows PowerShell em servidores que executam o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36636-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="36636-105">Por padrão, os membros do grupo RTCUniversalServerAdmins não podem executar esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="36636-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="36636-106">Conceda permissões e direitos de administrador para executar **Enable-CsTopology** em servidores que executam o Lync Server usando o cmdlet **Grant-CsSetupPermission** e especificando uma UO (unidade organizacional) onde os objetos de computador do servidor que executa o Lync Server 2013 estão localizados.</span><span class="sxs-lookup"><span data-stu-id="36636-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="36636-107">A preparação do domínio que ocorre quando você instala o Lync Server não adiciona automaticamente as permissões que permitem que os membros do grupo RTCUniversalServerAdmins executem o cmdlet Enable-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="36636-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="36636-108">Isso significa que, por padrão, é necessário que você seja um administrador do domínio para poder habilitar uma topologia.</span><span class="sxs-lookup"><span data-stu-id="36636-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="36636-109">Para dar aos membros do grupo RTCUniversalServerAdmins o direito de habilitar uma topologia, você deve executar o cmdlet Grant-CsSetupPermissions.</span><span class="sxs-lookup"><span data-stu-id="36636-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="36636-110">Além disso, você precisará executar esse cmdlet em cada contêiner do Active Directory que hospeda computadores que executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="36636-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="36636-111">Tenha em mente que esse cmdlet apenas concede permissões ao grupo RTCUniversalServerAdmins; ele não pode ser utilizado para conceder permissões aos grupos de segurança ou a usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="36636-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36636-112"><STRONG>Enable-CsTopology</STRONG> é o cmdlet principal para permitir que os membros do grupo RTCUniversalServerAdmins configurem e implantem o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36636-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="36636-113">Para adicionar a habilidade de executar o cmdlet Enable-CsTopology ao grupo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="36636-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="36636-114">Faça logon em um servidor como membro do grupo Administradores de Domínio para o domínio em que o usuário delegado executará o cmdlet **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="36636-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="36636-115">Abra o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36636-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="36636-116">O Shell de gerenciamento do Lync Server 2013 é instalado automaticamente em cada servidor de front-end ou em qualquer computador onde as ferramentas administrativas do Lync Server 2013 tenham sido instaladas.</span><span class="sxs-lookup"><span data-stu-id="36636-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="36636-117">Para obter detalhes sobre o Shell de gerenciamento do Lync Server 2013, consulte [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="36636-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="36636-118">Execute o seguinte cmdlet no Shell de gerenciamento do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="36636-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="36636-119">Se OU não for o nível superior, você deve fornecer o nome de domínio completo.</span><span class="sxs-lookup"><span data-stu-id="36636-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="36636-120">No exemplo a seguir, a UO é o "Lync Server", que está no domínio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="36636-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

