---
title: 'Lync Server 2013: Configurando servidores de proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 640d8e97cf8b7a31e11cb2dc8f1b1394e4b1aae3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521808"
---
# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a><span data-ttu-id="0d2ff-102">Configurando servidores de proxy reverso para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d2ff-102">Setting up reverse proxy servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d2ff-103">_**Última modificação do tópico:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="0d2ff-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="0d2ff-104">Para implantações do servidor de borda do Microsoft Lync Server 2013, um proxy reverso HTTPS na rede de perímetro é necessário para que clientes externos acessem os serviços Web do Lync Server 2013 (chamados de *componentes da Web* no Office Communications Server) no diretor e o pool de casa do usuário.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-104">For Microsoft Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for external clients to access the Lync Server 2013 Web Services (called *Web Components* in Office Communications Server) on the Director and the user’s home pool.</span></span> <span data-ttu-id="0d2ff-105">Veja abaixo alguns dos recursos que exigem acesso externo por meio de proxy reverso:</span><span class="sxs-lookup"><span data-stu-id="0d2ff-105">Some of the features that require external access through a reverse proxy include the following:</span></span>

  - <span data-ttu-id="0d2ff-106">Permitir que usuários externos baixem o conteúdo de reunião para suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-106">Enabling external users to download meeting content for your meetings.</span></span>

  - <span data-ttu-id="0d2ff-107">Permitir que usuários externos expandam grupos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-107">Enabling external users to expand distribution groups.</span></span>

  - <span data-ttu-id="0d2ff-108">Permitir que usuários remotos baixem arquivos do serviço de Catálogo de Endereços.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-108">Enabling remote users to download files from the Address Book service.</span></span>

  - <span data-ttu-id="0d2ff-109">Acessar o cliente Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-109">Accessing the Lync Web App client.</span></span>

  - <span data-ttu-id="0d2ff-110">Acessar a página da web de Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-110">Accessing the Dial-in Conferencing Settings webpage.</span></span>

  - <span data-ttu-id="0d2ff-111">Permitir que dispositivos externos se conectem ao serviço web de Atualização de Dispositivo e obtenham atualizações.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-111">Enabling external devices to connect to Device Update web service and obtain updates.</span></span>

  - <span data-ttu-id="0d2ff-112">Permitir que aplicativos móveis descubram e usem automaticamente as URLs de mobilidade (MCX) a partir da Internet.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-112">Enabling mobile applications to automatically discover and use the mobility (Mcx) URLs from the Internet.</span></span>

  - <span data-ttu-id="0d2ff-113">Habilitando o cliente do Lync 2013, o aplicativo Lync Windows Store e o cliente móvel do Lync 2013 para localizar as URLs de descoberta do Lync (descoberta automática) e usar o UCWA (Unified Communications Web API).</span><span class="sxs-lookup"><span data-stu-id="0d2ff-113">Enabling the Lync 2013 client, Lync Windows Store app and Lync 2013 Mobile client to locate the Lync Discover (autodiscover) URLs and use Unified Communications Web API (UCWA).</span></span>

<span data-ttu-id="0d2ff-114">Recomendamos que configure seu proxy reverso HTTP para publicar todos os Serviços Web em todos os pools.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-114">We recommend that you configure your HTTP reverse proxy to publish all Web Services in all pools.</span></span> <span data-ttu-id="0d2ff-115">Publishing https://ExternalFQDN/ \* publica todos os diretórios virtuais do IIS para um pool.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-115">Publishing https:// ExternalFQDN/\* publishes all IIS virtual directories for a pool.</span></span> <span data-ttu-id="0d2ff-116">Você precisa de uma regra de publicação para cada servidor Standard Edition, pool de Front-Ends ou Diretores, ou Diretores em sua organização.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-116">You need one publishing rule for each Standard Edition server, Front End pool, or Director or Director pool in your organization.</span></span>

<span data-ttu-id="0d2ff-117">Além disso, você precisa publicar as URLs simples.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-117">In addition, you need to publish the simple URLs.</span></span> <span data-ttu-id="0d2ff-118">Caso a organização possua um Diretor ou pool de Diretores, o proxy reverso HTTP escuta por solicitações HTTP/HTTPS às URLs simples e as encaminha via proxy ao diretório virtual de Serviços Web externos no Diretor  ou pool de Diretores.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-118">If the organization has a Director or Director pool, the HTTP reverse proxy listens for HTTP/HTTPS requests to the simple URLs and proxies them to the external Web Services virtual directory on the Director or Director pool.</span></span> <span data-ttu-id="0d2ff-119">Caso você não tenha implantado um diretor, você precisará designar um pool para manipular as solicitações às URLs simples.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-119">If you have not deployed a Director, you need to designate one pool to handle requests to the simple URLs.</span></span> <span data-ttu-id="0d2ff-120">(Caso este não seja o pool inicial do usuário, ele irá redirecioná-los para o Serviços Web no pool inicial do usuário).</span><span class="sxs-lookup"><span data-stu-id="0d2ff-120">(If this is not the user’s home pool, it will redirect them onward to the Web Services on the user’s home pool).</span></span> <span data-ttu-id="0d2ff-121">As URLs simples podem ser manipuladas por uma regra de publicação de web dedicada ou você pode adicioná-la aos nomes públicos da regra de publicação de web para o Diretor.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-121">The simple URLs can be handled by a dedicated web publishing rule, or you can add it to the public names of the web publishing rule for the Director.</span></span> <span data-ttu-id="0d2ff-122">Você também precisa publicar a URL externa do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-122">You also need to publish the external Autodiscover Service URL.</span></span>

