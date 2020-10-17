---
title: 'Lync Server 2013: criar ou editar configuração do parceiro XMPP'
description: 'Lync Server 2013: criar ou editar configuração do parceiro XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19289df1920287984f104bb1bdfa214d6f83f5cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553867"
---
# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a><span data-ttu-id="ee4f6-103">Criar ou editar configuração do parceiro XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee4f6-103">Create or edit XMPP partner configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee4f6-104">_**Última modificação do tópico:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="ee4f6-104">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="ee4f6-105">O Microsoft Lync Server 2013 integra um proxy XMPP (Extensible Messaging and Presence Protocol) no servidor de borda e um Gateway XMPP no servidor front-end ou no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-105">Microsoft Lync Server 2013 integrates an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="ee4f6-106">Para permitir conexões de outras implantações do XMPP, você deve configurar o XMPP no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-106">To allow connections from other XMPP deployments, you must configure XMPP in the Lync Server Control Panel.</span></span> <span data-ttu-id="ee4f6-107">Defina as configuração com base no domínio XMPP.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-107">You configure settings on an XMPP domain basis.</span></span> <span data-ttu-id="ee4f6-108">Para criar uma nova associação de parceiro, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ee4f6-108">To create a new partner association, you do the following:</span></span>

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a><span data-ttu-id="ee4f6-109">Para criar um novo parceiro federado ou editar uma configuração existente</span><span class="sxs-lookup"><span data-stu-id="ee4f6-109">To create a new federated partner or edit an existing configuration</span></span>

1.  <span data-ttu-id="ee4f6-110">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ee4f6-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ee4f6-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ee4f6-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ee4f6-113">Na barra de navegação esquerda, clique em **Federação e Acesso Externo** e, então, clique em**Parceiros XMPP Federados**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-113">In the left navigation bar, click **Federation and External Access**, and then click **XMPP Federated Partners**.</span></span>

4.  <span data-ttu-id="ee4f6-114">Para criar uma configuração, clique em **Novo**</span><span class="sxs-lookup"><span data-stu-id="ee4f6-114">To create a new configuration, click **New**</span></span>

5.  <span data-ttu-id="ee4f6-115">Para editar uma configuração existente, selecione-a e clique em **Editar**</span><span class="sxs-lookup"><span data-stu-id="ee4f6-115">To edit an existing configuration, select the configuration and click **Edit**</span></span>

6.  <span data-ttu-id="ee4f6-116">Para criar ou editar configurações de **Parceiros XMPP Federados**, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="ee4f6-116">To create or edit configurations for **XMPP Federated Partners**, you define the following settings:</span></span>

