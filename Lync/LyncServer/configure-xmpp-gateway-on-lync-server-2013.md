---
title: Configurar o Gateway XMPP no Lync Server 2013
description: Configure o gateway do XMPP no Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78765237e737dea29d77230d6b0eecdb0348cb41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542947"
---
# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="2652e-103">Configurar o Gateway XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2652e-103">Configure XMPP gateway on Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2652e-104">_**Última modificação do tópico:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="2652e-104">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="2652e-105">As etapas finais para migrar seu gateway do XMPP são configurar certificados para o servidor de borda do Lync Server 2013, implantar o gateway do Lync Server 2013 XMPP e atualizar os registros DNS para o Gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="2652e-105">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="2652e-106">Estas etapas devem ser realizadas em paralelo para minimizar o tempo de inatividade do seu Gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="2652e-106">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="2652e-107">Todos os usuários devem ser movidos para a sua implantação do Microsoft Lync Server 2013 antes de executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2652e-107">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="2652e-108">A Federação XMPP não é suportada para usuários hospedados em aparelhos de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="2652e-108">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="2652e-109">Isso se aplica a informações de presença e troca de mensagens de IM.</span><span class="sxs-lookup"><span data-stu-id="2652e-109">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="2652e-110">Configurar certificados do Gateway XMPP no Servidor de Borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2652e-110">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="2652e-111">No Servidor de Borda, no Assistente de Implantação, próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="2652e-111">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="2652e-112">Se estiver implantando o Servidor de Borda pela primeira vez, você verá Executar ao invés de Executar novamente.</span><span class="sxs-lookup"><span data-stu-id="2652e-112">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="2652e-113">Na página **Tarefas de Certificado Disponíveis**, clique em **Criar uma nova solicitação de certificado**.</span><span class="sxs-lookup"><span data-stu-id="2652e-113">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="2652e-114">Na página **Solicitação de Certificado**, clique em **Certificado de Borda Externa**.</span><span class="sxs-lookup"><span data-stu-id="2652e-114">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="2652e-115">Na página **Solicitação Atrasada ou Imediata**, marque a caixa de seleção **Preparar a solicitação agora, mas enviá-la depois**.</span><span class="sxs-lookup"><span data-stu-id="2652e-115">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="2652e-116">Na página **arquivo de solicitação de certificado** , digite o caminho completo e o nome do arquivo para o qual a solicitação será salva (por exemplo, c: \\ CERT \_ externos \_ Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="2652e-116">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="2652e-117">Na página **Especificar Modelo de Certificado Alternativo**, para usar um modelo diferente do modelo WebServer padrão, marque a caixa de seleção **Usar o modelo de certificado alternativo para a autoridade de certificação selecionada**.</span><span class="sxs-lookup"><span data-stu-id="2652e-117">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="2652e-118">Na página **Nome e Configurações de Segurança**, siga estes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="2652e-118">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="2652e-119">Em **Nome amigável**, digite um nome para exibição do certificado.</span><span class="sxs-lookup"><span data-stu-id="2652e-119">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="2652e-120">Em **Comprimento de bit**, especifique o comprimento de bit (normalmente o padrão de 2048).</span><span class="sxs-lookup"><span data-stu-id="2652e-120">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="2652e-121">Verifique se a caixa de seleção **Marcar chave privada de certificado como exportável**  está marcada.</span><span class="sxs-lookup"><span data-stu-id="2652e-121">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="2652e-122">Na página **Informações da Organização**, digite o nome da organização e a unidade organizacional (por exemplo, uma divisão ou departamento).</span><span class="sxs-lookup"><span data-stu-id="2652e-122">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="2652e-123">Na página **Informações Geográficas**, especifique as informações de localização.</span><span class="sxs-lookup"><span data-stu-id="2652e-123">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="2652e-p103">Na página **Nome da Entidade/Nomes Alternativos da Entidade**, as informações a serem preenchidas automaticamente pelo assistente são exibidas. Se nomes alternativos de entidade adicionais forem necessários, especifique-os nas próximas duas etapas.</span><span class="sxs-lookup"><span data-stu-id="2652e-p103">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="2652e-126">Na página **configuração do domínio SIP em nomes alternativos da entidade (SANs)** , marque a caixa de seleção domínio para adicionar um SIP.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="2652e-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="2652e-127">entrada à lista de nomes alternativos da entidade.</span><span class="sxs-lookup"><span data-stu-id="2652e-127">entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="2652e-128">Na página **Configurar Nomes Alternativos da Entidade Adicionais**, especifique quaisquer nomes alternativos de entidade adicionais que sejam necessários.</span><span class="sxs-lookup"><span data-stu-id="2652e-128">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="2652e-p105">Se o proxy XMPP é instalado, por padrão o nome de domínio (como contoso.com) é preenchido nas entradas SAN. Se você precisa de mais entradas, adicione-as nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="2652e-p105">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="2652e-131">Na página **Resumo da Solicitação**, examine as informações do certificado a ser usado para gerar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="2652e-131">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="2652e-132">Após o comando finalizar a execução, é possível **Exibir o Log** ou clicar em Avançar para continuar.</span><span class="sxs-lookup"><span data-stu-id="2652e-132">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="2652e-133">Na página **Arquivo de solicitação de certificado**, é possível exibir o arquivo CSR gerado clicando em **Exibir** ou sair do Assistente de Certificado clicando em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2652e-133">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="2652e-134">Copie o arquivo solicitado e envie-o para a autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="2652e-134">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="2652e-p106">Após receber, importar e atribuir o certificado público, você deve parar e reiniciar os serviços do Servidor de Borda. Você faz isso digitando no console do Gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="2652e-p106">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="2652e-137">Configurar um novo Gateway XMPP do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2652e-137">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="2652e-138">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2652e-138">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="2652e-139">Na barra de navegação esquerda, clique em **Acesso Externo e Federação** e em **Parceiros XMPP Federados**.</span><span class="sxs-lookup"><span data-stu-id="2652e-139">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="2652e-140">Para criar uma nova configuração, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2652e-140">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="2652e-141">Defina as configurações globais:</span><span class="sxs-lookup"><span data-stu-id="2652e-141">Define the following settings:</span></span>