<span data-ttu-id="0d2ff-123">Você pode usar o Microsoft Forefront Threat Management Gateway 2010, o Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 ou o Internet Information Server 7,0, 7,5 ou 8,0 com o serviço de roteamento de solicitação de aplicativo (IIS ARR) como um proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-123">You can use Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, or Internet Information Server 7.0, 7.5 or 8.0 with Application Request Routing (IIS ARR) as a reverse proxy.</span></span> <span data-ttu-id="0d2ff-124">As etapas detalhadas nesta seção descrevem como configurar o Forefront Threat Management Gateway (TMG) 2010 e as etapas para configurar o ISA Server 2006 são quase idênticas.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-124">The detailed steps in this section describe how to configure Forefront Threat Management Gateway 2010, and the steps for configuring ISA Server 2006 are almost identical.</span></span> <span data-ttu-id="0d2ff-125">As orientações também são fornecidas para o IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-125">Guidance is also provided for IIS ARR.</span></span> <span data-ttu-id="0d2ff-126">Se você estiver usando outro proxy reverso, consulte a documentação do produto e mapeie os requisitos definidos aqui para os recursos associados em outros proxies reversos.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-126">If you are using a different reverse proxy, consult the documentation for that product and map the requirements defined here to the associated features in other reverse proxies.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0d2ff-127">Serviço de roteamento de solicitação de aplicativo do Internet Information Server (IIS ARR) é uma opção totalmente testada e com suporte para implementar um proxy reverso para Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-127">Internet Information Server Application Request Routing (IIS ARR) is a fully tested and supported option for implementing a reverse proxy for Lync Server 2010 and Lync Server 2013.</span></span> <span data-ttu-id="0d2ff-128">Em novembro de 2012, a Microsoft deixou vendas de licenças do ForeFront Threat Management Gateway 2010 ou TMG.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-128">In November, 2012, Microsoft ceased license sales of ForeFront Threat Management Gateway 2010, or TMG.</span></span> <span data-ttu-id="0d2ff-129">A TMG ainda é um produto com suporte completo e ainda está disponível para venda nos dispositivos vendidos por terceiros.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-129">TMG is still a fully supported product, and is still available for sale on appliances sold by third parties.</span></span> <span data-ttu-id="0d2ff-130">Além disso, vários balanceadores de carga de hardware e firewalls de terceiros oferecem suporte de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-130">Also, many third party hardware load balancers and firewalls provide reverse proxy support.</span></span> <span data-ttu-id="0d2ff-131">Para balanceadores de carga de hardware e firewalls que oferecem recursos de proxy reverso, consulte seu fornecedor para obter instruções específicas sobre como configurar o produto para fornecer suporte de proxy reverso para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-131">For hardware load balancers and firewalls that provide reverse proxy features, check with your vendor for specific instructions on how to configure their product to provide reverse proxy support for Lync Server.</span></span> <span data-ttu-id="0d2ff-132">Você também pode exibir as terceiros que enviaram a documentação do produto para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-132">You can also view third parties that have submitted documentation for their product to Microsoft.</span></span> <span data-ttu-id="0d2ff-133">O suporte é fornecido por terceiros para sua solução.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-133">Support is provided by the third party for their solution.</span></span> <span data-ttu-id="0d2ff-134">Para ver terceiros que estão ativos no fornecimento de soluções, consulte <A href="https://go.microsoft.com/fwlink/?linkid=268730">Infrastructure Qualified for Microsoft Lync</A>.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-134">To see third parties that are active in providing solutions, see <A href="https://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span></span>



</div>

