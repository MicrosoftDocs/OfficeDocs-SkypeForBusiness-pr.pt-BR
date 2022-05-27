---
title: Implantar Gerenciador de Estatísticas do Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Resumo: Leia este tópico para saber como implantar o Gerenciador de Estatísticas para Skype for Business Server.'
ms.openlocfilehash: 1debe0c38b3e3df0b6be193e892991c09e15fb61
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675983"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Implantar Gerenciador de Estatísticas do Skype for Business Server

**Resumo:** Leia este tópico para saber como implantar o Gerenciador de Estatísticas para Skype for Business Server.

 O Gerenciador de Estatísticas para Skype for Business Server é uma ferramenta poderosa que permite exibir Skype for Business Server dados de desempenho e integridade em tempo real. Você pode sondar dados de desempenho em centenas de servidores a cada poucos segundos e exibir os resultados instantaneamente no site do Gerenciador de Estatísticas.

Antes de tentar instalar o Gerenciador de Estatísticas, verifique se você está familiarizado com os requisitos de software, rede e hardware. Para obter mais informações, [consulte Plan for Statistics Manager for Skype for Business Server](plan.md).

> [!NOTE]
> Se você estiver atualizando de uma versão anterior do Gerenciador de Estatísticas, consulte [Atualizar o Gerenciador](upgrade.md) de Estatísticas para Skype for Business Server.

> [!NOTE]
> O site do Gerenciador de Estatísticas foi testado e funciona corretamente no Internet Explorer 11+, no Edge 20.10240+ e no Chrome 46+ (versão atual do evergreen).

Você pode encontrar o Gerenciador de Estatísticas para download em [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).

Este tópico contém as seguintes seções:

- [Implantar o Gerenciador de Estatísticas](deploy.md#BKMK_Deploy)

- [Solucionar problemas de implantação](deploy.md#BKMK_Troubleshoot)

- [Criar um certificado autoassinado](deploy.md#BKMK_SelfCert)

## <a name="deploy-statistics-manager"></a>Implantar o Gerenciador de Estatísticas
<a name="BKMK_Deploy"> </a>

Para implantar o Gerenciador de Estatísticas, siga estas etapas:

1. Prepare o computador host ouvinte instalando o sistema de cache na memória do Redis e garantindo que você tenha instalado os certificados apropriados.

2. Instale o serviço Ouvinte no computador host.

3. Instale o site no computador host.

4. Instale um Agente em cada Skype for Business Server computador que você deseja monitorar.

5. Importe a topologia para os servidores que você está monitorando.

> [!NOTE]
> O Redis, o serviço Ouvinte e o Site devem estar instalados no mesmo computador host. Verifique se o computador host não tem Skype for Business Server instalado.

### <a name="prepare-the-listener-host-machine"></a>Preparar o computador host do ouvinte

Para preparar o computador host, você precisará instalar o sistema de cache na memória do Redis e garantir que um certificado válido esteja no computador. A Microsoft recomenda que você instale o build estável mais recente do Redis 3.0. O Gerenciador de Estatísticas versão 2.0 foi testado com o Redis 3.2.100.

1. Baixe o Redis do seguinte site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).

    Instaladores não assinados podem ser baixados de [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)

    Binários assinados estão disponíveis por meio de gerenciadores de pacotes populares: [Nuget](https://www.nuget.org/packages/Redis-64/) e [Choclatey](https://chocolatey.org/packages/redis-64).

   - Execute o msi fornecido e siga os prompts.

   - Não marque a caixa para adicionar uma regra de firewall.

2. O serviço Ouvinte requer um certificado. A Microsoft recomenda que você tenha um certificado assinado por uma autoridade de certificação confiável.

    Se você quiser usar um certificado autoassinado para fins de teste em um laboratório, por exemplo, consulte Criar um certificado [autoassinado](deploy.md#BKMK_SelfCert).

    O Agente usa a verificação de impressão digital do certificado (em vez de verificação em cadeia). Ele não fará a validação completa do certificado porque é possível usar certificados autoassinados.

### <a name="install-the-listener-service"></a>Instalar o serviço ouvinte

Instale o serviço Ouvinte no computador host executando o StatsManPerfAgentListener.msi e especificando o seguinte:

1. Examine o Contrato de Licença e, se você concordar, selecione Aceitar os termos no contrato **de** licença e clique em **Avançar**.

2. Na próxima página, especifique as seguintes informações:

   - **Senha do Serviço:** Essa senha é usada pelos Agentes remotos para autenticar no serviço ouvinte.

   - **Porta de Serviço:** Esse número da porta HTTPS é usado pelo Ouvinte para se comunicar com os Agentes. Durante a instalação, essa porta será permitida por meio do firewall local, uma ACL de URL será criada e um certificado SSL será associado a essa porta. O padrão é 8443.

   - **Impressão Digital do Certificado:** Esse certificado é usado pelo Ouvinte para criptografar o protocolo HTTPS. O Serviço de Rede deve ter acesso de leitura à chave privada.

     Clique no **botão Selecionar...** para escolher a impressão digital.

     Você pode encontrar a impressão digital do certificado usando o Gerenciador de Certificados ou usando o seguinte comando do PowerShell:

      ```PowerShell
      Get-ChildItem -path cert:\LocalMachine\My
      ```

   - **Instalar Dir:** Esse diretório é onde os binários serão instalados. Você pode alterá-lo do padrão usando o **botão Procurar...**

   - **AppData Dir:** Esse diretório é onde a pasta Logs e outros dados serão armazenados. Você pode alterá-lo do padrão. Ele não será excluído na desinstalação.

3. Clique em **Instalar**.

Para validar a instalação, execute as seguintes etapas:

1. Abra um navegador e navegue até `https://localhost:<service-port>/healthcheck/`

    Por padrão, a porta de serviço é 8443 (a menos que você tenha especificado outra porta).

2. Para garantir que o Ouvinte tenha sido instalado corretamente, procure o seguinte:

   - Se a página de verificação de integridade aparecer, a instalação do Ouvinte foi bem-sucedida.

   - Se KnownServerCount for 1 ou superior, a conexão com o Redis será estabelecida.

   - Depois de aguardar alguns minutos e depois que pelo menos um Agente tiver sido instalado, verifique se o contador ValuesWritten está sendo incrementado.

### <a name="install-the-website"></a>Instalar o site

Instale o site no computador host executando o StatsManWebSite.msi (incluído no [Skype for Business Server, Real-Time Statistics Manager (64 bits)](https://www.microsoft.com/download/details.aspx?id=57518)):

1. Examine o Contrato de Licença e, se você concordar, selecione Aceitar os termos no contrato **de** licença e clique em **Avançar**.

2. Na próxima página, especifique as seguintes informações:

   - **Porta de Serviço:** Essa porta TCP é onde o site escutará. Você pode alterá-lo posteriormente usando a associação do gerenciador do IIS. Durante a instalação, essa porta será permitida por meio do firewall local.

   - **Instalar Dir:** Esse diretório é onde os binários serão instalados. Você pode alterá-lo do padrão usando o **botão Procurar...**

   - **AppData Dir:** Esse diretório é onde a pasta Logs e outros dados serão armazenados. Você pode alterá-lo do padrão. Ele não será excluído na desinstalação.

3. Clique em **Instalar**.

Para exibir o Site, abra um navegador e navegue até: `http://<localhost:webport/>`.

Para exibir apenas informações de integridade, abra um navegador e navegue até: `http://localhost:<webport>/healthcheck/`.

Por padrão, o número da porta da Web é 8080. Você pode alterar a associação de porta do site usando o gerenciador do IIS.

O instalador da Web adiciona um grupo de segurança local, chamado StatsManWebSiteUsers. Você pode adicionar contas a esse grupo de segurança para conceder acesso ao Site.

### <a name="install-the-agents"></a>Instalar os Agentes

Instale um Agente em cada Skype for Business Server que você deseja monitorar executando o StatsManPerfAgent.msi:

1. Examine o Contrato de Licença e, se você concordar, selecione Aceitar os termos no contrato **de** licença e clique em **Avançar**.

2. Na próxima página, especifique as seguintes informações:

   - **Senha do Serviço:** Essa senha é usada pelo agente remoto para autenticar no serviço ouvinte.

   - **URI do serviço:** Essa URL é onde reside o Ouvinte. Use o `https://name:port` formato.

     Você pode usar um nome NETBIOS ou um FQDN. Você pode usar o nome que também é especificado como o Assunto  ou Os  Nomes Alternativos da Entidade do certificado no serviço Ouvinte, mas isso não é um requisito.

   - **Impressão Digital do Serviço:** Este certificado SS: é usado pelo Ouvinte. O Agente usará essa impressão digital para autenticar no Ouvinte. Ele não fará a validação completa do certificado porque é possível usar certificados autoassinados.

   - **Instalar Dir:** Esse diretório é onde os binários serão instalados. Você pode alterá-lo do padrão usando o **botão Procurar...**

   - **AppData Dir:** Esse diretório é onde a pasta Logs e o arquivo password.txt criptografado serão armazenados. Você pode agradecer por alterá-lo do padrão. Ele não será excluído na desinstalação.

3. Clique em **Instalar**.

Se você estiver instalando um Agente em vários computadores, provavelmente desejará fazer isso no modo autônomo. Por exemplo:

```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importar a topologia
<a name="BKMK_ImportTopology"> </a>

Depois que o Gerenciador de Estatísticas estiver instalado e em execução, você precisará importar a topologia do Skype for Business Server para que o Gerenciador de Estatísticas conheça o Site, o Pool e a Função de cada servidor. Para importar sua topologia Skype for Business Server, você usará o cmdlet [Get-CsPool](/powershell/module/skype/get-cspool) para recuperar informações sobre cada pool em uso em sua organização e, em seguida, importar essas informações para o Gerenciador de Estatísticas.

Para importar a Skype for Business Server, siga estas etapas:

1. Em um host que tem os Skype for Business Server cmdlets do PowerShell:

    a. Execute o seguinte comando:

   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```

    b. Copie o arquivo "mypoolinfo.xml" para o servidor que executa o Ouvinte.

2. No host que executa o Ouvinte:

   a. Execute o PowerShell.

   b. Navegue até o diretório no qual o Ouvinte está instalado. O padrão é:

   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. Para confirmar quais servidores estão sendo adicionados e atualizados, execute o seguinte comando:

   ```console
   .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

O comando a seguir permite que você exiba todas as opções:

```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed
```

Para ver as informações do servidor importado no momento, execute o seguinte script:

```powershell
.\Get-StatsManServerInfo.ps1
```

Se você quiser monitorar servidores que não estão em sua topologia do Skype for Business Server , um Exchange Server, por exemplo, poderá fazer uma importação de servidor único no host que executa o Ouvinte. Para fazer uma importação de servidor único, siga estas etapas:

1. Navegue até o diretório no qual o Ouvinte está instalado. O padrão é:

   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Execute o seguinte comando:

   ```powershell
   .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Solucionar problemas de implantação
<a name="BKMK_Troubleshoot"> </a>

Se um Agente não for iniciado, verifique se há os seguintes problemas:

- O agente está registrado no Gerenciador de Estatísticas?

   1. Verifique se você seguiu as instruções para importar a topologia. Consulte [Importar a topologia](deploy.md#BKMK_ImportTopology).

   2. Se o Agente estiver em um servidor que não esteja listado na topologia (por exemplo, os nós em um cluster AlwaysOn do SQL), você precisará adicionar o Agente manualmente seguindo as instruções em Importar a [topologia](deploy.md#BKMK_ImportTopology).

- O Agente pode entrar em contato com o Ouvinte?

   1. Verifique se o serviço Ouvinte está em execução.

      Se ele não estiver em execução, verifique se o Redis está em execução e tente reiniciar o Ouvinte.

   2. Verifique se a porta está aberta para o serviço Ouvinte e se o computador do Agente pode se comunicar com a porta.

- Para garantir que o Gerenciador de Estatísticas esteja coletando dados, você pode verificar o arquivo CSV da seguinte maneira.

    O comando a seguir recupera os nomes de armazenamento do contador:

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    O próximo comando recupera os valores dos contadores especificados:

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Para obter informações sobre todos os eventos que você pode ver no log de eventos do aplicativo, consulte [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).

## <a name="create-a-self-signed-certificate"></a>Criar um certificado autoassinado
<a name="BKMK_SelfCert"> </a>

A Microsoft recomenda que você use um certificado assinado por uma autoridade de certificação confiável. No entanto, se você quiser usar um certificado autoassinado para fins de teste, execute as seguintes etapas:

1. Em um console do PowerShell enquanto estiver conectado como Administrador, execute o seguinte comando:

   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Digite  `certlm.msc`. Isso abrirá o Gerenciador de Certificados para o computador local.

3. Navegue **até Pessoal** e, em seguida, abra **Certificados**.

4. Clique com o botão **direito do mouse em StatsManListener – \> Todas as Tarefas – \>Gerenciar Chaves Privadas...**

5. Clique em **Adicionar**.

6. Na caixa **Inserir os nomes de objeto a serem selecionados** , digite o seguinte texto: Serviço de Rede

7. Clique em **OK**.

8. Em **Controle Total**, desmarque a **caixa de** seleção Permitir. (Somente acesso de leitura é necessário.)

9. Clique em **OK**.

## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_SelfCert"> </a>

Para mais informações, confira os seguintes tópicos:

- [Planejar o Gerenciador de estatísticas do Skype for Business Server](plan.md)

- [Atualizar o Gerenciador de estatísticas do Skype for Business Server](upgrade.md)

- [Solução de problemas do Gerenciador de estatísticas do Skype for Business Server](troubleshoot.md)
