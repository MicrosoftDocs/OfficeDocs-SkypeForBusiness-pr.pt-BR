---
title: 'Lync Server 2013: Definir um Servidor ou Aparelho de Filial Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dadaa26f6a951995906ed29ffd0615da16066928
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="aa564-102">Definir um Servidor ou Aparelho de Filial Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa564-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa564-103">_**Tópico da última modificação:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="aa564-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="aa564-104">Execute este procedimento no site central se você não definiu o aplicativo ou o aplicativo da ramificação sobreviventes quando o adicionou à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="aa564-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="aa564-105">Para definir um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes</span><span class="sxs-lookup"><span data-stu-id="aa564-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="aa564-106">Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="aa564-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="aa564-107">Na árvore de console, expanda o site central, expanda **sites**de ramificação e, em seguida, expanda o nome do site de ramificação no qual você planeja implantar o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="aa564-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="aa564-108">Clique com o botão direito do mouse em **aparelhos de ramificação sobreviventes**e clique em **novo aplicativo de ramificação sobreviventes**.</span><span class="sxs-lookup"><span data-stu-id="aa564-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aa564-109"><STRONG>Aparelhos de ramificação sobreviventes</STRONG> é onde você define servidores de ramificação sobreviventes e aparelhos de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="aa564-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="aa564-110">Na caixa de diálogo **definir equipamento de ramificação sobreviventes** , clique em **FQDN**, digite o nome de domínio totalmente qualificado (FQDN) da ferramenta de ramificação sobreviventes ou do servidor de ramificação sobreviventes que você irá implantar nesse site de filial e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="aa564-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aa564-111">Se você estiver definindo um aparelho de ramificação sobreviventes, o nome que você inserir no <STRONG>FQDN</STRONG> deve ser o mesmo que o FQDN do aparelho de ramificação sobreviventes atribuído ao atributo <STRONG>servicePrincipalName</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="aa564-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="aa564-112">Para obter detalhes, consulte <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Adicionar um aparelho de ramificação sobreviventes ao Active Directory no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aa564-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="aa564-113">Clique em **pool de front-end**, clique no servidor front-end (pool de serviços do usuário) no site central em que esse aparelho de ramificação de persistência ou o servidor de ramificação sobreviventes se conectará e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="aa564-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="aa564-114">Clique em **servidor de borda**, clique no pool de bordas em que esse aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes se conectará para fornecer conectividade PSTN a usuários remotos do site de filial e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="aa564-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="aa564-115">Clique em **endereço IP ou FQDN do gateway**e, em seguida, digite o FQDN ou endereço IP do par de gateways que o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes está associado para chamadas PSTN de entrada ou de saída.</span><span class="sxs-lookup"><span data-stu-id="aa564-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aa564-116">Se você estiver definindo um aparelho de ramificação sobreviventes, esse é o gateway ao qual o servidor de mediação dentro da ramificação de ramificação sobreviventes se conectará para conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="aa564-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="aa564-117">Clique em **porta de escuta do gateway IP/PSTN**e aceite a porta padrão.</span><span class="sxs-lookup"><span data-stu-id="aa564-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="aa564-118">Em **protocolo de transporte SIP**, clique no protocolo de transporte o aplicativo de ramificação sobreviventes ou o servidor de ramificação sobreviventes será usado e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="aa564-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa564-119">Por motivos de segurança, recomendamos enfaticamente que você use Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="aa564-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="aa564-120">Se você estiver definindo um aparelho de ramificação sobreviventes, confira a documentação do fornecedor da sua agência de ramificação sobreviventes para verificar se o seu aparelho de ramificação sobreviventes é compatível com o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="aa564-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="aa564-121">Na árvore do console, clique com o botão direito do mouse no novo aplicativo ou aplicativo da ramificação sobreviventes, clique em **topologia**e, em seguida, clique em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="aa564-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="aa564-122">**Próxima etapa**: [implantar um aplicativo ou um aplicativo de ramificação sobreviventes com o Lync Server 2013-tarefa do site de ramificação](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="aa564-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

