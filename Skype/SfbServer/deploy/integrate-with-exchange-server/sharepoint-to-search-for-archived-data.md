---
title: Configurar o SharePoint Server para pesquisar dados arquivados do Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Resumo: Configure SharePoint Server para pesquisar dados arquivados pelo Exchange Server e do Skype para Business Server.'
ms.openlocfilehash: efd3fc67faacba503736968786988aaf01f45073
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971796"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Configurar o SharePoint Server para pesquisar dados arquivados do Skype for Business
 
**Resumo:** Configure o SharePoint Server para pesquisar dados arquivados pelo Exchange Server 2016 ou Exchange Server 2013 e Skype para Business Server.
  
Uma das principais vantagens do armazenamento de mensagens instantâneas e transcrições de conferência da Web no Exchange Server, em vez de Skype para Business Server é que o armazenamento de dados no mesmo local permite que os administradores usem uma única ferramenta para procurar dados arquivados do Exchange e/ou arquivado Skype para dados de Business Server. Porque todos os dados são armazenados no mesmo colocam (Exchange) também pode pesquisar qualquer ferramenta que pode pesquisar dados arquivados do Exchange arquivada Skype para dados de Business Server.
  
Uma ferramenta que torna fácil pesquisar dados arquivados é o Microsoft SharePoint Server 2013. Se você gostaria de usar o SharePoint para pesquisar Skype para dados de Business Server, você deve primeiro concluir todas as etapas envolvidas na configuração de arquivamento do Exchange no Skype para Business Server. Depois que o Exchange Server e do Skype para Business Server foi integrado com êxito, em seguida, instale o Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) no seu servidor do SharePoint. O arquivo baixado (EWSManagedAPI.msi) pode ser salvo em qualquer pasta do SharePoint Server.
  
Depois que o arquivo for baixado, conclua o procedimento a seguir no servidor do SharePoint:
  
1. Abra uma janela de comando clicando em **Iniciar**, **Todos os Programas**, **Acessórios**, clicando com o botão direito em **Prompt de comando**, e então clicando em **Executar como administrador**.
    
2. Na janela de comando, use o comando cd para mudar o diretório atual para a pasta onde o arquivo EWSManagedAPI.msi foi salvo. Por exemplo, se você salvou o arquivo em C:\Downloads, digite o seguinte comando na janela de comando e pressione Enter:
    
   ```
   cd C:\Downloads
   ```

3. Para instalar a API, digite o seguinte comando e pressione Enter:
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Após a API tenha sido instalada, redefina o IIS digitando o seguinte comando e pressionando Enter:
    
   ```
   iisreset
   ```

Após a instalação do Exchange Web Services, em seguida, você deve configurar a autenticação de servidor-para-servidor entre o SharePoint Server e o Exchange Server. Para fazer isso, abra o Shell de gerenciamento do SharePoint e execute o seguinte conjunto de comandos:
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Certifique-se de usar o URI para seu serviço de descoberta automática. Não use o exemplo de URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1. 
  
Depois de ter criado o emissor de token e configurado o serviço de token, execute estes comandos, certificando-se de substituir a URL do seu site do SharePoint para a URL de exemplohttp://atl-sharepoint-001:
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Para configurar a autenticação de servidor-para-servidor para o Exchange Server, abra o Shell de gerenciamento do Exchange e execute um comando semelhante ao seguinte (supondo que o Exchange foi instalado na unidade c: e que ele usa o caminho da pasta padrão):
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Depois de configurar o aplicativo parceiro é recomendável que você parar e reiniciar os serviços de informações da Internet (IIS) em todos os Exchange mailbox e cliente access servidores. Você pode reiniciar o IIS usando um comando similar a esse, que reinicia o serviço no atl-exchange-001 do computador:
  
```
iisreset atl-exchange-001
```

Este comando pode ser executado de dentro do Shell de gerenciamento do Exchange ou de qualquer outra janela de comando.
  
Em seguida, execute um comando semelhante ao seguinte, que permite o usuário especificado (neste exemplo, kenmyer) o direito de fazer descoberta no Exchange:
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Depois que tiver sido estabelecida a autenticação de servidor-para-servidor entre o Exchange e SharePoint, sua próxima etapa é criar um site de descoberta eletrônica no SharePoint. Que pode ser feito executando comandos semelhantes a estas do Shell de gerenciamento do SharePoint:
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> "eDiscovery" é uma abreviação de "electronic discovery (descoberta eletrônica)", e normalmente se refere ao processo de pesquisa por itens em arquivos eletrônicos, que possa ser "razoavelmente calculada para levar a provas admissíveis" em tribunal judicial. 
  
Quando o novo site estiver pronto, a próxima etapa é configurar o Exchange Server para atuar como resultado fonte para SharePoint. Você pode fazer isso, completando o procedimento a seguir na página Administração Central do SharePoint:
  
1. Na página de Administração Central, clique em **Gerenciar Aplicativos de Serviço** e então clique em **Aplicativo de Serviço de Pesquisa**.
    
2. Na página Aplicativo de Serviço de Pesquisa: Administração de Pesquisa, clique em **Fontes de Resultado** e então clique em **Nova Fonte de Resultado**.
    
3. No painel **Nova Fonte de Resultado** insira um nome para a nova fonte de resultado (por exemplo, **Microsoft Exchange**) na caixa **Nome**. Selecione **Exchange** como a fonte de resultados **protocolo**e digite a URL de origem de serviços da web para seu servidor do Exchange na caixa **URL de origem do Exchange** . A URL da fonte deve parecer com esta:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Certifique-se de que **Usar Descoberta Automática** não está selecionado e então clique em **OK**.
    
Finalmente, crie um novo caso de descoberta eletrônica e um novo eDiscovery definido, completando o procedimento a seguir do site do SharePoint de descoberta (por exemplo,https://atl-sharepoint-001/sites/discovery):
  
1. Na página de Conteúdos do Site clique em **Criar um novo caso**.
    
2. Na página Conteúdos do Site: Novo Site do SharePoint, insira o alias do email do usuário (por exemplo, **kenmyer**) na caixa **Título**, então adicione esta mesma URL à caixa **Endereço do Site**. Isso resultará em uma URL similar a esta:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Clique em **Criar**.
    
4. Quando a página de conjunto de descoberta eletrônica aparecer, clique em **novo item** sob **Identidade e Preservação: Conjuntos de Descoberta**.
    
5. Na página Novo: Conjunto de Descoberta, insira o alias do email do usuário na caixa **Nome do Conjunto de Descoberta**. Insira **eDiscovery Lync\* ** no **filtro** caixa e, em seguida, clique em **Add &amp; gerenciar fontes**.
    
6. Em Adicionar &amp; gerenciar fontes de página, insira o alias de email do usuário na primeira caixa de texto em **caixas de correio**. Clique no ícone de verificação da caixa de correio ao lado da caixa de texto para verificar se o SharePoint consegue se conectar à caixa de correio especificada.
    
7. Clique em **OK**.
    
8. Na página do conjunto de descoberta eletrônica, clique em **Salvar** para salvar o novo conjunto de descoberta eletrônica.
    
Neste ponto, você pode pesquisar a caixa de correio especificada (kenmyer) e/ou enable In-Place holds da mesma maneira que faria para qualquer outra SharePoint resultados ou conteúdo fonte.
  

