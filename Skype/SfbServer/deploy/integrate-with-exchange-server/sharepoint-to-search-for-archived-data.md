---
title: Configurar o SharePoint Server para pesquisar dados arquivados do Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: Configure o SharePoint Server para pesquisar dados arquivados pelo Exchange Server e pelo Skype for Business Server.'
ms.openlocfilehash: 406e0a713c65bc147ce6eb492f251a25ea2a3afc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833941"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Configurar o SharePoint Server para pesquisar dados arquivados do Skype for Business
 
**Resumo:** Configure o SharePoint Server para pesquisar dados arquivados pelo Exchange Server 2016 ou Exchange Server 2013 e pelo Skype for Business Server.
  
Uma das principais vantagens de armazenar transcrições de mensagens instantâneas e webconferências no Exchange Server em vez do Skype for Business Server é que o armazenamento de dados no mesmo local permite que os administradores usem uma única ferramenta para pesquisar dados arquivados do Exchange e/ou dados arquivados do Skype for Business Server. Como todos os dados são armazenados no mesmo local (Exchange), qualquer ferramenta que possa pesquisar dados arquivados do Exchange também pode pesquisar por dados arquivados do Skype for Business Server.
  
Uma ferramenta que facilita a pesquisa de dados arquivados é o Microsoft SharePoint Server 2013. Se você quiser usar o SharePoint para pesquisar dados do Skype for Business Server, primeiro deverá concluir todas as etapas envolvidas na configuração do arquivamento do Exchange no Skype for Business Server. Depois que o Exchange Server e o Skype for Business Server foram integrados com êxito, você deve instalar a API Gerenciada dos [Serviços Web](https://go.microsoft.com/fwlink/p/?LinkId=258305) do Exchange em seu SharePoint Server. O arquivo baixado (EWSManagedAPI.msi) pode ser salvo em qualquer pasta no seu servidor do SharePoint.
  
Após o arquivo ter sido baixado, complete o procedimento a seguir no servidor do SharePoint:
  
1. Abra uma janela de comando clicando em **Iniciar**, clicando em **Todos os Programas**, clicando em **Acessórios**, clicando com o botão direito em **Prompt de comando**, e então clicando em **Executar como administrador**.
    
2. Na janela de comando, use o comando cd mada mudar o diretório atual para a pasta onde o arquivo EWSManagedAPI.msi foi salvo. Por exemplo, se você salvou o arquivo em C:\Downloads, digite o seguinte comando na janela de comando e pressione Enter:
    
   ```console
   cd C:\Downloads
   ```

3. Para instalar a API, digite o seguinte comando e pressione Enter:
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Depois que a API tiver sido instalada, redefinir o IIS digitando o seguinte comando e pressionando Enter:
    
   ```console
   iisreset
   ```

Após a instalação dos Serviços Web do Exchange, você deve configurar a autenticação de servidor para servidor entre o SharePoint Server e o Exchange Server. Para fazer isso, abra primeiro o Shell de Gerenciamento do SharePoint e execute o seguinte conjunto de comandos:
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Tenha certeza de qual é o URI para seu serviço de descoberta automática e o use. Não use o URI de https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 exemplo. 
  
Depois de criar o emissor do token e configurar o serviço de token, execute estes comandos, substituindo a URL do seu site do SharePoint pela URL de exemplo http://atl-sharepoint-001:
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Para configurar a autenticação de servidor para servidor para o Exchange Server, abra o Shell de Gerenciamento do Exchange e execute um comando semelhante a este (supondo que o Exchange tenha sido instalado na unidade C: e que ele use o caminho de pasta padrão):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Depois de configurar o aplicativo parceiro, é recomendável que você pare e reinicie os Serviços de Informações da Internet (IIS) em todos os servidores de acesso para cliente e caixa de correio do Exchange. Você pode reiniciar o IIS usando um comando similar a este, que reinicia o serviço no computador atl-exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Esse comando pode ser executado de dentro do Shell de Gerenciamento do Exchange ou de qualquer outra janela de comando.
  
Em seguida, execute um comando semelhante ao seguinte, que concede ao usuário especificado (neste exemplo, kenmyer) o direito de fazer descoberta no Exchange:
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Depois que a autenticação de servidor para servidor tiver sido estabelecida entre o Exchange e o SharePoint, sua próxima etapa será criar um site de Descoberta eDiscovery no SharePoint. Isso pode ser feito executando comandos semelhantes a estes do Shell de Gerenciamento do SharePoint:
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> "eDiscovery" é uma abreviação de "electronic discovery (descoberta eletrônica)", e normalmente se refere ao processo de pesquisa por itens em arquivos eletrônicos, que possa ser "razoavelmente calculada para levar a provas admissíveis" em tribunal judicial. 
  
Quando o novo site estiver pronto, a próxima etapa é configurar o Exchange Server para agir como uma fonte de resultados para o SharePoint. Você pode fazer isso concluindo o procedimento a seguir na página da Administração Central do SharePoint:
  
1. Na página de Administração Central, clique em **Gerenciar Aplicativos de Serviço** e então clique em **Aplicativo de Serviço de Pesquisa**.
    
2. Na página Aplicativo de Serviço de Pesquisa: Administração de Pesquisa, clique em **Fontes de Resultado** e então clique em **Nova Fonte de Resultado**.
    
3. No painel **Nova Fonte de Resultado** insira um nome para a nova fonte de resultado (por exemplo, **Microsoft Exchange**) na caixa **Nome**. Selecione **Exchange como** o protocolo de fonte de resultados e insira a URL de origem de serviços Web para seu servidor Exchange na caixa URL de **origem do Exchange.**  A URL da fonte deve parecer com esta:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Assegure-se de que **Usar Descoberta Automática** não está selecionado, e então clique em **OK**.
    
Por fim, crie um novo caso de Descoberta e um novo conjunto de Descobertas De eDiscovery concluindo o procedimento a seguir no site de Descoberta do SharePoint (por exemplo, https://atl-sharepoint-001/sites/discovery):
  
1. Na página de Conteúdos do Site clique em **Criar um novo caso**.
    
2. Na página Conteúdos do Site: Novo Site do SharePoint, insira o alias do email do usuário (por exemplo, **kenmyer**) na caixa **Título**, então adicione esta mesma URL à caixa **Endereço do Site**. Isso resultará em uma URL similar a esta:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Clique em **Criar**.
    
4. Quando a página de conjunto de descoberta eletrônica aparecer, clique em **novo item** sob **Identidade e Preservação: Conjuntos de Descoberta**.
    
5. Na página Novo: Conjunto de Descoberta, insira o alias do email do usuário na caixa **Nome do Conjunto de Descoberta**. Enter **eDiscovery Lync \\** _ in the _ *Filter** box and then click Add Manage **&amp; Sources**.
    
6. Na página Adicionar Fontes Gerenciadas, insira o alias de email do usuário na &amp; primeira caixa de texto em Caixas de **Correio.** Clique no ícone de verificação da caixa de correio ao lado da caixa de texto para verificar que o SharePoint consegue se conectar à caixa de correio especificada.
    
7. Clique em **OK**.
    
8. Na página do conjunto de descoberta eletrônica, clique em **Salvar** para salvar o novo conjunto de descoberta eletrônica.
    
Neste ponto, você pode pesquisar a caixa de correio especificada (kenmyer) e/ou habilitar In-Place retém da mesma forma que faria para qualquer outra fonte de resultados ou conteúdo do SharePoint.
  

