---
title: 'Lync Server 2013: Configurando federação de XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd61aded33d37e4a1f5f58e9050f3cd62794f9b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="8bb9c-102">Configurando federação de XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bb9c-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bb9c-103">_**Tópico da última modificação:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="8bb9c-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="8bb9c-104">Para implantar o proxy XMPP no servidor de borda, você deve configurar o servidor de borda para a Federação do XMPP.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-104">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation.</span></span> <span data-ttu-id="8bb9c-105">Para fazer isso, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-105">To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="8bb9c-106">Configurando a Federação do XMPP</span><span class="sxs-lookup"><span data-stu-id="8bb9c-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="8bb9c-107">Faça logon no computador em que o assistente de implantação do Lync Server está instalado como membro do grupo Domain admins e do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="8bb9c-108">No servidor front-end, abra o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-108">On the Front End server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="8bb9c-109">Clique em instalar ou atualizar o Lync Server System e, em seguida, clique em configurar ou remover componentes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-109">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="8bb9c-110">Clique em executar novamente.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-110">Click Run Again.</span></span>

3.  <span data-ttu-id="8bb9c-111">Em configurar componentes do Lync Server, clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-111">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="8bb9c-112">A tela Resumo mostrará as ações conforme elas são executadas.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-112">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="8bb9c-113">Depois que a implantação for concluída, clique em Exibir log para exibir os arquivos de log disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-113">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="8bb9c-114">Clique em concluir para concluir a implantação.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-114">Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="8bb9c-115">No servidor de borda, abra o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="8bb9c-116">Clique em instalar ou atualizar o Lync Server System e, em seguida, clique em configurar ou remover componentes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="8bb9c-117">Clique em executar novamente.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-117">Click Run Again.</span></span>

