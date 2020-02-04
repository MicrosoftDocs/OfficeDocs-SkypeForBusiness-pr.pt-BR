---
title: 'Lync Server 2013: Configurando o Microsoft SharePoint Server 2013 para pesquisar dados arquivados do Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e000f6116b112b3de9840c22c29510745303035
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>Configurando o Microsoft SharePoint Server 2013 para pesquisar dados do Microsoft Lync Server 2013 arquivados

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-04_

Uma das principais vantagens de armazenar mensagens instantâneas e transcrições de webconferências no Microsoft Exchange Server 2013 em vez do Microsoft Lync Server 2013 é o fato de que armazenar dados no mesmo local permite que os administradores usem uma única ferramenta para pesquisar dados do Exchange arquivados e/ou dados do Lync Server arquivados. Como todos os dados são armazenados no mesmo lugar (Exchange), qualquer ferramenta que possa pesquisar dados do Exchange arquivado também pode procurar por dados arquivados do Lync Server.

Uma ferramenta que torna mais fácil pesquisar dados arquivados é o Microsoft SharePoint Server 2013. Se quiser usar o SharePoint para pesquisar dados do Lync Server, primeiro você deve concluir todas as etapas envolvidas na configuração do arquivamento do Exchange no Lync Server. Após o Exchange 2013 e o Lync Server 2013 terem sido integrados com sucesso, você deve instalar a versão 2,0 da API gerenciada dos serviços Web do Exchange no seu servidor do SharePoint; o programa de instalação dessa API pode ser baixado a partir do centro de download[http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)da Microsoft (). O arquivo baixado (EWSManagedAPI.msi) pode ser salvo em qualquer pasta do SharePoint Server.

Depois que o arquivo for baixado, conclua o procedimento a seguir no servidor do SharePoint:

1.  Abra uma janela de comando clicando em **Iniciar**, **Todos os Programas**, **Acessórios**, clicando com o botão direito em **Prompt de comando**, e então clicando em **Executar como administrador**.

2.  Na janela de comando, use o comando **cd** para mudar o diretório atual para a pasta onde o arquivo EWSManagedAPI.msi foi salvo. Por exemplo, se você salvou o arquivo em C:\\downloads, digite o seguinte comando na janela de comando e pressione ENTER:
    
        cd C:\Downloads

3.  Para instalar a API, digite o comando a seguir e então pressione ENTER:
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  Depois que a API for instalada, reinicie o IIS digitando o seguinte comando e pressionando ENTER:
    
        iisreset

Após a instalação do Exchange Web Services, você deve configurar a autenticação de servidor para servidor entre o SharePoint Server 2013 e o Exchange 2013. Para fazer isso, primeiro abra o Shell de gerenciamento do SharePoint 2013 e execute o seguinte conjunto de comandos:

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> Certifique-se de usar o URI para seu serviço de descoberta automática. Não use o URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1de exemplo.



</div>

Depois de criar o emissor do token e configurar o serviço de token, execute esses comandos, substituindo a URL do seu site do SharePoint pela URL de exemplohttp://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Para configurar a autenticação de servidor para servidor para o Exchange 2013, abra o Shell de gerenciamento do Exchange e execute um comando semelhante a isso (pressupondo que o Exchange tenha sido instalado na unidade C: e que ele use o caminho de pasta padrão):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

Depois de configurar o aplicativo de parceiro, é recomendável parar e reiniciar os serviços de informações da Internet (IIS) em todos os servidores de caixa de correio do Exchange e de acesso para cliente. Você pode reiniciar o IIS usando um comando similar a esse, que reinicia o serviço no atl-exchange-001 do computador:

    iisreset atl-exchange-001

Esse comando pode ser executado de dentro do Shell de gerenciamento do Exchange ou de qualquer outra janela de comando.

Em seguida, execute um comando semelhante ao seguinte, que fornece ao usuário especificado (neste exemplo, kenmyer) o direito de fazer a descoberta no Exchange:

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

Após o estabelecimento da autenticação de servidor para servidor entre o Exchange e o SharePoint, a próxima etapa é criar um site de descoberta eletrônica no SharePoint. Isso pode ser feito executando-se comandos semelhantes aos do Shell de gerenciamento do SharePoint:

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> "eDiscovery" é uma abreviação de "electronic discovery (descoberta eletrônica)", e normalmente se refere ao processo de pesquisa por itens em arquivos eletrônicos, que possa ser "razoavelmente calculada para levar a provas admissíveis" em tribunal judicial.



</div>

Quando o novo site estiver pronto, a próxima etapa é configurar o Exchange 2013 para atuar como uma fonte de resultados para o SharePoint. Você pode fazer isso completando o seguinte procedimento na página Administração Central do SharePoint 2013:

1.  Na página de Administração Central, clique em **Gerenciar Aplicativos de Serviço** e então clique em **Aplicativo de Serviço de Pesquisa**.

2.  Na página Aplicativo de Serviço de Pesquisa: Administração de Pesquisa, clique em **Fontes de Resultado** e então clique em **Nova Fonte de Resultado**.

3.  No painel **Nova Fonte de Resultado** insira um nome para a nova fonte de resultado (por exemplo, **Microsoft Exchange**) na caixa **Nome**. Selecione **Exchange** como o **protocolo**de origem do resultado e, em seguida, insira a URL da fonte de serviços Web para o seu servidor Exchange na caixa **URL de origem do Exchange** . A URL da fonte deve parecer com esta:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  Certifique-se de que **Usar Descoberta Automática** não está selecionado e então clique em **OK**.

Por fim, crie um novo caso de descoberta eletrônica e um novo conjunto de descobertas eletrônicas completando o procedimento a seguir no site de descoberta do SharePoint (por exemplo,https://atl-sharepoint-001/sites/discovery):

1.  Na página de Conteúdos do Site clique em **Criar um novo caso**.

2.  Na página Conteúdos do Site: Novo Site do SharePoint, insira o alias do email do usuário (por exemplo, **kenmyer**) na caixa **Título**, então adicione esta mesma URL à caixa **Endereço do Site**. Isso resultará em uma URL similar a esta:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  Clique em **Criar**.

4.  Quando a página de conjunto de descoberta eletrônica aparecer, clique em **novo item** sob **Identidade e Preservação: Conjuntos de Descoberta**.

5.  Na página Novo: Conjunto de Descoberta, insira o alias do email do usuário na caixa **Nome do Conjunto de Descoberta**. Digite **Lync\* do descoberta eletrônica** na caixa **filtro** e clique em **Adicionar & gerenciar fontes**.

6.  Na página Adicionar e Gerenciar Fontes, insira o alias do email do usuário na primeira caixa de texto sob **Caixas de correio**. Clique no ícone de verificação da caixa de correio ao lado da caixa de texto para verificar se o SharePoint consegue se conectar à caixa de correio especificada.

7.  Clique em **OK**.

8.  Na página do conjunto de descoberta eletrônica, clique em **Salvar** para salvar o novo conjunto de descoberta eletrônica.

Nesse ponto, você pode pesquisar a caixa de correio especificada (kenmyer) e/ou habilitar no local suspensões da mesma maneira que faria para qualquer outro conteúdo do SharePoint ou fonte de resultados.

</div>

<span> </span>

</div>

</div>

</div>

