---
title: Configurar o Gateway XMPP no Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e1b9134b1dd1c22fed888d409dd9ea21c9877ee
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="3f7d2-102">Configurar o Gateway XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f7d2-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f7d2-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3f7d2-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3f7d2-104">Ao configurar políticas para suportar parceiros federados XMPP, as políticas para usuários dos domínios federados XMPP, mas não usuários de provedores de serviço de mensagem instantânea (IM) do SIP (por exemplo, Windows Live) ou domínios federados SIP.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="3f7d2-105">Você configura um Parceiro Federado XMPP para cada domínio federado XMPP que você deseja permitir seus usuários para adicionar contatos e comunicar-se com eles.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="3f7d2-106">Depois que as políticas estiverem em vigor, as tarefas adicionais incluirão a configuração dos certificados de gateway do XMPP, a implantação do Gateway XMPP do Lync Server 2013 e, finalmente, a atualização dos registros DNS do Gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="3f7d2-107">Configurar certificados do Gateway XMPP no Servidor de Borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f7d2-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="3f7d2-108">No Servidor de Borda, no Assistente de Implantação, próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="3f7d2-109">Se estiver implantando o Servidor de Borda pela primeira vez, você verá Executar ao invés de Executar novamente.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="3f7d2-110">Na página **Tarefas de Certificado Disponíveis**, clique em **Criar uma nova solicitação de certificado**.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="3f7d2-111">Na página **Solicitação de Certificado**, clique em **Certificado de Borda Externa**.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="3f7d2-112">Na página **Solicitação Atrasada ou Imediata**, marque a caixa de seleção **Preparar a solicitação agora, mas enviá-la depois**.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="3f7d2-113">Na página **arquivo de solicitação de certificado** , digite o caminho completo e o nome do arquivo para o qual a solicitação será salva (por exemplo, c:\\CERT\_externos\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="3f7d2-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="3f7d2-114">Na página **Especificar Modelo de Certificado Alternativo**, para usar um modelo diferente do modelo WebServer padrão, marque a caixa de seleção **Usar o modelo de certificado alternativo para a autoridade de certificação selecionada**.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="3f7d2-115">Na página **Nome e Configurações de Segurança**, siga estes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="3f7d2-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="3f7d2-116">Em **Nome amigável**, digite um nome para exibição do certificado.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="3f7d2-117">Em **Comprimento de bit**, especifique o comprimento de bit (normalmente o padrão de 2048).</span><span class="sxs-lookup"><span data-stu-id="3f7d2-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="3f7d2-118">Verifique se a caixa de seleção **Marcar chave privada de certificado como exportável**  está marcada.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="3f7d2-119">Na página **Informações da Organização**, digite o nome da organização e a unidade organizacional (por exemplo, uma divisão ou departamento).</span><span class="sxs-lookup"><span data-stu-id="3f7d2-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="3f7d2-120">Na página **Informações Geográficas**, especifique as informações de localização.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="3f7d2-p102">Na página **Nome da Entidade/Nomes Alternativos da Entidade**, as informações a serem preenchidas automaticamente pelo assistente são exibidas. Se nomes alternativos de entidade adicionais forem necessários, especifique-os nas próximas duas etapas.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-p102">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="3f7d2-123">Na página **configuração do domínio SIP em nomes alternativos da entidade (SANs)** , marque a caixa de seleção domínio para adicionar um SIP. \<entrada\> sipdomain para a lista de nomes alternativos de entidade.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="3f7d2-124">Na página **Configurar Nomes Alternativos da Entidade Adicionais**, especifique quaisquer nomes alternativos de entidade adicionais que sejam necessários.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-124">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="3f7d2-p103">Se o proxy XMPP é instalado, por padrão o nome de domínio (como contoso.com) é preenchido nas entradas SAN. Se você precisa de mais entradas, adicione-as nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-p103">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="3f7d2-127">Na página **Resumo da Solicitação**, revise as informações do certificado a serem usadas para gerar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-127">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="3f7d2-128">Após a conclusão da execução dos comandos, é possível **Exibir o Log** ou clicar em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-128">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="3f7d2-129">Na página **Arquivo de Solicitação de Certificado**, veja o arquivo de solicitação de assinatura de certificado (CSR) gerado clicando em Exibir ou saia do Assistente de Certificado clicando em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-129">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="3f7d2-130">Copie o arquivo de solicitação e envie-o à sua autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-130">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="3f7d2-p104">Após receber, importar e atribuir o certificado público, você deve parar e reiniciar os serviços do Servidor de Borda. Você faz isso digitando no console do Gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="3f7d2-p104">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="3f7d2-133">Configurar um novo Gateway XMPP do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f7d2-133">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="3f7d2-134">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-134">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="3f7d2-135">Na barra de navegação esquerda, clique em **Acesso Externo e Federação** e em **Parceiros XMPP Federados**.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-135">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="3f7d2-136">Para criar uma nova configuração, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-136">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="3f7d2-137">Defina as configurações globais:</span><span class="sxs-lookup"><span data-stu-id="3f7d2-137">Define the following settings:</span></span>