<span data-ttu-id="0d2ff-135">Os seguintes tópicos e procedimentos usam o Forefront Threat Management Gateway 2010 e o IIS ARR como base para os procedimentos de implantação e configuração.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-135">The following topics and procedures use Forefront Threat Management Gateway 2010 and IIS ARR as the basis for the deployment and configuration procedures.</span></span>

  - [<span data-ttu-id="0d2ff-136">Configurar FQDNs do Web farm para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d2ff-136">Configure web farm FQDNs for Lync Server 2013</span></span>](lync-server-2013-configure-web-farm-fqdns.md)

  - [<span data-ttu-id="0d2ff-137">Configurar adaptadores de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d2ff-137">Configure network adapters in Lync Server 2013</span></span>](lync-server-2013-configure-network-adapters.md)

  - [<span data-ttu-id="0d2ff-138">Solicitar e configurar um certificado para seu proxy HTTP reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d2ff-138">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [<span data-ttu-id="0d2ff-139">Configurar regras de publicação na Web para um único pool interno no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d2ff-139">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [<span data-ttu-id="0d2ff-140">Verificar ou configurar a autenticação e certificação nos diretórios virtuais do IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d2ff-140">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [<span data-ttu-id="0d2ff-141">Criar registros DNS para servidores de proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d2ff-141">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [<span data-ttu-id="0d2ff-142">Verificar o acesso por meio de seu proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d2ff-142">Verify access through your reverse proxy in Lync Server 2013</span></span>](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a><span data-ttu-id="0d2ff-143">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0d2ff-143">Before You Begin</span></span>

<span data-ttu-id="0d2ff-144">Para implantar com êxito o Forefront Threat Management Gateway 2010 como seu proxy reverso, é necessário configurar um servidor, usando os pré-requisitos e requisitos de hardware definidos na documentação do Forefront Threat Management Gateway 2010.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-144">To successfully deploy Forefront Threat Management Gateway 2010 as your reverse proxy, you need to setup and configure a server, using the prerequisites and hardware requirements defined in the Forefront Threat Management Gateway 2010 documentation.</span></span> <span data-ttu-id="0d2ff-145">Consulte o tópico a seguir para configurar corretamente o hardware e para instalar o Forefront Threat Management Gateway 2010 no servidor antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-145">See the following topic set to properly configure the hardware and to install Forefront Threat Management Gateway 2010 on the server before proceeding.</span></span>

  - <span></span>  
    [<span data-ttu-id="0d2ff-146">Forefront Threat Management Gateway (TMG) 2010</span><span class="sxs-lookup"><span data-stu-id="0d2ff-146">Forefront Threat Management Gateway (TMG) 2010</span></span>](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [<span data-ttu-id="0d2ff-147">Recomendações de hardware do Forefront TMG 2010</span><span class="sxs-lookup"><span data-stu-id="0d2ff-147">Forefront TMG 2010 hardware recommendations</span></span>](https://go.microsoft.com/fwlink/?linkid=291293)

<span data-ttu-id="0d2ff-148">Para implantar o IIS ARR como seu proxy reverso, revise os tópicos a seguir para configurar o hardware e o software de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-148">To successfully deploy IIS ARR as your reverse proxy, review the following topics to configure the hardware and the prerequisite software.</span></span>

  - <span></span>  
    <span data-ttu-id="0d2ff-149">Para instalar o IIS no Windows Server 2008 ou no Windows Server 2008 R2, consulte [instalando o IIS 7 no Windows server 2008 ou Windows server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)</span><span class="sxs-lookup"><span data-stu-id="0d2ff-149">To install IIS on Windows Server 2008 or Windows Server 2008 R2, see [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)</span></span>

  - <span></span>  
    <span data-ttu-id="0d2ff-150">Para instalar o IIS no Windows Server 2012, consulte [instalando o IIS 8 no Windows server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span><span class="sxs-lookup"><span data-stu-id="0d2ff-150">To install IIS on Windows Server 2012, see [Installing IIS 8 on Windows Server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span></span>

  - <span></span>  
    <span data-ttu-id="0d2ff-151">Para instalar o IIS no Windows Server 2012 R2, consulte [instalando o iis 8,5 no Windows server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span><span class="sxs-lookup"><span data-stu-id="0d2ff-151">To install IIS on Windows Server 2012 R2, see [Installing IIS 8.5 on Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span></span>

  - <span></span>  
    <span data-ttu-id="0d2ff-152">Para baixar a extensão de roteamento de solicitação de aplicativo para o IIS, siga as instruções em [download de roteamento de solicitação de aplicativo v 2.5](https://go.microsoft.com/fwlink/?linkid=291298)</span><span class="sxs-lookup"><span data-stu-id="0d2ff-152">To download the Application Request Routing extension for IIS, follow the instructions at [Application Request Routing v2.5 Download](https://go.microsoft.com/fwlink/?linkid=291298)</span></span>

  - <span></span>  
    <span data-ttu-id="0d2ff-153">Para instalar o ARR, para as instruções em [instalar o encaminhamento de solicitação de aplicativo versão 2](https://go.microsoft.com/fwlink/?linkid=291299)</span><span class="sxs-lookup"><span data-stu-id="0d2ff-153">To install ARR, for the instructions at [Install Application Request Routing Version 2](https://go.microsoft.com/fwlink/?linkid=291299)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0d2ff-154">As instruções atualmente postadas são para o ARR 2,0.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-154">The instructions currently posted are for ARR 2.0.</span></span> <span data-ttu-id="0d2ff-155">Para a instalação da extensão, não há diferença entre as duas versões.</span><span class="sxs-lookup"><span data-stu-id="0d2ff-155">For installation of the extension, there is no difference between the two versions.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

