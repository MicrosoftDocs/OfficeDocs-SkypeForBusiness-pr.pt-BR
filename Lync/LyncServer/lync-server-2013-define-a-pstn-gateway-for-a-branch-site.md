---
title: 'Lync Server 2013: definir um gateway PSTN para um site de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ae74ead7eb481a6551156fc0ce228c743fdf1b6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="23280-102">Definir um gateway PSTN para um site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23280-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23280-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="23280-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="23280-104">Execute este procedimento no site central, que contém pelo menos um pool de front-ends ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="23280-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="23280-105">Antes de executar o procedimento, as seguintes condições devem estar presentes:</span><span class="sxs-lookup"><span data-stu-id="23280-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="23280-106">O software de&nbsp;comunicações do Lync Server 2013 deve ser configurado no site central.</span><span class="sxs-lookup"><span data-stu-id="23280-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="23280-107">O servidor de mediação deve ser implantado no site central.</span><span class="sxs-lookup"><span data-stu-id="23280-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="23280-108">Para definir um gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="23280-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="23280-109">Clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server** e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="23280-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="23280-110">Na árvore do console, expanda o site central, expanda **Sites de filial do escritório** e expanda o nome do site da filial para o qual você deseja definir um gateway PSTN (rede telefônica pública comutada) e expanda **Componentes compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="23280-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="23280-111">Clique com o botão direito do mouse em **Gateways PSTN** e clique em **Novo gateway IP/PSTN**.</span><span class="sxs-lookup"><span data-stu-id="23280-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="23280-112">Na caixa de diálogo **Definir novo gateway IP/PSTN**, clique em **FQDN ou endereço IP do gateway** e digite o FQDN ou endereço IP do gateway que você vai implantar na filial.</span><span class="sxs-lookup"><span data-stu-id="23280-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="23280-113">Clique em **Porta de escuta do Gateway IP/PSTN** e aceite os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="23280-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="23280-114">Na lista **Protocolo de Transporte SIP**, clique no protocolo de transporte que o gateway usa e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="23280-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23280-115">Por motivos de segurança, recomendamos que você use um gateway PSTN que oferece suporte à segurança de camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="23280-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="23280-116">Use o cmdlet <STRONG>Set-CsPstnGateway</STRONG> para modificar as propriedades de um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="23280-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="23280-117">Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">set-CsPstnGateway</A>, na ajuda do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23280-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="23280-118">**Próxima etapa** para resiliência de site de filial: [Configurando usuários para resiliência de site de filial no Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="23280-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="23280-119">Confira Também</span><span class="sxs-lookup"><span data-stu-id="23280-119">See Also</span></span>


[<span data-ttu-id="23280-120">Opções de implantação de gateway PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23280-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

