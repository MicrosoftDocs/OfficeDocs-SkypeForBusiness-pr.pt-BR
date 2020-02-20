---
title: 'Lync Server 2013: configurar adaptadores de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd2609c8b8a900b9c970943a2f24bc0462eafb85
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="a5f0c-102">Configurar adaptadores de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5f0c-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5f0c-103">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="a5f0c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="a5f0c-104">Você deve atribuir um ou mais endereços IP ao adaptador de rede externo e pelo menos um endereço IP ao adaptador de rede interno.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="a5f0c-105">Nos procedimentos a seguir, o servidor que executa o Forefront Threat Management Gateway (TMG) 2010 ou o roteamento de solicitação de aplicativo do servidor de informações da Internet tem dois adaptadores de rede:</span><span class="sxs-lookup"><span data-stu-id="a5f0c-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="a5f0c-106">Um adaptador de rede público ou externo, para clientes que tentam se conectar ao seu site (ou seja, geralmente pela Internet).</span><span class="sxs-lookup"><span data-stu-id="a5f0c-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="a5f0c-107">Uma interface de rede privada ou interna, para servidores internos que executam o Lync Server que hospeda serviços Web.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a5f0c-108">Semelhante aos servidores de borda, você define o gateway padrão somente no adaptador de rede externo.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="a5f0c-109">O gateway padrão será o endereço IP do roteador ou do firewall externo voltado para direcionar o tráfego para a Internet.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="a5f0c-110">Para o tráfego destinado do proxy reverso para o adaptador de rede interno, você deve usar rotas estáticas persistentes (como o comando Route no Windows Server) para todas as sub-redes que contêm servidores referenciados pelas regras de publicação da Web.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="a5f0c-111">A definição de uma rota persistente não faz com que o computador se torne um roteador.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="a5f0c-112">Se o encaminhamento de IP não estiver habilitado, o computador estará agindo somente para direcionar o tráfego específico destinado a outra rede para a interface apropriada.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="a5f0c-113">Isso é essencialmente Configurando dois gateways – um como o padrão apontando para as redes externas e outra para o tráfego destinado à interface interna e em um roteador ou outra rede.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="a5f0c-114">No entanto, a criação de rotas persistentes para todas as sub-redes pode não ser necessária se os roteadores da rede estiverem configurados para resumir as rotas.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-114">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes.</span></span> <span data-ttu-id="a5f0c-115">Criar uma rota persistente para a rede onde o roteador está definido e usar o roteador como o gateway padrão.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-115">Create a persistent route to the network where the router is defined and use the router as the default gateway.</span></span> <span data-ttu-id="a5f0c-116">Se você não tiver certeza de que sua rede está configurada e precisa de orientação sobre quais rotas persistentes precisam ser criadas, consulte os engenheiros de rede da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-116">If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="a5f0c-117">O proxy reverso deve ser capaz de resolver os registros de host DNS (A) para o diretor interno ou servidor front-end e FQDNs do pool de próximo salto usados nas regras de publicação da Web.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="a5f0c-118">Como nos servidores de borda, por motivos de segurança, recomendamos que você não configure um proxy reverso para usar um servidor DNS localizado na rede interna.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="a5f0c-119">Isso significa que você precisa dos servidores DNS no perímetro ou precisa de entradas de arquivo HOSTs no proxy reverso que resolva cada um desses FQDNs para o endereço IP interno dos servidores.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="a5f0c-120">Para configurar as placas adaptadoras de rede no computador proxy reverso</span><span class="sxs-lookup"><span data-stu-id="a5f0c-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="a5f0c-121">No servidor Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2 em execução como proxy reverso, clique em \*\*\*\* **Iniciar**, aponte para **painel de controle**, clique em **centro de rede e compartilhamento**e, em seguida, clique em **alterar as configurações do adaptador**.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="a5f0c-122">Clique com o botão direito do mouse na conexão de rede externa que você deseja usar para a interface externa e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="a5f0c-123">Na página **Propriedades** , clique na guia **rede** , clique em **protocolo TCP/IP versão 4 (TCP/IPv4)** na lista **esta conexão usa os seguintes itens** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="a5f0c-124">Na página **Propriedades do protocolo TCP/IP** , configure os endereços IP conforme apropriado para a sub-rede de rede à qual o adaptador de rede está conectado.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a5f0c-125">Se o proxy reverso já estiver sendo usado por outros aplicativos que usam HTTPS/TCP/443, por exemplo, para publicar o Outlook Web Access, é necessário adicionar outro endereço IP para que você possa publicar os serviços Web do Lync Server 2013 em HTTPS/TCP/443 sem interferir nas regras existentes e ouvintes da Web, ou você precisa substituir o certificado existente por um que adicione os novos nomes de FQDN externos ao nome alternativo da entidade.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="a5f0c-126">Clique em **OK**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="a5f0c-127">Em **conexões de rede**, clique com o botão direito do mouse na conexão de rede interna que você deseja usar para a interface interna e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="a5f0c-128">Repita as etapas de 3 a 5 para configurar a conexão de rede interna.</span><span class="sxs-lookup"><span data-stu-id="a5f0c-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