5.  <span data-ttu-id="3f7d2-138">**Domínio primário (**     obrigatório).</span><span class="sxs-lookup"><span data-stu-id="3f7d2-138">**Primary domain**    (Required).</span></span> <span data-ttu-id="3f7d2-139">O domínio primário é o domínio base do parceiro XMPP.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-139">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="3f7d2-140">Por exemplo, você deveria inserir **fabrikam.com** para o nome de domínio do parceiro XMPP.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-140">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="3f7d2-141">Esta é uma entrada necessária.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-141">This is a required entry.</span></span>

6.  <span data-ttu-id="3f7d2-142">**Descrição**   a descrição é para anotações ou outras informações de identificação para esta configuração específica.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-142">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="3f7d2-143">Esta entrada é opcional.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-143">This entry is optional.</span></span>

7.  <span data-ttu-id="3f7d2-144">**Domínios adicionais domínios**   adicionais são domínios que fazem parte do domínio do seu parceiro do XMPP que devem ser incluídos como parte da comunicação do XMPP permitido.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-144">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="3f7d2-145">Por exemplo, se o domínio primário é **fabrikam.com**, você deve listar todos os outros domínios sob fabrikam.com que irão se comunicar através do XMPP.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-145">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="3f7d2-146">**Tipo de parceiro**   o **tipo de parceiro** é uma configuração obrigatória.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-146">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="3f7d2-147">Você deve escolher um dos seguintes para descrever e forçar quais contatos podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-147">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="3f7d2-148">É possível selecionar entre:</span><span class="sxs-lookup"><span data-stu-id="3f7d2-148">You can select from:</span></span>
    
      - <span data-ttu-id="3f7d2-149">**Federado** Um tipo de parceiro **federado** representa um alto nível de confiança entre a implantação do Lync Server e o parceiro XMPP.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-149">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="3f7d2-150">Este tipo de parceiro é recomendado para federação com servidores XMPP dentro da mesma empresa ou se há uma relação comercial estabelecida.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-150">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="3f7d2-151">Os contatos XMPP nos parceiros Federados podem:</span><span class="sxs-lookup"><span data-stu-id="3f7d2-151">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="3f7d2-152">Adicionar contatos do Lync e exibir sua presença sem autorização expressa do usuário Lync.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-152">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="3f7d2-153">Enviar mensagens instantâneas para contatos do Lync se o usuário do Lync os adicionou ou não em sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-153">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="3f7d2-154">Veja as notas de status do usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-154">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="3f7d2-155">**Público verificado** um parceiro **público verificado** é um provedor de XMPP público que é confiável para verificar a identidade de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-155">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="3f7d2-156">Os contatos XMPP nas redes Públicas verificadas podem adicionar contatos do Lync e exibir sua presença e enviar mensagens instantâneas para eles sem expressar a autorização dos usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-156">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="3f7d2-157">Os contatos do XMPP em redes verificadas públicas nunca veem as notas de status dos usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-157">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="3f7d2-158">Essa configuração não é recomendada.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-158">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="3f7d2-p111">**Público não verificado** Um parceiro **Público não verificado** é um provedor XMPP público não confiável para verificar a identidade de seus usuários.  Usuários XMPP em redes Públicas não verificadas não podem se comunicar com usuários do Lync, a menos que o usuário do Lync os autorize expressamente adicionando-os à lista de contatos.  Os usuários XMPP em redes públicas não verificadas nunca veem as notas de status de usuários do Lync.  Essa configuração é recomendada para qualquer federação com provedores XMPP públicos como o Google Talk.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-p111">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.  XMPP users on public unverified networks never see Lync users’ status notes.  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="3f7d2-163">**Tipo de conexão:** define as diversas regras e configurações de retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-163">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="3f7d2-164">**A negociação**   TLS define as regras de negociação TLS.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-164">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="3f7d2-165">Um serviço XMPP pode exigir TLS, pode tornar o TLS opcional, ou definir que o TLS não é suportado.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-165">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="3f7d2-166">Escolher Opcional deixa os requisitos para o serviço XMPP para uma decisão de obrigatória para negociação.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-166">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="3f7d2-167">Para exibir todas as configurações e detalhes possíveis para a negociação SASL, TLS e Dialback – incluindo configurações de erro não válidas e conhecidas-consulte [configurações de negociação para parceiros federados do XMPP no Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="3f7d2-167">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="3f7d2-168">**Obrigatório**   o serviço XMPP requer negociação TLS.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-168">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="3f7d2-169">**Opcional**   o serviço XMPP indica que o TLS é obrigatório para negociar.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-169">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="3f7d2-170">**Não suportado**   o serviço XMPP não oferece suporte a TLS.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-170">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="3f7d2-171">**A negociação**   SASL define as regras de negociação SASL.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-171">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="3f7d2-172">Um serviço XMPP pode exigir SASL, pode tornar SASL opcional ou definir que o SASL não é suportado.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-172">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="3f7d2-173">Escolher Opcional deixa os requisitos para o serviço XMPP parceiro para uma decisão de obrigatório para negociar.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-173">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="3f7d2-174">**Obrigatório**   o serviço XMPP requer negociação SASL.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-174">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="3f7d2-175">**Opcional**   o serviço XMPP indica que SASL é obrigatório para negociar.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-175">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="3f7d2-176">**Não suportado**   o serviço XMPP não suporta SASL.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-176">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="3f7d2-177">**Dialback negociação de servidor de suporte** O processo de negociação dialback do servidor de suporte usa o DNS (sistema de nomes de domínio) e um servidor autoritativo para verificar se a solicitação provém de um parceiro do XMPP válido.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-177">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="3f7d2-178">Para fazer isso, o servidor originador cria uma mensagem de um tipo específico com uma chave de discagem gerada e procura o servidor de recebimento no DNS.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-178">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="3f7d2-179">O servidor originador envia a chave em um fluxo XML para a pesquisa DNS resultante, provavelmente o servidor recebedor.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-179">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="3f7d2-180">Na receita do fluxo chave sobre XML, o servidor recebedor não responde ao servidor originador, mas envia a chave para um servidor autoritativo conhecido.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-180">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="3f7d2-181">O servidor autoritativo verifica se a chave é válida ou inválida.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-181">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="3f7d2-182">Se não for válida, o servidor recebedor não responde ao servidor originador.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-182">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="3f7d2-183">Se a chave é válida, o servidor recebedor informa ao servidor originador que a identidade e a chave é válida e a conversação pode começar.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-183">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="3f7d2-184">Existem dois estados válidos para **Negociação de discagem**:</span><span class="sxs-lookup"><span data-stu-id="3f7d2-184">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="3f7d2-185">**True**   o servidor do XMPP está configurado para usar a negociação do Dialback se uma solicitação precisar ser recebida de um servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-185">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="3f7d2-186">**False**   o servidor XMPP não está configurado para usar a negociação Dialback e, se uma solicitação for recebida de um servidor de origem, ela será ignorada.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-186">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="3f7d2-187">Clique em **Confirmar** para salvar suas mudanças para a política local ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-187">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="3f7d2-188">Atualizar registros DNS para Gateway XMPP do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f7d2-188">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="3f7d2-189">Para configurar o DNS para Federação XMPP, adicione o seguinte registro SRV ao seu DNS externo:\_XMPP-Server. \_TCP. \<nome\> do domínio o registro SRV resolverá o FQDN de borda de acesso do servidor de borda, com um valor de porta de 5269.</span><span class="sxs-lookup"><span data-stu-id="3f7d2-189">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

