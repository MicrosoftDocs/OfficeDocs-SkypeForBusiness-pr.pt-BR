---
title: 'Lync Server 2013: suporte e requisitos adicionais do servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7b83f900a5d6ccca9932b68e012d5c0dbbd6d23
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="bd091-102">Suporte e requisitos adicionais do servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd091-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd091-103">_**Última modificação do tópico:** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="bd091-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="bd091-104">Além do suporte de software descrito nas outras seções desta documentação de suporte, o Lync Server 2013 tem as seguintes limitações de suporte:</span><span class="sxs-lookup"><span data-stu-id="bd091-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="bd091-105">O Lync Server 2013 suporta o DNS (sistema de nomes de domínio) e o balanceamento de carga de hardware para funções de servidor específicas.</span><span class="sxs-lookup"><span data-stu-id="bd091-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="bd091-106">Ele também suporta o balanceamento de carga de aplicativo para Servidores de Mediação, onde for aplicável.</span><span class="sxs-lookup"><span data-stu-id="bd091-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="bd091-107">Para obter detalhes sobre quando usar cada um, consulte a documentação de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="bd091-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="bd091-108">O Lync Server 2013 usa o DLX (Distribution List Expansion Protocol) para expandir as listas de distribuição.</span><span class="sxs-lookup"><span data-stu-id="bd091-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="bd091-109">Esse protocolo também especifica o método de serviço Web que é usado para obter a participação de uma lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="bd091-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="bd091-110">O Microsoft Exchange Server oferece suporte a grupos dinâmicos que não têm Membros atribuídos estaticamente a eles.</span><span class="sxs-lookup"><span data-stu-id="bd091-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="bd091-111">Em vez disso, eles armazenam consultas que são avaliadas quando o grupo é expandido.</span><span class="sxs-lookup"><span data-stu-id="bd091-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="bd091-112">O DLX não oferece suporte a listas de distribuição dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="bd091-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="bd091-113">Essa limitação de DLX se aplica a todas as versões do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bd091-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="bd091-114">O Assistente para Habilitar Usuário não oferece suporte à conversão automática de caracteres do inglês para um URI compatível com SIP; portanto, você deve modificar manualmente o endereço SIP.</span><span class="sxs-lookup"><span data-stu-id="bd091-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="bd091-115">Para servidores que executam software antivírus, consulte [exclusões de verificação antivírus para o Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) para exclusões de vírus sugeridas e outras recomendações relacionadas à segurança.</span><span class="sxs-lookup"><span data-stu-id="bd091-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="bd091-116">Se você usa o IPsec, recomendamos desativar o IPsec nos intervalos de porta usados para o tráfego de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="bd091-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="bd091-117">Para obter detalhes, consulte [exceções de IPsec no Lync Server 2013](lync-server-2013-ipsec-exceptions.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="bd091-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="bd091-118">Caso sua organização use uma infraestrutura de QoS (Qualidade de Serviço), o subsistema de mídia estará projetado para operar dentro dessa infraestrutura existente.</span><span class="sxs-lookup"><span data-stu-id="bd091-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="bd091-119">Para obter detalhes sobre como implementar a QoS, consulte [Managing Quality of Service (QoS) no Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="bd091-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="bd091-120">O uso do firewall do sistema operacional é suportado.</span><span class="sxs-lookup"><span data-stu-id="bd091-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="bd091-121">O Lync Server 2013 gerencia as exceções de firewall para o Firewall do sistema operacional, exceto para o software de banco de dados do Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd091-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="bd091-122">Para obter detalhes sobre os requisitos de firewall SQL Server, consulte a documentação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd091-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="bd091-123">As interfaces externas usadas para implementar o suporte ao acesso de usuário externo devem estar em uma sub-rede separada, *não* na mesma rede que as interfaces internas.</span><span class="sxs-lookup"><span data-stu-id="bd091-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="bd091-124">O recurso XMPP do Lync Server 2013 é testado e suportado pela Microsoft para Federação de mensagens instantâneas com o Google Talk.</span><span class="sxs-lookup"><span data-stu-id="bd091-124">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="bd091-125">Para qualquer outro sistema XMPP, entre em contato com o fornecedor terceirizado para verificar se eles suportam a Federação com o Lync Server 2013 e para qualquer recomendação de implantação ou solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="bd091-125">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="bd091-126">Com o lançamento das atualizações cumulativas do Lync Server 2013:2013 de julho, o Lync Server 2013 agora oferece suporte à autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="bd091-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="bd091-127">Para obter mais informações, consulte [autenticação de dois fatores no Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="bd091-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="bd091-128">A maioria dos servidores internos requer um tipo de certificado definido como **autenticação aberta** (OAuth).</span><span class="sxs-lookup"><span data-stu-id="bd091-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="bd091-129">Você precisa solicitar e atribuir um certificado OAuth durante a fase **solicitar, instalar e atribuir certificados** do assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bd091-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="bd091-130">O tamanho mínimo de uma chave de certificado OAuth é de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="bd091-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="bd091-131">Um aviso pode ser exibido se você solicitar um certificado com um tamanho de chave inferior a 2048 bits de comprimento.</span><span class="sxs-lookup"><span data-stu-id="bd091-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="bd091-132">Para evitar possíveis problemas no caso de um comprimento de chave de 2048 ser aplicado em vez de avisado, é altamente recomendável usar sempre um comprimento de chave de 2048 para certificados OAuth.</span><span class="sxs-lookup"><span data-stu-id="bd091-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="bd091-133">O Lync Server 2013 e o Microsoft Exchange Server 2010 Service Pack 1 (SP1) operam com suporte para algoritmos de 140-2 padrão FIPS (Federal Information Processing Standard) se os sistemas operacionais Windows Server 2008 R2 estiverem configurados para usar os algoritmos FIPS 140-2 para criptografia de sistema.</span><span class="sxs-lookup"><span data-stu-id="bd091-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="bd091-134">Para implementar o suporte a FIPS, você deve configurar cada servidor executando o Lync Server 2013 para dar suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="bd091-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="bd091-135">Para obter detalhes sobre algoritmos compatíveis com FIPS e como implementar o suporte a FIPS, consulte o artigo 811833 da base de dados de conhecimento da Microsoft, "criptografia de sistema: usar algoritmos compatíveis com FIPS para criptografia, hash e assinatura no Windows [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)XP e em versões posteriores do Windows em.</span><span class="sxs-lookup"><span data-stu-id="bd091-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="bd091-136">Para obter detalhes sobre o suporte a FIPS 140-2 e limitações no Exchange 2010, consulte "Exchange 2010 SP1 and Support for FIPS compliant [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)algoritmos" em.</span><span class="sxs-lookup"><span data-stu-id="bd091-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="bd091-137">O Lync Server 2013 requer a instalação de outro software em componentes específicos antes ou durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="bd091-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="bd091-138">Isso inclui software disponível com o sistema operacional, software baixável e software que é instalado automaticamente durante a instalação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd091-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="bd091-139">A seguinte lista cita os softwares adicionais que podem ser necessários:</span><span class="sxs-lookup"><span data-stu-id="bd091-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="bd091-140">Windows Update</span><span class="sxs-lookup"><span data-stu-id="bd091-140">Windows Update</span></span>

  - <span data-ttu-id="bd091-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="bd091-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="bd091-142">Estrutura do Microsoft .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="bd091-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="bd091-143">Microsoft Visual C++ 2012 Redistributable</span><span class="sxs-lookup"><span data-stu-id="bd091-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd091-144">O Microsoft Visual C++ 2012 Redistributable é instalado automaticamente quando você instala o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd091-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="bd091-145">Você não deve instalar e usar qualquer outra versão.</span><span class="sxs-lookup"><span data-stu-id="bd091-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="bd091-146">URL Rewrite Module versão 2.0 Redistributable</span><span class="sxs-lookup"><span data-stu-id="bd091-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="bd091-147">Tempo de Execução do Windows Media Format</span><span class="sxs-lookup"><span data-stu-id="bd091-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="bd091-148">Windows PowerShell versão 3,0</span><span class="sxs-lookup"><span data-stu-id="bd091-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="bd091-149">Plug-in do navegador Microsoft Silverlight 4 (Silverlight 4.0.50524.0 ou a versão mais recente do Painel de Controle do Lync Server)</span><span class="sxs-lookup"><span data-stu-id="bd091-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="bd091-150">Ferramentas de serviços de domínio do Active Directory</span><span class="sxs-lookup"><span data-stu-id="bd091-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="bd091-151">Alguns desses requisitos de software se aplicam somente a funções específicas de servidor ou componentes.</span><span class="sxs-lookup"><span data-stu-id="bd091-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="bd091-152">Para obter detalhes sobre esses requisitos de software, consulte [Additional Software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="bd091-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

