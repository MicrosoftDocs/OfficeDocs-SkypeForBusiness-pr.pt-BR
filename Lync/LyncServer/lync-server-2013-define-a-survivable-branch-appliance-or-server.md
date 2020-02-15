---
title: 'Lync Server 2013: definir um servidor ou aparelho de filial persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9006aa3a54a2aa38cecb4b49ef56094eb24494fc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="33872-102">Definir um servidor ou aparelho de filial persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33872-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33872-103">_**Última modificação do tópico:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="33872-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="33872-104">Execute este procedimento no local central caso não tenha definido o Servidor ou o Aparelho de Filial Persistente quando o adicionou à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="33872-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="33872-105">Para definir um aparelho de filial persistente ou servidor de filial persistente</span><span class="sxs-lookup"><span data-stu-id="33872-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="33872-106">Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="33872-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="33872-107">Na árvore do console, expanda o site central, expanda **sites de filial**e, em seguida, expanda o nome do site de filial onde você planeja implantar o aparelho de filial persistente ou servidor de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="33872-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="33872-108">Clique com o botão direito em **aparelhos de filial persistente**e, em seguida, clique em **novo aparelho de filial persistente**.</span><span class="sxs-lookup"><span data-stu-id="33872-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="33872-109"><STRONG>Aparelhos de filial persistentes</STRONG> é onde você define servidores de filial persistente e aparelhos de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="33872-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="33872-110">Na caixa de diálogo **definir aparelho de filial persistente** , clique em **FQDN**, digite o FQDN (nome de domínio totalmente qualificado) do aparelho de filial persistente ou servidor de filial persistente que você irá implantar neste site de filial e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="33872-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="33872-111">Se você estiver definindo um aparelho de filial persistente, o nome inserido no <STRONG>FQDN</STRONG> deve ser o mesmo que o FQDN do aparelho de filial persistente que você atribuiu ao atributo <STRONG>servicePrincipalName</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="33872-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="33872-112">Para obter detalhes, consulte <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Adicionar um aparelho de filial persistente ao Active Directory no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="33872-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="33872-113">Clique em **pool de front-ends**, clique no servidor de front-end (pool de serviços de usuário) no site central ao qual esse aparelho de filial persistente ou servidor de filial persistente se conectará e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="33872-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="33872-114">Clique em **servidor de borda**, clique no pool de borda que esse aparelho de filial persistente ou servidor de filial persistente se conectará para fornecer conectividade PSTN aos usuários remotos do site de filial e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="33872-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="33872-115">Clique em **FQDN de gateway ou endereço IP**e, em seguida, digite o FQDN ou endereço IP do ponto de gateway que o aparelho de filial persistente ou servidor de filial persistente está associado para rotear chamadas PSTN de entrada ou saída.</span><span class="sxs-lookup"><span data-stu-id="33872-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="33872-116">Se você está definindo um Aparelho de Filial Persistente, este é o gateway ao qual o Servidor de Mediação dentro do Aparelho de Filial Persistente se conectará para obter conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="33872-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="33872-117">Clique em **Porta de Escuta para Gateway de IP/PSTN** e aceite a porta padrão.</span><span class="sxs-lookup"><span data-stu-id="33872-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="33872-118">No **protocolo de transporte SIP**, clique no protocolo de transporte que o aparelho de filial persistente ou servidor de filial persistente usará e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="33872-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33872-119">Por motivos de segurança, recomendamos que você use o TLS.</span><span class="sxs-lookup"><span data-stu-id="33872-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="33872-120">Caso esteja definindo um Aparelho de Filial Persistente, consulte sua documentação do fornecedor do Aparelho de Filial Persistente para verificar se o seu Aparelho de Filial Persistente é compatível com protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="33872-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="33872-121">Na árvore do console, clique com o botão direito no novo Aparelho ou Servidorde Filial Persistente, clique em **Topologia** e em **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="33872-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="33872-122">**Próxima etapa**: [implantar um servidor ou aparelho de filial persistente com o Lync Server 2013-tarefa do site de filial](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="33872-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

