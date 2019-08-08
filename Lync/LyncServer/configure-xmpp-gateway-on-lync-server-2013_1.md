---
title: Configurar o gateway do XMPP no Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e972b8729126615a375f4d82f4c378a71642a4fb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="acc34-102">Configurar o gateway do XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acc34-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acc34-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="acc34-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="acc34-104">Quando você configura políticas para dar suporte a parceiros federados do protocolo de Unificação de mensagens e de protocolo de presença (XMPP), as políticas se aplicam a usuários de domínios federados XMPP, mas não aos usuários de provedores de serviços de mensagens instantâneas SIP (protocolo de iniciação de sessão) (por exemplo, Windows Live) ou domínios federados SIP.</span><span class="sxs-lookup"><span data-stu-id="acc34-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="acc34-105">Você configura um parceiro federado do XMPP para cada domínio federado XMPP que você deseja permitir que os usuários adicionem contatos e se comuniquem.</span><span class="sxs-lookup"><span data-stu-id="acc34-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="acc34-106">Depois que as políticas estiverem em vigor, as tarefas adicionais incluirão a configuração dos certificados de gateway do XMPP, a implantação do Gateway XMPP do Lync Server 2013 e, finalmente, a atualização de registros DNS do Gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="acc34-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="acc34-107">Configurar certificados de gateway do XMPP no servidor de borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acc34-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="acc34-108">No servidor de borda, no assistente de implantação, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.</span><span class="sxs-lookup"><span data-stu-id="acc34-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="acc34-109">Se você estiver implantando o servidor de borda pela primeira vez, você verá executar novamente em vez de executar novamente.</span><span class="sxs-lookup"><span data-stu-id="acc34-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="acc34-110">Na página **Tarefas de Certificado Disponíveis**, clique em  **Criar uma nova solicitação de certificado**.</span><span class="sxs-lookup"><span data-stu-id="acc34-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="acc34-111">Na página **solicitação de certificado** , clique em **certificado de borda externa**.</span><span class="sxs-lookup"><span data-stu-id="acc34-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="acc34-112">Na página **solicitação atrasada ou imediata** , marque a caixa de seleção **preparar a solicitação agora, mas enviá-la mais tarde** .</span><span class="sxs-lookup"><span data-stu-id="acc34-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="acc34-113">Na página **arquivo de solicitação de certificado** , digite o caminho completo e o nome do arquivo para o qual a solicitação deve ser salva (por exemplo, c:\\CERT\_guia\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="acc34-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="acc34-114">Na página **especificar modelo de certificado alternativo** , para usar um modelo diferente do modelo padrão do webserver, marque a caixa de seleção **usar modelo de certificado alternativo para a autoridade de certificação selecionada** .</span><span class="sxs-lookup"><span data-stu-id="acc34-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="acc34-115">Na página **configurações de nome e segurança** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="acc34-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="acc34-116">Em **nome amigável**, digite um nome de exibição para o certificado.</span><span class="sxs-lookup"><span data-stu-id="acc34-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="acc34-117">Em **comprimento de bit**, especifique o comprimento do bit (geralmente, o padrão de 2048).</span><span class="sxs-lookup"><span data-stu-id="acc34-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="acc34-118">Verifique se a caixa de seleção **Marcar chave privada de certificado como** exportável está marcada.</span><span class="sxs-lookup"><span data-stu-id="acc34-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="acc34-119">Na página **informações da organização** , digite o nome da organização e da unidade organizacional (por exemplo, uma divisão ou um departamento).</span><span class="sxs-lookup"><span data-stu-id="acc34-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="acc34-120">Na página **informações** geográficas, especifique as informações de localização.</span><span class="sxs-lookup"><span data-stu-id="acc34-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="acc34-121">Na página **nome do assunto/nomes alternativos de assunto** , as informações a serem automaticamente preenchidas pelo assistente serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="acc34-121">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="acc34-122">Se forem necessários nomes alternativos de entidades adicionais, especifique-os nas próximas duas etapas.</span><span class="sxs-lookup"><span data-stu-id="acc34-122">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="acc34-123">Na **configuração de domínio SIP na página de nomes alternativos de entidades (SANs)** , marque a caixa de seleção domínio para adicionar um SIP. \<entrada\> sipdomain para a lista de nomes alternativos de assunto.</span><span class="sxs-lookup"><span data-stu-id="acc34-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="acc34-124">Na página **configurar nomes alternativos de entidades adicionais** , especifique os nomes alternativos de entidades adicionais necessários.</span><span class="sxs-lookup"><span data-stu-id="acc34-124">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="acc34-125">Se o proxy XMPP estiver instalado, por padrão, o nome de domínio (como contoso.com) será preenchido nas entradas de SAN.</span><span class="sxs-lookup"><span data-stu-id="acc34-125">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="acc34-126">Se você precisar de mais entradas, adicione-as nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="acc34-126">If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="acc34-127">Na página **Resumo da solicitação** , examine as informações do certificado a serem usadas para gerar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="acc34-127">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="acc34-128">Após a conclusão da execução dos comandos, você pode **Exibir o log**ou clicar em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="acc34-128">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="acc34-129">Na página **arquivo de solicitação de certificado** , você pode exibir o arquivo de solicitação de assinatura de certificado (CSR) gerado clicando em exibir ou em sair do assistente de certificado clicando em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="acc34-129">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="acc34-130">Copie o arquivo de solicitação e envie para sua autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="acc34-130">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="acc34-131">Depois de receber, importar e atribuir o certificado público, você deve parar e reiniciar os serviços do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="acc34-131">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="acc34-132">Para fazer isso, digite no console de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="acc34-132">You do this by typing in the Lync Server Management console:</span></span>
    
       ```
        Stop-CsWindowsService
       ```
    
       ```
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="acc34-133">Configurar um novo gateway do Lync Server 2013 XMPP</span><span class="sxs-lookup"><span data-stu-id="acc34-133">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="acc34-134">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="acc34-134">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="acc34-135">Na barra de navegação à esquerda, clique em **Federação e acesso externo** e, em seguida, clique em **parceiros federados do XMPP**.</span><span class="sxs-lookup"><span data-stu-id="acc34-135">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="acc34-136">Para criar uma nova configuração, clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="acc34-136">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="acc34-137">Defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="acc34-137">Define the following settings:</span></span>

5.  <span data-ttu-id="acc34-138">**Domínio primário (**     obrigatório).</span><span class="sxs-lookup"><span data-stu-id="acc34-138">**Primary domain**    (Required).</span></span> <span data-ttu-id="acc34-139">O domínio primário é o domínio base do parceiro XMPP.</span><span class="sxs-lookup"><span data-stu-id="acc34-139">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="acc34-140">Por exemplo, você digitaria **fabrikam.com** para o nome de domínio do parceiro XMPP.</span><span class="sxs-lookup"><span data-stu-id="acc34-140">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="acc34-141">Esta é uma entrada obrigatória.</span><span class="sxs-lookup"><span data-stu-id="acc34-141">This is a required entry.</span></span>

6.  <span data-ttu-id="acc34-142">**Descrição**   a descrição é para anotações ou outras informações de identificação para essa configuração específica.</span><span class="sxs-lookup"><span data-stu-id="acc34-142">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="acc34-143">Esta entrada é opcional.</span><span class="sxs-lookup"><span data-stu-id="acc34-143">This entry is optional.</span></span>

7.  <span data-ttu-id="acc34-144">**Domínios adicionais**   os domínios adicionais são domínios que fazem parte do domínio do seu parceiro XMPP que devem ser incluídos como parte da comunicação XMPP permitida.</span><span class="sxs-lookup"><span data-stu-id="acc34-144">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="acc34-145">Por exemplo, se o domínio primário for **fabrikam.com**, você listará todos os outros domínios que estão sob fabrikam.com com os quais você irá se comunicar por meio de XMPP.</span><span class="sxs-lookup"><span data-stu-id="acc34-145">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="acc34-146">**Tipo de parceiro**   o **tipo de parceiro** é uma configuração obrigatória.</span><span class="sxs-lookup"><span data-stu-id="acc34-146">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="acc34-147">Você deve escolher uma das seguintes opções para descrever e reforçar quais contatos podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="acc34-147">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="acc34-148">Você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="acc34-148">You can select from:</span></span>
    
      - <span data-ttu-id="acc34-149">**Federado** Um tipo de parceiro **federado** representa um alto nível de confiança entre a implantação do Lync Server e o parceiro XMPP.</span><span class="sxs-lookup"><span data-stu-id="acc34-149">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="acc34-150">Esse tipo de parceiro é recomendado para federação com servidores XMPP na mesma empresa ou em que há uma relação comercial estabelecida.</span><span class="sxs-lookup"><span data-stu-id="acc34-150">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="acc34-151">Os contatos do XMPP em parceiros federados podem:</span><span class="sxs-lookup"><span data-stu-id="acc34-151">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="acc34-152">Adicione contatos do Lync e visualize sua presença sem a autorização expressa do usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="acc34-152">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="acc34-153">Envie mensagens de chat para contatos do Lync se ou não o usuário do Lync os adicionou à lista de contatos dele.</span><span class="sxs-lookup"><span data-stu-id="acc34-153">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="acc34-154">Consulte as anotações de status de um usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="acc34-154">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="acc34-155">**Público verificado** se um parceiro **verificado público** é um provedor de XMPP público confiável para verificar a identidade de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="acc34-155">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="acc34-156">Os contatos do XMPP em redes verificadas públicas podem adicionar contatos do Lync e exibir sua presença e enviar mensagens de chat a eles sem a autorização expressa dos usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="acc34-156">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="acc34-157">Os contatos do XMPP em redes comprovadas não são exibidos nas notas de status dos usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="acc34-157">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="acc34-158">Esta configuração não é recomendada.</span><span class="sxs-lookup"><span data-stu-id="acc34-158">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="acc34-159">**Público não verificado** Um parceiro não **verificado público** é um provedor de XMPP público que não é confiável para verificar a identidade de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="acc34-159">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="acc34-160">Os usuários do XMPP em redes públicas não verificadas não podem se comunicar com os usuários do Lync, a menos que o usuário do Lync o tenha autorizado expressamente adicionando-os à lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="acc34-160">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="acc34-161">Os usuários do XMPP em redes não verificadas públicas nunca podem ver as notas de status dos usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="acc34-161">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="acc34-162">Essa configuração é recomendada para qualquer Federação com provedores de XMPP públicos, como o Google Talk.</span><span class="sxs-lookup"><span data-stu-id="acc34-162">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="acc34-163">**Tipo de conexão:** Define as várias regras e configurações de dialback.</span><span class="sxs-lookup"><span data-stu-id="acc34-163">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="acc34-164">**A negociação**   de TLS define as regras de negociação de TLS.</span><span class="sxs-lookup"><span data-stu-id="acc34-164">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="acc34-165">Um serviço XMPP pode exigir o TLS, pode criar a TLS opcional ou você define que o TLS não é compatível.</span><span class="sxs-lookup"><span data-stu-id="acc34-165">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="acc34-166">Escolher opcional deixa a necessidade de até o serviço XMPP para uma decisão obrigatória a negociação.</span><span class="sxs-lookup"><span data-stu-id="acc34-166">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="acc34-167">Para ver todas as configurações e os detalhes possíveis para a negociação SASL, TLS e Dialback, incluindo configurações de erro não válidas e conhecidas-consulte [configurações de negociação para XMPP parceiros federados no Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="acc34-167">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="acc34-168">**Obrigatório**   o serviço XMPP exige negociação de TLS.</span><span class="sxs-lookup"><span data-stu-id="acc34-168">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="acc34-169">**Opcional**   o serviço XMPP indica que o TLS é obrigatório para negociar.</span><span class="sxs-lookup"><span data-stu-id="acc34-169">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="acc34-170">**Não compatível com**   o serviço XMPP não é compatível com TLS.</span><span class="sxs-lookup"><span data-stu-id="acc34-170">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="acc34-171">**A negociação**   SASL define as regras de negociação SASL.</span><span class="sxs-lookup"><span data-stu-id="acc34-171">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="acc34-172">Um serviço XMPP pode exigir SASL, pode deixar SASL opcional, ou você define que SASL não é compatível.</span><span class="sxs-lookup"><span data-stu-id="acc34-172">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="acc34-173">Escolher opcional deixa o requisito para o serviço de XMPP do parceiro para uma decisão obrigatória-para-negociação.</span><span class="sxs-lookup"><span data-stu-id="acc34-173">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="acc34-174">**Obrigatório**   o serviço XMPP requer negociação SASL.</span><span class="sxs-lookup"><span data-stu-id="acc34-174">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="acc34-175">**Opcional**   o serviço XMPP indica que a SASL é obrigatória para negociar.</span><span class="sxs-lookup"><span data-stu-id="acc34-175">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="acc34-176">**Não suportado**   o serviço XMPP não dá suporte a SASL.</span><span class="sxs-lookup"><span data-stu-id="acc34-176">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="acc34-177">**Negociação do dialback do servidor de suporte** O processo de negociação dialback do servidor de suporte usa o sistema de nomes de domínio (DNS) e um servidor autoritativo para verificar se a solicitação veio de um parceiro XMPP válido.</span><span class="sxs-lookup"><span data-stu-id="acc34-177">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="acc34-178">Para fazer isso, o servidor de origem cria uma mensagem de um tipo específico com uma chave dialback gerada e procura o servidor de recebimento no DNS.</span><span class="sxs-lookup"><span data-stu-id="acc34-178">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="acc34-179">O servidor de origem envia a chave em um fluxo de XML para a pesquisa de DNS resultante, supostamente o servidor de recebimento.</span><span class="sxs-lookup"><span data-stu-id="acc34-179">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="acc34-180">No recebimento da chave sobre o fluxo XML, o servidor de recebimento não responde ao servidor de origem, mas envia a chave para um servidor autoritativo conhecido.</span><span class="sxs-lookup"><span data-stu-id="acc34-180">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="acc34-181">O servidor autoritativo verifica se a chave é válida ou não é válida.</span><span class="sxs-lookup"><span data-stu-id="acc34-181">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="acc34-182">Se não for válido, o servidor de recebimento não responderá ao servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="acc34-182">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="acc34-183">Se a chave for válida, o servidor de recebimento informa ao servidor de origem que a identidade e a chave são válidas e que a conversa pode começar.</span><span class="sxs-lookup"><span data-stu-id="acc34-183">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="acc34-184">Há dois Estados válidos para a **negociação do Dialback**:</span><span class="sxs-lookup"><span data-stu-id="acc34-184">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="acc34-185">**True**   , o servidor XMPP está configurado para usar a negociação Dialback caso uma solicitação seja recebida de um servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="acc34-185">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="acc34-186">**False**   o XMPP Server não está configurado para usar a negociação Dialback e, caso uma solicitação seja recebida de um servidor de origem, ela será ignorada.</span><span class="sxs-lookup"><span data-stu-id="acc34-186">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="acc34-187">Clique em **confirmar** para salvar as alterações no site ou na política de usuário.</span><span class="sxs-lookup"><span data-stu-id="acc34-187">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="acc34-188">Atualizar registros DNS para o Lync Server 2013 XMPP gateway</span><span class="sxs-lookup"><span data-stu-id="acc34-188">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="acc34-189">Para configurar o DNS para a Federação do XMPP, adicione o seguinte registro SRV ao seu servidor\_DNS externo: XMPP. \_TCP. \<nome\> do domínio o registro SRV será resolvido para o FQDN de borda de acesso do servidor de borda, com um valor de porta de 5269.</span><span class="sxs-lookup"><span data-stu-id="acc34-189">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