5.  <span data-ttu-id="2652e-142">**Domínio primário**     (Obrigatório).</span><span class="sxs-lookup"><span data-stu-id="2652e-142">**Primary domain**    (Required).</span></span> <span data-ttu-id="2652e-143">O domínio primário é o domínio base do parceiro XMPP.</span><span class="sxs-lookup"><span data-stu-id="2652e-143">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="2652e-144">Por exemplo, você deveria inserir **fabrikam.com** para o nome de domínio do parceiro XMPP.</span><span class="sxs-lookup"><span data-stu-id="2652e-144">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="2652e-145">Esta é uma entrada necessária.</span><span class="sxs-lookup"><span data-stu-id="2652e-145">This is a required entry.</span></span>

6.  <span data-ttu-id="2652e-146">**Descrição**     A descrição é para anotações ou outras informações de identificação para esta configuração específica.</span><span class="sxs-lookup"><span data-stu-id="2652e-146">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="2652e-147">Esta entrada é opcional.</span><span class="sxs-lookup"><span data-stu-id="2652e-147">This entry is optional.</span></span>

7.  <span data-ttu-id="2652e-148">**Domínios adicionais**     Domínios adicionais são domínios que fazem parte do domínio do seu parceiro do XMPP que devem ser incluídos como parte da comunicação do XMPP permitido.</span><span class="sxs-lookup"><span data-stu-id="2652e-148">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="2652e-149">Por exemplo, se o domínio primário é **fabrikam.com**, você deve listar todos os outros domínios sob fabrikam.com que irão se comunicar através do XMPP.</span><span class="sxs-lookup"><span data-stu-id="2652e-149">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="2652e-150">**Tipo**     de parceiro O **tipo de parceiro** é uma configuração obrigatória.</span><span class="sxs-lookup"><span data-stu-id="2652e-150">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="2652e-151">Você deve escolher um dos seguintes para descrever e forçar quais contatos podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="2652e-151">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="2652e-152">É possível selecionar entre:</span><span class="sxs-lookup"><span data-stu-id="2652e-152">You can select from:</span></span>
    
      - <span data-ttu-id="2652e-153">**Federado**     Um tipo de parceiro **federado** representa um alto nível de confiança entre a implantação do Lync Server e o parceiro XMPP.</span><span class="sxs-lookup"><span data-stu-id="2652e-153">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="2652e-154">Este tipo de parceiro é recomendado para federação com servidores XMPP dentro da mesma empresa ou se há uma relação comercial estabelecida.</span><span class="sxs-lookup"><span data-stu-id="2652e-154">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="2652e-155">Os contatos XMPP nos parceiros Federados podem:</span><span class="sxs-lookup"><span data-stu-id="2652e-155">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="2652e-156">Adicionar contatos do Lync e exibir sua presença sem autorização expressa do usuário Lync.</span><span class="sxs-lookup"><span data-stu-id="2652e-156">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="2652e-157">Enviar mensagens instantâneas para contatos do Lync se o usuário do Lync os adicionou ou não em sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="2652e-157">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="2652e-158">Veja as notas de status do usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="2652e-158">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="2652e-159">**Público verificado**     Um parceiro **público verificado** é um provedor de XMPP público que é confiável para verificar a identidade de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="2652e-159">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="2652e-160">Os contatos XMPP nas redes Públicas verificadas podem adicionar contatos do Lync e exibir sua presença e enviar mensagens instantâneas para eles sem expressar a autorização dos usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="2652e-160">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="2652e-161">Os contatos do XMPP em redes verificadas públicas nunca veem as notas de status dos usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="2652e-161">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="2652e-162">Esta configuração não é recomendada.</span><span class="sxs-lookup"><span data-stu-id="2652e-162">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="2652e-163">**Público não verificado**     Um parceiro não **verificado público** é um provedor de XMPP público que não é confiável para verificar a identidade de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="2652e-163">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="2652e-164">Os usuários do XMPP nas redes Públicas não verificadas não podem se comunicar com os usuários do Lync a não ser que o usuário Lync tenha autorizado expressamente adicionando-os à lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="2652e-164">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="2652e-165">Os usuários do XMPP em redes públicas não verificadas nunca veem as notas de status dos usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="2652e-165">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="2652e-166">Esta configuração é recomendada para qualquer federação com provedores XMPP públicos como o Google Talk.</span><span class="sxs-lookup"><span data-stu-id="2652e-166">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="2652e-167">**Tipo de conexão:** Define as várias regras e configurações de discagem.</span><span class="sxs-lookup"><span data-stu-id="2652e-167">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="2652e-168">**Negociação TLS**     Define as regras de negociação TLS.</span><span class="sxs-lookup"><span data-stu-id="2652e-168">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="2652e-169">Um serviço XMPP pode exigir TLS, pode tornar o TLS opcional, ou definir que o TLS não é suportado.</span><span class="sxs-lookup"><span data-stu-id="2652e-169">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="2652e-170">Escolher Opcional deixa os requisitos para o serviço XMPP para uma decisão de obrigatória para negociação.</span><span class="sxs-lookup"><span data-stu-id="2652e-170">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="2652e-171">Para exibir todas as configurações e detalhes possíveis para a negociação SASL, TLS e Dialback – incluindo configurações de erro não válidas e conhecidas-consulte [configurações de negociação para parceiros federados do XMPP no Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="2652e-171">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="2652e-172">**Necessárias**     O serviço XMPP requer negociação TLS.</span><span class="sxs-lookup"><span data-stu-id="2652e-172">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="2652e-173">**Opcional**     O serviço XMPP indica que o TLS é obrigatório para negociar.</span><span class="sxs-lookup"><span data-stu-id="2652e-173">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="2652e-174">**Sem suporte**     O serviço XMPP não oferece suporte a TLS.</span><span class="sxs-lookup"><span data-stu-id="2652e-174">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="2652e-175">**Negociação SASL**     Define as regras de negociação SASL.</span><span class="sxs-lookup"><span data-stu-id="2652e-175">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="2652e-176">Um serviço XMPP pode exigir SASL, pode tornar SASL opcional ou definir que o SASL não é suportado.</span><span class="sxs-lookup"><span data-stu-id="2652e-176">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="2652e-177">Escolher Opcional deixa os requisitos para o serviço XMPP parceiro para uma decisão de obrigatório para negociar.</span><span class="sxs-lookup"><span data-stu-id="2652e-177">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="2652e-178">**Necessárias**     O serviço XMPP requer negociação SASL.</span><span class="sxs-lookup"><span data-stu-id="2652e-178">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="2652e-179">**Opcional**     O serviço XMPP indica que SASL é obrigatório para negociar.</span><span class="sxs-lookup"><span data-stu-id="2652e-179">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="2652e-180">**Sem suporte**     O serviço XMPP não suporta SASL.</span><span class="sxs-lookup"><span data-stu-id="2652e-180">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="2652e-181">**Dialback negociação de servidor de suporte** O processo de negociação dialback do servidor de suporte usa o DNS (sistema de nomes de domínio) e um servidor autoritativo para verificar se a solicitação provém de um parceiro do XMPP válido.</span><span class="sxs-lookup"><span data-stu-id="2652e-181">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="2652e-182">Para fazer isso, o servidor originador cria uma mensagem de um tipo específico com uma chave de discagem gerada e procura o servidor de recebimento no DNS.</span><span class="sxs-lookup"><span data-stu-id="2652e-182">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="2652e-183">O servidor originador envia a chave em um fluxo XML para a pesquisa DNS resultante, provavelmente o servidor recebedor.</span><span class="sxs-lookup"><span data-stu-id="2652e-183">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="2652e-184">Na receita do fluxo chave sobre XML, o servidor recebedor não responde ao servidor originador, mas envia a chave para um servidor autoritativo conhecido.</span><span class="sxs-lookup"><span data-stu-id="2652e-184">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="2652e-185">O servidor autoritativo verifica se a chave é válida ou inválida.</span><span class="sxs-lookup"><span data-stu-id="2652e-185">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="2652e-186">Se não for válida, o servidor recebedor não responde ao servidor originador.</span><span class="sxs-lookup"><span data-stu-id="2652e-186">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="2652e-187">Se a chave é válida, o servidor recebedor informa ao servidor originador que a identidade e a chave é válida e a conversação pode começar.</span><span class="sxs-lookup"><span data-stu-id="2652e-187">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="2652e-188">Existem dois estados válidos para **Negociação de discagem**:</span><span class="sxs-lookup"><span data-stu-id="2652e-188">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="2652e-189">**True**     O servidor do XMPP está configurado para usar a negociação do Dialback se uma solicitação for recebida de um servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="2652e-189">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="2652e-190">**False**     O servidor do XMPP não está configurado para usar a negociação Dialback e, se uma solicitação precisar ser recebida de um servidor de origem, ela será ignorada.</span><span class="sxs-lookup"><span data-stu-id="2652e-190">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="2652e-191">Clique em **Confirmar** para salvar suas mudanças para a política local ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="2652e-191">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="2652e-192">Atualizar registros DNS para Gateway XMPP do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2652e-192">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="2652e-193">Para configurar o DNS para Federação XMPP, adicione o seguinte registro SRV ao seu DNS externo: \_ XMPP-Server. \_ TCP.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="2652e-193">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="2652e-194">O registro SRV será resolvido para o FQDN de borda de acesso do servidor de borda, com um valor de porta de 5269.</span><span class="sxs-lookup"><span data-stu-id="2652e-194">The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

