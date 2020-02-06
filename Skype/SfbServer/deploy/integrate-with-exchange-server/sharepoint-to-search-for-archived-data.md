---
title: Configurar o SharePoint Server para pesquisar dados arquivados do Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Resumo: configurar o SharePoint Server para pesquisar dados arquivados pelo Exchange Server e pelo Skype for Business Server.'
ms.openlocfilehash: 1ca6ee7f398ddc8e0d9b8d51658dd65556225490
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797012"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Configurar o SharePoint Server para pesquisar dados arquivados do Skype for Business
 
**Resumo:** Configure o SharePoint Server para pesquisar dados arquivados pelo Exchange Server 2016 ou pelo Exchange Server 2013 e pelo Skype for Business Server.
  
Uma das principais vantagens de armazenar mensagens de chat e transcrições de webconferências no Exchange Server, em vez do Skype for Business Server, é que armazenar dados no mesmo local permite que os administradores usem uma única ferramenta para pesquisar dados do Exchange arquivados e/ou dados arquivados do Skype for Business Server. Como todos os dados são armazenados no mesmo lugar (Exchange), qualquer ferramenta que possa pesquisar dados do Exchange arquivado também pode procurar por dados arquivados do Skype for Business Server.
  
Uma ferramenta que torna mais fácil pesquisar dados arquivados é o Microsoft SharePoint Server 2013. Se quiser usar o SharePoint para pesquisar dados do Skype for Business Server, primeiro você deve concluir todas as etapas envolvidas na configuração do arquivamento do Exchange no Skype for Business Server. Após a integração do Exchange Server e do Skype for Business Server, você deve instalar a [API gerenciada dos serviços Web](https://go.microsoft.com/fwlink/p/?LinkId=258305) do Exchange no seu servidor do SharePoint. O arquivo baixado (EWSManagedAPI.msi) pode ser salvo em qualquer pasta do SharePoint Server.
  
Depois que o arquivo for baixado, conclua o procedimento a seguir no servidor do SharePoint:
  
1. Abra uma janela de comando clicando em **Iniciar**, **Todos os Programas**, **Acessórios**, clicando com o botão direito em **Prompt de comando**, e então clicando em **Executar como administrador**.
    
2. Na janela de comando, use o comando cd para mudar o diretório atual para a pasta onde o arquivo EWSManagedAPI.msi foi salvo. Por exemplo, se você salvou o arquivo no C:\Downloads digite o seguinte comando na janela de comando e pressione ENTER:
    
   ```console
   cd C:\Downloads
   ```

3. Para instalar a API, digite o seguinte comando e pressione ENTER:
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Após instalar a API, redefina o IIS digitando o seguinte comando e pressionando ENTER:
    
   ```console
   iisreset
   ```

Após a instalação do Exchange Web Services, você deve configurar a autenticação de servidor para servidor entre o SharePoint Server e o Exchange Server. Para fazer isso, primeiro abra o Shell de gerenciamento do SharePoint e execute o seguinte conjunto de comandos:
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Certifique-se de usar o URI para seu serviço de descoberta automática. Não use o URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1de exemplo. 
  
Depois de criar o emissor do token e configurar o serviço de token, execute esses comandos, substituindo a URL do seu site do SharePoint pela URL de exemplohttp://atl-sharepoint-001:
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Para configurar a autenticação de servidor para servidor para o Exchange Server, abra o Shell de gerenciamento do Exchange e execute um comando semelhante a isso (pressupondo que o Exchange tenha sido instalado na unidade C: e que ele use o caminho de pasta padrão):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Depois de configurar o aplicativo de parceiro, é recomendável parar e reiniciar os serviços de informações da Internet (IIS) em todos os servidores de caixa de correio do Exchange e de acesso para cliente. Você pode reiniciar o IIS usando um comando similar a esse, que reinicia o serviço no atl-exchange-001 do computador:
  
```powershell
iisreset atl-exchange-001
```

Esse comando pode ser executado de dentro do Shell de gerenciamento do Exchange ou de qualquer outra janela de comando.
  
Em seguida, execute um comando semelhante ao seguinte, que fornece ao usuário especificado (neste exemplo, kenmyer) o direito de fazer a descoberta no Exchange:
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Após o estabelecimento da autenticação de servidor para servidor entre o Exchange e o SharePoint, a próxima etapa é criar um site de descoberta eletrônica no SharePoint. Isso pode ser feito executando-se comandos semelhantes aos do Shell de gerenciamento do SharePoint:
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> "eDiscovery" é uma abreviação de "electronic discovery (descoberta eletrônica)", e normalmente se refere ao processo de pesquisa por itens em arquivos eletrônicos, que possa ser "razoavelmente calculada para levar a provas admissíveis" em tribunal judicial. 
  
Quando o novo site estiver pronto, a próxima etapa é configurar o Exchange Server para atuar como uma fonte de resultados para o SharePoint. Você pode fazer isso completando o seguinte procedimento na página Administração Central do SharePoint:
  
1. Na página de Administração Central, clique em **Gerenciar Aplicativos de Serviço** e então clique em **Aplicativo de Serviço de Pesquisa**.
    
2. Na página Aplicativo de Serviço de Pesquisa: Administração de Pesquisa, clique em **Fontes de Resultado** e então clique em **Nova Fonte de Resultado**.
    
3. No painel **Nova Fonte de Resultado** insira um nome para a nova fonte de resultado (por exemplo, **Microsoft Exchange**) na caixa **Nome**. Selecione **Exchange** como o **protocolo**de origem do resultado e, em seguida, insira a URL da fonte de serviços Web para o seu servidor Exchange na caixa **URL de origem do Exchange** . A URL da fonte deve parecer com esta:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Certifique-se de que **Usar Descoberta Automática** não está selecionado e então clique em **OK**.
    
Por fim, crie um novo caso de descoberta eletrônica e um novo conjunto de descobertas eletrônicas completando o procedimento a seguir no site de descoberta do SharePoint (por exemplo,https://atl-sharepoint-001/sites/discovery):
  
1. Na página de Conteúdos do Site clique em **Criar um novo caso**.
    
2. Na página Conteúdos do Site: Novo Site do SharePoint, insira o alias do email do usuário (por exemplo, **kenmyer**) na caixa **Título**, então adicione esta mesma URL à caixa **Endereço do Site**. Isso resultará em uma URL similar a esta:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Clique em **Criar**.
    
4. Quando a página de conjunto de descoberta eletrônica aparecer, clique em **novo item** sob **Identidade e Preservação: Conjuntos de Descoberta**.
    
5. Na página Novo: Conjunto de Descoberta, insira o alias do email do usuário na caixa **Nome do Conjunto de Descoberta**. Digite **Lync\\do descoberta eletrônica*** na caixa **filtro** e clique **em &amp; adicionar gerenciar fontes**.
    
6. Na página Adicionar &amp; gerenciar fontes, insira o alias de email do usuário na primeira caixa de texto em **caixas de correio**. Clique no ícone de verificação da caixa de correio ao lado da caixa de texto para verificar se o SharePoint consegue se conectar à caixa de correio especificada.
    
7. Clique em **OK**.
    
8. Na página do conjunto de descoberta eletrônica, clique em **Salvar** para salvar o novo conjunto de descoberta eletrônica.
    
Nesse ponto, você pode pesquisar a caixa de correio especificada (kenmyer) e/ou habilitar no local suspensões da mesma maneira que faria para qualquer outro conteúdo do SharePoint ou fonte de resultados.
  

