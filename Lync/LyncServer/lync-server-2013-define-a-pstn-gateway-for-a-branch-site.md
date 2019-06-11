---
title: 'Lync Server 2013: Definir um gateway de PSTN para um site de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c253f82001fef4dd52e19dccb11e7ac77bb12417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="9eeb0-102">Definir um gateway de PSTN para um site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9eeb0-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9eeb0-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9eeb0-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9eeb0-104">Execute este procedimento no site central, que contém pelo menos um pool de front-end ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9eeb0-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9eeb0-105">Antes de executar o procedimento, as seguintes condições devem estar em vigor:</span><span class="sxs-lookup"><span data-stu-id="9eeb0-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="9eeb0-106">O software de&nbsp;comunicação do Lync Server 2013 deve ser configurado no site central.</span><span class="sxs-lookup"><span data-stu-id="9eeb0-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="9eeb0-107">O servidor de mediação deve ser implantado no site central.</span><span class="sxs-lookup"><span data-stu-id="9eeb0-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="9eeb0-108">Para definir um gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="9eeb0-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="9eeb0-109">Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server**e, em seguida, clique em **Construtor de topologia do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9eeb0-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="9eeb0-110">Na árvore de console, expanda o site central, expanda **sites**de filiais, expanda o nome do site de filial para o qual você deseja definir um gateway PSTN (rede telefônica pública comutada) para e, em seguida, expanda **componentes compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="9eeb0-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="9eeb0-111">Clique com o botão direito do mouse em **gateways PSTN**e clique em **novo gateway IP/PSTN**.</span><span class="sxs-lookup"><span data-stu-id="9eeb0-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="9eeb0-112">Na caixa de diálogo **definir novo gateway IP/PSTN** , clique em **endereço IP ou FQDN do gateway**e digite o nome de domínio totalmente qualificado (FQDN) ou o endereço IP do gateway que você está implantando no site da filial.</span><span class="sxs-lookup"><span data-stu-id="9eeb0-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="9eeb0-113">Clique em **porta de escuta do gateway IP/PSTN**e aceite os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="9eeb0-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="9eeb0-114">Na lista **protocolo de transporte SIP** , clique no protocolo de transporte usado pelo gateway e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9eeb0-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9eeb0-115">Por motivos de segurança, recomendamos enfaticamente que você use um gateway PSTN compatível com TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="9eeb0-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="9eeb0-116">Use o cmdlet <STRONG>set-CsPstnGateway</STRONG> para modificar as propriedades de um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="9eeb0-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="9eeb0-117">Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">set-CsPstnGateway</A>na ajuda do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9eeb0-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="9eeb0-118">**Próxima etapa** para resiliência no local da filial: [Configurando usuários para resiliência de site de ramificação no Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="9eeb0-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9eeb0-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="9eeb0-119">See Also</span></span>


[<span data-ttu-id="9eeb0-120">Opções de implantação do gateway PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9eeb0-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

