---
title: 'Lync Server 2013: Configurando Federação XMPP'
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
ms.openlocfilehash: b6cbe8db6b432f8e837e110875881e86adab9c51
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="d6c2d-102">Configurando a Federação XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6c2d-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6c2d-103">_**Última modificação do tópico:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="d6c2d-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="d6c2d-p101">Para implantar o proxy XMPP no servidor de borda, você deve configurar o servidor de borda para a federação XMPP. Para isso, execute as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-p101">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation. To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="d6c2d-106">Configurando a XMPP</span><span class="sxs-lookup"><span data-stu-id="d6c2d-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="d6c2d-107">Faça logon no computador onde o assistente de implantação do Lync Server está instalado como um membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d6c2d-p102">No servidor front-end, abra o Assistente para Implantação do Lync Server. Clique em Instalar ou Atualizar o Sistema do Lync Server e depois em Instalar ou Remover os Componentes de Servidor do Lync Server. Clique em Executar Novamente.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-p102">On the Front End server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

3.  <span data-ttu-id="d6c2d-p103">Em Componentes de Configuração Lync Server, clique em Próxima. A tela de resumo mostrará as ações conforme forem executadas. Quando a implantação for concluída, clique em Exibir Log para ver os arquivos de log disponíveis. Clique em Concluir para finalizar a implantação.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-p103">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="d6c2d-p104">No servidor front-end, abra o Assistente para Implantação do Lync Server. Clique em Instalar ou Atualizar o Sistema do Lync Server e depois em Instalar ou Remover os Componentes de Servidor do Lync Server. Clique em Executar Novamente.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-p104">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="d6c2d-p105">Em Instalar componentes do Lync Server, clique em Avançar. A tela de resumo mostrará as ações à medida que forem executadas. Após a conclusão da implantação, clique em Exibir Log para exibir os arquivos de log disponíveis. Clique em Concluir para finalizar a implantação.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-p105">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="d6c2d-122">No servidor de borda, no Assistente para Implantação, ao lado da Etapa 3: Solicitar, Instalar ou Ceder Certificados, clique em Executar Novamente.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="d6c2d-123">Se você estiver implantando o servidor de borda pela primeira vez, verá Executar em vez de Executar Novamente.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="d6c2d-124">Na página Tarefas de Certificado Disponíveis, clique em Criar uma nova solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="d6c2d-125">Na página solicitação de certificado, clique em certificado de borda externa.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="d6c2d-126">Na página Solicitação Atrasada ou Imediata, marque a caixa de seleção Preparar a solicitação agora, mas enviá-la mais tarde.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="d6c2d-127">Na página arquivo de solicitação de certificado, digite o caminho completo e o nome do arquivo para o qual a solicitação será salva (por exemplo, c:\\CERT\_externos\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="d6c2d-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="d6c2d-128">Na página Especificar Modelo de Certificado Alternativo, para usar um modelo diferente do modelo WebServer padrão, marque a caixa de seleção Usar modelo de certificado alternativo para a autoridade de certificação selecionada.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="d6c2d-129">Na página Nome e Configurações de Segurança, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="d6c2d-130">Em Nome Amigável, digite um nome de exibição para o certificado.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="d6c2d-131">Em Comprimento de bit, especifique o comprimento de bit (normalmente o padrão de 2048).</span><span class="sxs-lookup"><span data-stu-id="d6c2d-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="d6c2d-132">Verifique se a caixa de seleção Marcar chave privada de certificado como exportável está marcada.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="d6c2d-133">Na página Informações da Organização, digite o nome da organização e a unidade organizacional (por exemplo, uma divisão ou um departamento).</span><span class="sxs-lookup"><span data-stu-id="d6c2d-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="d6c2d-134">Na página Informações Geográficas, especifique as informações de localização.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="d6c2d-p106">Na página Nome da Entidade/Nomes Alternativos da Entidade, as informações a serem preenchidas automaticamente pelo assistente são exibidas. Se nomes alternativos de entidade adicionais forem necessários, especifique-os nas próximas duas etapas.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-p106">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="d6c2d-137">Na página configuração do domínio SIP em nomes alternativos da entidade (SANs), marque a caixa de seleção domínio para adicionar um SIP. \<entrada\> sipdomain para a lista de nomes alternativos de entidade.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="d6c2d-138">Na página Configurar Nomes Alternativos da Entidade Adicionais, especifique os nomes alternativos de entidade adicionais que sejam necessários.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="d6c2d-p107">Se o proxy XMPP estiver instalado, o nome do domínio (por exemplo, contoso.com) será preenchido nas entradas de SAN por padrão. Se mais entradas forem necessárias, adicione-as nessa etapa.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-p107">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="d6c2d-141">Na página Resumo da Solicitação, examine as informações de certificado a serem usadas para gerar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="d6c2d-142">Após a conclusão da execução dos comandos, você poderá exibir o log ou clicar em Avançar para continuar.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="d6c2d-143">Na página Arquivo de Solicitação de Certificado, você pode exibir o arquivo de solicitação de assinatura de certificado (CSR) gerado clicando em Exibir ou fechar o Assistente de Certificado clicando em Concluir.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="d6c2d-144">Copie o arquivo de solicitação e envie-o para sua autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="d6c2d-p108">Após receber, importar e atribuir o certificado público, você deve parar e reiniciar os serviços do Servidor de Borda. Você faz isso digitando no console do Gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-p108">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="d6c2d-147">Para configurar o DNS para Federação XMPP, adicione o seguinte registro SRV ao DNS externo:\_XMPP-Server. \_TCP. \<nome\> do domínio o registro SRV resolverá o FQDN de borda de acesso do servidor de borda, com um valor de porta de 5269.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="d6c2d-148">Além disso, configure um registro de host "A" (por exemplo, xmpp.contoso.com) que aponte para o endereço IP do servidor de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d6c2d-p110">Se você tiver pools de borda em vários sites, é recomendável que adicione vários registros SRV para federação XMPP. Adicione um registro SRV para cada pool de borda de sua organização e atribua a cada um desses registros SRV uma prioridade diferente. Quando todos os pools de borda estiverem em execução, as solicitações XMPP serão todas manipuladas pelo pool de borda com a maior prioridade, mas, se esse pool de borda ficar inoperante, você não precisará adicionar um novo registro SRV para recuperar a funcionalidade de federação XMPP.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-p110">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation. Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority. When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="d6c2d-152">Configure uma nova política de acesso externo para habilitar todos os usuários abrindo o Shell de Gerenciamento do Lync Server no front-end e digitando:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="d6c2d-153">Habilite o acesso XMPP para usuários externos digitando:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="d6c2d-154">No servidor de borda onde o proxy XMPP está implantado, abra um prompt de comando ou uma interface de linha de comando do Windows PowerShell™ e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="d6c2d-155">O comando **netstat – ano** é um comando de estatísticas de rede, a solicitação de parâmetros **– ano** em que netstat exibe todas as conexões e portas de escuta, address e Ports são exibidos em um formato numérico e que a ID de processo de propriedade é associada a cada conexão.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="d6c2d-156">O caractere **|** define um pipe para o próximo comando, **findstr**ou localizar cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="d6c2d-157">O número 5269 e 23456 que é passado para findstr como um parâmetro instrui o findstr a Pesquisar a saída do netstat para as cadeias de caracteres 5269 e 23456.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="d6c2d-158">Se o XMPP estiver configurado corretamente, o resultado dos comandos deverá resultar em conexões estabelecidas e estabelecidas, tanto na interface externa (porta 5269) quanto nas interfaces internas (porta 23456) do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="d6c2d-159">Se os comandos não retornarem as portas estabelecidas ou de escuta em 5269 e 23456, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="d6c2d-160">Solucionando problemas da federação XMPP</span><span class="sxs-lookup"><span data-stu-id="d6c2d-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="d6c2d-161">Para determinar se o proxy XMPP está em execução, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="d6c2d-162">Faça logon no servidor de borda que está executando o serviço do proxy XMPP como membro do grupo de administrador local.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="d6c2d-163">Clique em **Iniciar**, em **Todos os Programas**, em **Ferramentas Administrativas** e em **Serviços**</span><span class="sxs-lookup"><span data-stu-id="d6c2d-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="d6c2d-p112">Em Serviços, localize Proxy do Gateway de Tradução XMPP do Lync Server. O serviço deverá estar no estado **Iniciado**. Se ele não estiver iniciado, clique no ícone **Iniciar** na barra de ferramentas. O ícone se parece com uma seta verde apontando para a direita.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-p112">In Services, locate Lync Server XMPP Translating Gateway Proxy. The service should be in the **Started** state. If it is not started, click the **Start** icon in the toolbar. The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="d6c2d-p113">Confirme se o serviço mudou para **Iniciado**. Se ele tiver sido iniciado com êxito, feche **Serviços** e continue o procedimento.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-p113">Confirm that the service has changed to **Started**. If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="d6c2d-170">Se o serviço não tiver sido iniciado com êxito, nas Ferramentas Administrativas, abra o Visualizador de Eventos e consulte os erros e avisos na parte **Lync Server** em **Logs de Aplicativos e Serviços**.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="d6c2d-171">Depois que o serviço **Proxy do Gateway de Tradução XMPP do Lync Server** estiver em execução, verifique novamente os comandos netstat usados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="d6c2d-172">Se você não estiver vendo sessões estabelecidas ou de escuta, verifique se a **rota de Federação do XMPP** está configurada corretamente no construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="d6c2d-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="d6c2d-173">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="d6c2d-174">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="d6c2d-175">No construtor de topologias, selecione o site para a rota de Federação do XMPP e revise para confirmar que a **atribuição de rota de Federação do site** para a **Federação XMPP** mostra o servidor de borda ou o pool de borda como a atribuição de rota de Federação do XMPP selecionada.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="d6c2d-176">Se a atribuição de rota estiver incorreta ou não estiver definida, clique com o botão direito do mouse no site e depois em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="d6c2d-177">Marque a caixa de seleção Federação XMPP e, em seguida, selecione o servidor de borda ou o pool de borda correto.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="d6c2d-178">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-178">Publish the topology.</span></span> <span data-ttu-id="d6c2d-179">Para obter detalhes, consulte [Publish Your Topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="d6c2d-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="d6c2d-180">Embora não seja obrigatório e normalmente não seja necessário, você pode precisar reiniciar os servidores de borda</span><span class="sxs-lookup"><span data-stu-id="d6c2d-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="d6c2d-181">Usando o processo netstat usado anteriormente, confirme se o servidor de borda agora está escutando ou estabeleceu sessões na porta 5269 e na porta 23456.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="d6c2d-182">Se as sessões esperadas ainda não forem exibidas, verifique o Visualizador de Eventos para ver se há possíveis causas para o problema de comunicação.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6c2d-183">Confira também</span><span class="sxs-lookup"><span data-stu-id="d6c2d-183">See Also</span></span>


[<span data-ttu-id="d6c2d-184">Exemplo de configuração de XMPP no Lync Server 2013 – Federação do XMPP com Google Talk</span><span class="sxs-lookup"><span data-stu-id="d6c2d-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="d6c2d-185">Gerenciar parceiros federados do XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6c2d-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