7.  <span data-ttu-id="ee4f6-117">**Domínio primário** (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="ee4f6-117">**Primary domain** (Required).</span></span> <span data-ttu-id="ee4f6-118">O domínio primário é o domínio base do parceiro XMPP.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-118">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="ee4f6-119">Por exemplo, você deveria inserir **fabrikam.com** para o nome de domínio do parceiro XMPP.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-119">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="ee4f6-120">Esta é uma entrada necessária.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-120">This is a required entry.</span></span>

8.  <span data-ttu-id="ee4f6-121">**Descrição**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-121">**Description**.</span></span> <span data-ttu-id="ee4f6-122">A descrição é para notas ou outra informação de identificação desta determinada configuração.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-122">The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="ee4f6-123">Esta entrada é opcional.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-123">This entry is optional.</span></span>

9.  <span data-ttu-id="ee4f6-124">**Domínios adicionais**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-124">**Additional domains**.</span></span> <span data-ttu-id="ee4f6-125">Os domínios adicionais são domínios que fazem parte do seu domínio do parceiro XMPP que devem ser incluídos como parte da comunicação XMPP permitida.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-125">Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="ee4f6-126">Por exemplo, se o domínio primário for **fabrikam.com**, será preciso listar todos os domínios que estão sob fabrikam.com e com os quais haverá comunicação por meio de XMPP.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-126">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span> <span data-ttu-id="ee4f6-127">Por exemplo, é possível inserir **corp.fabrikam.com** e **it.fabrikam.com** para o domínio XMPP corporativo e para o domínio XMPP de TI sob o domínio XMPP básico fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-127">For example, you might enter **corp.fabrikam.com** and **it.fabrikam.com** for the Corporate XMPP domain and the Information Technologies XMPP domain under fabrikam.com’s main XMPP domain.</span></span>

10. <span data-ttu-id="ee4f6-128">**Tipo de parceiro**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-128">**Partner type**.</span></span> <span data-ttu-id="ee4f6-129">O **Tipo de parceiro** é uma configuração obrigatória que dá a você a seleção de três opções em um menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-129">The **Partner type** is a required setting and gives you a selection of three choices in a drop-down menu.</span></span> <span data-ttu-id="ee4f6-130">Você deve escolher umas das seguintes opções para descrever e impor os contatos que podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-130">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="ee4f6-131">É possível selecionar entre:</span><span class="sxs-lookup"><span data-stu-id="ee4f6-131">You can select from:</span></span>
    
      - <span data-ttu-id="ee4f6-132">**Federado**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-132">**Federated**.</span></span> <span data-ttu-id="ee4f6-133">Um tipo de parceiro **federado** é uma conexão confiável entre uma implantação de parceiro do Lync Server ou do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-133">A **Federated** partner type is a trusted connection between a Lync Server or Office Communications Server 2007 R2 partner deployment.</span></span>
    
      - <span data-ttu-id="ee4f6-134">**Público verificado**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-134">**Public verified**.</span></span> <span data-ttu-id="ee4f6-135">Um parceiro **Verificado publicamente** significa que há contatos que fazem parte de uma implantação, que foram verificados pelo provedor e que podem ser adicionados a sua lista de contatos de usuários.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-135">A **Public verified** partner is when contacts that are part of a deployment that are verified by the provider can be added to your user’s list of contacts.</span></span> <span data-ttu-id="ee4f6-136">Os convites podem ser enviados do usuário do Lync ou o usuário do Lync pode aceitar convites do contato do parceiro.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-136">Invites can be sent from the Lync user or the Lync user can accept invites from the partner contact.</span></span>
    
      - <span data-ttu-id="ee4f6-137">**Público não verificado**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-137">**Public unverified**.</span></span> <span data-ttu-id="ee4f6-138">Uma relação de **Não verificado publicamente** implica na ausência de uma relação estabelecida e de status verificável entre as duas implantações.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-138">A **Public unverified** relationship implies that there is no established and verifiable status between the two deployments.</span></span> <span data-ttu-id="ee4f6-139">Um usuário do Lync deve convidar o contato não verificado para que o contato possa adicionar o usuário do Lync à sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-139">A Lync user must invite the unverified contact for that contact to be able to add the Lync user to his contact list.</span></span> <span data-ttu-id="ee4f6-140">Por exemplo, o Google GTalk não é um serviço do XMPP verificado como se relaciona com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-140">For example, Google GTalk is not a public verified XMPP service as it relates to Lync Server.</span></span> <span data-ttu-id="ee4f6-141">Um usuário do GTalk não será capaz de adicionar o usuário do Lync como um contato, a menos que haja um convite explícito enviado pelo usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-141">A GTalk user will not be able to add the Lync user as a contact unless there is an explicit invite sent from the Lync user.</span></span>

11. <span data-ttu-id="ee4f6-142">Observações sobre a negociação de fluxo e os métodos de segurança de TLS (protocolo TLS) e SASL (Software Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="ee4f6-142">Notes on stream negotiation and the security methods Transport Layer Security (TLS) and Software Authentication and Security Layer (SASL):</span></span>
    
    <span data-ttu-id="ee4f6-p110">O XSF (**XMPP Standards Foundation**) e o IETF (**Internet Engineering Task Force**) definem um conjunto de regras e padrões de uso e gerenciamento de certificados de cliente de TLS e o mecanismo SASL. O uso de TLS e SASL é o processo exigido para proteger o fluxo XMPP. Segundo o documento Padrões de XMPP **XEP-0178**, “especifica um fluxo de protocolo recomendado para uso do mecanismo EXTERNO SASL com certificados PKIX, especialmente quando um serviço XMPP indicar que o protocolo TLS é obrigatório para a negociação". PKIX, como declarado na documentação do XSF, refere-se à infraestrutura da chave pública, também conhecida como PKI.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-p110">The **XMPP Standards Foundation** (XSF) and the **Internet Engineering Task Force** (IETF) define a set of rules and standards for using and managing TLS client certificates, TLS server certificates, and the SASL mechanism. Using TLS and SASL is the required process for securing the XMPP stream. From the XMPP Standards document **XEP-0178**, “specifies a recommended protocol flow for use of the SASL EXTERNAL mechanism with PKIX certificates, especially when an XMPP service indicates that TLS is mandatory-to-negotiate.” PKIX, as stated in the XSF documentation, refers to public key infrastructure, also known as PKI.</span></span>
    
    <span data-ttu-id="ee4f6-147">Consulte o documento do XSF XEP-0178 para obter mais detalhes sobre os requisitos de XMPP.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-147">Refer to the XSF document XEP-0178 for more details on the XMPP requirements.</span></span> <span data-ttu-id="ee4f6-148">Para obter detalhes, consulte “XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates”.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-148">For details, refer to “XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates”.</span></span> <http://xmpp.org/extensions/xep-0178.html>
    
    <span data-ttu-id="ee4f6-149">Consulte o documento de IETF "Extensible Messaging and Presence Protocol (XMPP): Core", seção 5,0, negociação de STARTTLS <https://tools.ietf.org/html/rfc6120> .</span><span class="sxs-lookup"><span data-stu-id="ee4f6-149">Refer to the IETF document “Extensible Messaging and Presence Protocol (XMPP): Core“, Section 5.0, STARTTLS Negotiation <https://tools.ietf.org/html/rfc6120>.</span></span>
    
      - <span data-ttu-id="ee4f6-150">**Negociação TLS**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-150">**TLS Negotiation**.</span></span> <span data-ttu-id="ee4f6-151">Define as regras de negociação TLS.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-151">Defines the TLS negotiation rules.</span></span> <span data-ttu-id="ee4f6-152">Um serviço XMPP pode exigir TLS, pode tornar o TLS opcional, ou definir que o TLS não é suportado.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-152">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="ee4f6-153">Escolher Opcional deixa os requisitos para o serviço XMPP para uma decisão de obrigatória para negociação.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-153">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="ee4f6-154">Para exibir todas as configurações e detalhes possíveis para a negociação SASL, TLS e Dialback – incluindo configurações de erro não válidas e conhecidas-consulte [configurações de negociação para parceiros federados do XMPP no Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="ee4f6-154">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="ee4f6-155">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-155">**Required**.</span></span> <span data-ttu-id="ee4f6-156">O serviço XMPP exige a negociação TLS.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-156">The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="ee4f6-157">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-157">**Optional**.</span></span> <span data-ttu-id="ee4f6-158">O serviço XMPP indica que o TLS é obrigatório para negociar.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-158">The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="ee4f6-159">**Sem suporte**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-159">**Not Supported**.</span></span> <span data-ttu-id="ee4f6-160">O serviço XMPP não suporta TLS.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-160">The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="ee4f6-161">**Negociação SASL**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-161">**SASL negotiation**.</span></span> <span data-ttu-id="ee4f6-162">Define as regras de negociação SASL.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-162">Defines the SASL negotiation rules.</span></span> <span data-ttu-id="ee4f6-163">Um serviço XMPP pode exigir SASL, pode tornar SASL opcional ou definir que o SASL não é suportado.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-163">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="ee4f6-164">A escolha de Opcional deixa o requisito a carga do serviço XMPP parceiro para uma decisão obrigatória para negociação.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-164">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="ee4f6-p117">SASL exige o protocolo TLS. Para usar SASL, o protocolo TLS deve ser obrigatório ou opcional. Qualquer configuração que defina SASL como obrigatório ou opcional deve ter suporte ao protocolo TLS. Quando clicar em <STRONG>Confirmar</STRONG> para salvar suas alterações, se ainda não tiver definido o protocolo TLS como obrigatório ou opcional, você será avisado de que SASL deve ter suporte ao protocolo TLS e as alterações não serão salvas. Para solucionar o erro, defina o protocolo TLS como <STRONG>Obrigatório</STRONG> ou <STRONG>Opcional</STRONG>. Se o uso de SASL for opcional e o suporte à negociação do protocolo TLS não for possível, será preciso definir a negociação SASL como <STRONG>Não suportado</STRONG>. Confirme no serviço XMPP como devem ser os fluxos de negociação apropriados SASL ou do protocolo TLS ou ocorrerá uma interrupção do serviço.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-p117">SASL requires TLS. To use SASL, TLS must either be required or optional. Any configuration that defines SASL as either required or optional must have TLS support. When clicking <STRONG>Commit</STRONG> to save your changes, if you have not set TLS to required or optional, you will be warned that SASL must have TLS support and your changes are not saved. To resolve the error, set TLS to <STRONG>Required</STRONG> or <STRONG>Optional</STRONG>. If use of SASL is optional and TLS negotiation support is not possible, you must set SASL negotiation to <STRONG>Not Supported</STRONG>. Confirm with the XMPP service what the proper negotiation streams must be for TLS and SASL or service interruption will occur.</span></span>

        
        </div>
        
          - <span></span>  
            <span data-ttu-id="ee4f6-172">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-172">**Required**.</span></span> <span data-ttu-id="ee4f6-173">O serviço XMPP exige negociação SASL.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-173">The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="ee4f6-174">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-174">**Optional**.</span></span> <span data-ttu-id="ee4f6-175">O serviço XMPP indica que o SASL é obrigatório para negociar.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-175">The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="ee4f6-176">**Sem suporte**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-176">**Not Supported**.</span></span> <span data-ttu-id="ee4f6-177">O serviço XMPP não suporta SASL.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-177">The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="ee4f6-178">**Negociação Dialback**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-178">**Dialback negotiation**.</span></span> <span data-ttu-id="ee4f6-179">A negociação Dialback é definida pelo XSF no documento **XEP-220: Server Dialback** <http://xmpp.org/extensions/xep-0220.html> .</span><span class="sxs-lookup"><span data-stu-id="ee4f6-179">Dialback negotiation is defined by the XSF in document **XEP-220 : Server Dialback** <http://xmpp.org/extensions/xep-0220.html>.</span></span> <span data-ttu-id="ee4f6-180">O processo do servidor de rediscagem usa o DNS (Sistema de Nomes de Domínio) e um servidor autoritativo para verificar se a solicitação veio de um parceiro XMPP válido.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-180">The server dialback process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="ee4f6-181">Para isso, o servidor de origem cria uma mensagem de um tipo específico com uma chave de rediscagem gerada e pesquisa o servidor de recebimento no DNS.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-181">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="ee4f6-182">O servidor originador envia a chave em um fluxo XML para a pesquisa DNS resultante, provavelmente o servidor recebedor.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-182">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="ee4f6-183">Na receita do fluxo chave sobre XML, o servidor recebedor não responde ao servidor originador, mas envia a chave para um servidor autoritativo conhecido.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-183">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="ee4f6-184">O servidor autoritativo verifica se a chave é válida ou inválida.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-184">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="ee4f6-185">Se não for válida, o servidor recebedor não responde ao servidor originador.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-185">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="ee4f6-186">Se a chave é válida, o servidor recebedor informa ao servidor originador que a identidade e a chave é válida e a conversação pode começar.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-186">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="ee4f6-187">Existem dois estados válidos para **Negociação de discagem**:</span><span class="sxs-lookup"><span data-stu-id="ee4f6-187">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="ee4f6-188">**True**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-188">**True**.</span></span> <span data-ttu-id="ee4f6-189">O servidor XMPP está configurado para receber negociação de rediscagem se uma solicitação for recebida de um servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-189">The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server</span></span>
        
          - <span></span>  
            <span data-ttu-id="ee4f6-190">**False**.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-190">**False**.</span></span> <span data-ttu-id="ee4f6-191">O servidor XMPP não está configurado para usar negociação de rediscagem se uma solicitação for recebida de um servidor de origem; a solicitação será ignorada.</span><span class="sxs-lookup"><span data-stu-id="ee4f6-191">The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