5.  <span data-ttu-id="8bb9c-118">Em configurar componentes do Lync Server, clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="8bb9c-119">A tela Resumo mostrará as ações conforme elas são executadas.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="8bb9c-120">Depois que a implantação for concluída, clique em Exibir log para exibir os arquivos de log disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="8bb9c-121">Clique em concluir para concluir a implantação.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-121">Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="8bb9c-122">No servidor de borda, no assistente de implantação, ao lado da etapa 3: solicitar, instalar ou atribuir certificados, clique novamente em executar.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="8bb9c-123">Se você estiver implantando o servidor de borda pela primeira vez, você verá executar novamente em vez de executar novamente.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="8bb9c-124">Na página Tarefas de Certificado Disponíveis, clique em  Criar uma nova solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="8bb9c-125">Na página solicitação de certificado, clique em certificado de borda externa.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="8bb9c-126">Na página solicitação atrasada ou imediata, marque a caixa de seleção preparar a solicitação agora, mas enviá-la mais tarde.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="8bb9c-127">Na página arquivo de solicitação de certificado, digite o caminho completo e o nome do arquivo para o qual a solicitação deve ser salva (por exemplo, c:\\CERT\_guia\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="8bb9c-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="8bb9c-128">Na página especificar modelo de certificado alternativo, para usar um modelo diferente do modelo padrão do webserver, marque a caixa de seleção usar modelo de certificado alternativo para a autoridade de certificação selecionada.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="8bb9c-129">Na página  Nome e Configurações de Segurança, siga estes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="8bb9c-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="8bb9c-130">Em nome amigável, digite um nome de exibição para o certificado</span><span class="sxs-lookup"><span data-stu-id="8bb9c-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="8bb9c-131">Em comprimento de bit, especifique o comprimento do bit (geralmente, o padrão de 2048)</span><span class="sxs-lookup"><span data-stu-id="8bb9c-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="8bb9c-132">Verifique se a caixa de seleção Marcar chave privada de certificado como exportável está marcada</span><span class="sxs-lookup"><span data-stu-id="8bb9c-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="8bb9c-133">Na página informações da organização, digite o nome da organização e da unidade organizacional (por exemplo, uma divisão ou um departamento)</span><span class="sxs-lookup"><span data-stu-id="8bb9c-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="8bb9c-134">Na página informações geográficas, especifique as informações de localização</span><span class="sxs-lookup"><span data-stu-id="8bb9c-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="8bb9c-135">Na página nome do assunto/nomes alternativos de assunto, as informações a serem automaticamente preenchidas pelo assistente serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-135">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="8bb9c-136">Se forem necessários nomes alternativos de entidades adicionais, você os especificará nas duas próximas etapas</span><span class="sxs-lookup"><span data-stu-id="8bb9c-136">If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="8bb9c-137">Na configuração de domínio SIP na página de nomes alternativos de entidades (SANs), marque a caixa de seleção domínio para adicionar um SIP. \<entrada\> sipdomain para a lista de nomes alternativos de assunto.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="8bb9c-138">Na página Configurar nomes alternativos de entidades adicionais, especifique os nomes alternativos de entidades adicionais necessários</span><span class="sxs-lookup"><span data-stu-id="8bb9c-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="8bb9c-139">Se o proxy XMPP estiver instalado, por padrão, o nome de domínio (como contoso.com) será preenchido nas entradas de SAN.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-139">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="8bb9c-140">Se você precisar de mais entradas, adicione-as nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-140">If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="8bb9c-141">Na página Resumo da solicitação, examine as informações do certificado a serem usadas para gerar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="8bb9c-142">Após a conclusão da execução dos comandos, você pode exibir o log ou clicar em avançar para continuar.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="8bb9c-143">Na página arquivo de solicitação de certificado, você pode exibir o arquivo de solicitação de assinatura de certificado (CSR) gerado clicando em exibir ou em sair do assistente de certificado clicando em concluir.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="8bb9c-144">Copie o arquivo de solicitação e envie para sua autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="8bb9c-145">Depois de receber, importar e atribuir o certificado público, você deve parar e reiniciar os serviços do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-145">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="8bb9c-146">Para fazer isso, digite no console de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="8bb9c-146">You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="8bb9c-147">Para configurar o DNS para a Federação do XMPP, adicione o seguinte registro SRV para DNS\_externo: XMPP-Server. \_TCP. \<nome\> do domínio o registro SRV será resolvido para o FQDN de borda de acesso do servidor de borda, com um valor de porta de 5269.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="8bb9c-148">Além disso, você configura um registro de host ' A ' (por exemplo, xmpp.contoso.com) que aponta para o endereço IP do servidor de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8bb9c-149">Se você tiver pools de bordas em vários sites, recomendamos que adicione vários registros SRV para a Federação do XMPP.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-149">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation.</span></span> <span data-ttu-id="8bb9c-150">Adicione um registro SRV para cada pool de bordas em sua organização e dê a cada um desses registros uma prioridade diferente.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-150">Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority.</span></span> <span data-ttu-id="8bb9c-151">Quando todos os pools de bordas estiverem em execução, as solicitações de XMPP serão manipuladas pelo pool de bordas com a primeira prioridade, mas, se esse pool de bordas cair, você não terá que adicionar um novo registro SRV para recuperar a funcionalidade de Federação do XMPP.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-151">When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="8bb9c-152">Configure uma nova política de acesso externo para permitir que todos os usuários abram o Shell de gerenciamento do Lync Server no front-end e digitem:</span><span class="sxs-lookup"><span data-stu-id="8bb9c-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="8bb9c-153">Habilite o acesso do XMPP para usuários externos digitando:</span><span class="sxs-lookup"><span data-stu-id="8bb9c-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="8bb9c-154">No servidor de borda em que o proxy XMPP está implantado, abra um prompt de comando ou uma interface de linha de comando™ do Windows PowerShell e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8bb9c-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="8bb9c-155">O comando **netstat – ano** é um comando de estatísticas de rede, os parâmetros – pedido do **ano** em que o netstat exibe todas as conexões e portas de escuta, endereço e portas são exibidos em uma forma numérica e se a ID do processo de propriedade está associada a cada conexão.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="8bb9c-156">O caractere **|** define um pipe para o próximo comando, **findstr**ou localizar cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="8bb9c-157">O número 5269 e 23456 que é passado para findstr como parâmetro instrui findstr para pesquisar a saída do netstat para as cadeias de caracteres 5269 e 23456.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="8bb9c-158">Se XMPP estiver configurado corretamente, o resultado dos comandos deve resultar em conexões de escuta e estabelecidas, ambas nas interfaces externa (porta 5269) e interna (porta 23456) do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="8bb9c-159">Se os comandos não retornam portas estabelecidas ou em escuta no 5269 e no 23456, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8bb9c-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="8bb9c-160">Solução de problemas de Federação do XMPP</span><span class="sxs-lookup"><span data-stu-id="8bb9c-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="8bb9c-161">Para determinar se o proxy XMPP está em execução, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8bb9c-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="8bb9c-162">Faça logon no servidor de borda que está executando o serviço de proxy XMPP como membro do grupo administrador local.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="8bb9c-163">Clique em **Iniciar**, em **todos os programas**, em **Ferramentas administrativas**e em **Serviços**</span><span class="sxs-lookup"><span data-stu-id="8bb9c-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="8bb9c-164">Em serviços, localize o Lync Server XMPP de converter proxy de gateway.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-164">In Services, locate Lync Server XMPP Translating Gateway Proxy.</span></span> <span data-ttu-id="8bb9c-165">O serviço deve estar no estado **inicial** .</span><span class="sxs-lookup"><span data-stu-id="8bb9c-165">The service should be in the **Started** state.</span></span> <span data-ttu-id="8bb9c-166">Se não for iniciado, clique no ícone **Iniciar** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-166">If it is not started, click the **Start** icon in the toolbar.</span></span> <span data-ttu-id="8bb9c-167">O ícone aparece como uma seta verde, apontando para a direita.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-167">The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="8bb9c-168">Confirme se o serviço mudou para **iniciado**.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-168">Confirm that the service has changed to **Started**.</span></span> <span data-ttu-id="8bb9c-169">Se ele tiver começado com êxito, feche os **Serviços** e continue.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-169">If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="8bb9c-170">Se o serviço não foi iniciado com êxito, em ferramentas administrativas, abra o Visualizador de eventos e consulte os avisos e erros na parte do **Lync Server** em **logs de aplicativos e serviços**.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="8bb9c-171">Depois que o serviço do **Gateway de conversão do Lync Server XMPP** estiver em execução, verifique novamente os comandos netstat usados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="8bb9c-172">Se você não estiver vendo sessões estabelecidas ou em escuta, verifique se a **rota de Federação do XMPP** está configurada corretamente no construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="8bb9c-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="8bb9c-173">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="8bb9c-174">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="8bb9c-175">No construtor de topologias, selecione o site para a rota de Federação do XMPP e a revisão para confirmar que a **atribuição de rota de Federação do site** para a **Federação XMPP** mostra o servidor de borda ou o pool de bordas como a atribuição de rota de Federação do XMPP selecionada.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="8bb9c-176">Se a atribuição de roteiro estiver incorreta ou não estiver definida, clique com o botão direito do mouse no site e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="8bb9c-177">Marque a caixa de seleção Federação do XMPP e selecione o servidor de borda ou o pool de bordas correto.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="8bb9c-178">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-178">Publish the topology.</span></span> <span data-ttu-id="8bb9c-179">Para obter detalhes, consulte [publicar sua topologia no Lync Server 2013](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="8bb9c-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="8bb9c-180">Embora não seja necessário e normalmente não é necessário, você pode descobrir que precisará reiniciar os servidores de borda</span><span class="sxs-lookup"><span data-stu-id="8bb9c-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="8bb9c-181">Usando o processo netstat usado anteriormente, confirme se o servidor de borda agora está ouvindo ou se estabeleceu sessões na porta 5269 e na porta 23456.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="8bb9c-182">Se você ainda não estiver vendo as sessões esperadas, verifique o Visualizador de eventos para possíveis causas de contribuição para o problema de comunicação.</span><span class="sxs-lookup"><span data-stu-id="8bb9c-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8bb9c-183">Confira também</span><span class="sxs-lookup"><span data-stu-id="8bb9c-183">See Also</span></span>


[<span data-ttu-id="8bb9c-184">Exemplo de configuração de XMPP no Lync Server 2013 – federação XMPP com Google Talk</span><span class="sxs-lookup"><span data-stu-id="8bb9c-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="8bb9c-185">Gerenciar parceiros XMPP federados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bb9c-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

