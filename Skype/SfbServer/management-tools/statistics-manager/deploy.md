---
title: Implantar Gerenciador de Estatísticas do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Resumo: Leia este tópico para saber como implantar o Gerenciador de Estatísticas do Skype for Business Server.'
ms.openlocfilehash: 44aad14970716f00550255855d251919a767a268
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803961"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Implantar Gerenciador de Estatísticas do Skype for Business Server
 
**Resumo:** Leia este tópico para saber como implantar o Gerenciador de Estatísticas do Skype for Business Server.
  
 O Gerenciador de Estatísticas do Skype for Business Server é uma poderosa ferramenta que permite exibir o desempenho e a integridade do Skype for Business Server em tempo real. É possível sondar dados de desempenho em centenas de servidores em intervalos de alguns segundos e ver os resultados instantaneamente no site do Gerenciador de Estatísticas.
  
Antes de tentar instalar o Gerenciador de Estatísticas, certifique-se que você está familiarizado com os requisitos de software, rede e hardware. Para mais informações, confira [Plano para Gerenciador de Estatísticas do Skype for Business Server](plan.md).
  
> [!NOTE]
> Se você estiver atualizando de uma versão anterior do Gerenciador de Estatísticas, confira [Atualizar o Gerenciador de Estatísticas do Skype for Business Server](upgrade.md). 
  
> [!NOTE]
> O site do Gerenciador de Estatísticas foi testado e funciona corretamente no Internet Explorer 11+, Microsoft Edge 20.10240+ e Chrome 46+ (versão evergreen atual). 
  
Você pode encontrar o Gerenciador de Estatísticas disponível para download na [ https://aka.ms/StatsManDownload ](https://aka.ms/StatsManDownload). 
  
Este tópico inclui as seguintes seções:
  
- [Implantar o Gerenciador de Estatísticas](deploy.md#BKMK_Deploy)
    
- [Solução de problemas de implantação](deploy.md#BKMK_Troubleshoot)
    
- [Criar um certificado autoassinado](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Implantar o Gerenciador de Estatísticas
<a name="BKMK_Deploy"> </a>

Para implantar o Gerenciador de Estatísticas, siga estas etapas:
  
1. Prepare o computador host Ouvinte instalando o sistema de cache na memória Redis e verificando se você instalou os certificados adequados.
    
2. Instale o serviço de escuta no computador host. 
    
3. Instale o site no computador host.
    
4. Instale um Agente em cada computador com Skype for Business Server que desejar monitorar.
    
5. Importe a topologia para os servidores que estiver monitorando.
    
> [!NOTE]
> O Redis, o serviço de escuta e o site deverão estar todos instalados no mesmo computador host. Certifique-se que o computador host não tem o Skype for Business Server instalado. 
  
### <a name="prepare-the-listener-host-machine"></a>Preparar o computador host Ouvinte

Para preparar o computador host, será necessário instalar o sistema de cache na memória Redis e verificar se há um certificado válido no computador. A Microsoft recomenda que você instale o build estável mais recente do Redis 3.0. A versão 2.0 do Gerenciador de Estatísticas foi testada com o Redis 3.2.100. 
  
1. Baixe o Redis do seguinte site: [ https://github.com/MSOpenTech/redis ](https://github.com/MSOpenTech/redis). 
    
    Instaladores não assinados podem ser baixados do [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    Se necessário, os binários assinados estão disponíveis por meio de gerenciadores de pacotes populares: [Nuget](https://www.nuget.org/packages/Redis-64/) e [Choclatey](https://chocolatey.org/packages/redis-64).
    
   - Execute o msi fornecido e siga as instruções.
    
   - Não marque a caixa para adicionar uma regra de firewall.
    
2. O serviço de escuta requer um certificado. A Microsoft recomenda que você tenha um certificado assinado por uma autoridade de certificação confiável. 
    
    Se quiser usar um certificado autoassinado (para fins de teste em um laboratório, por exemplo), veja [Criar um certificado autoassinado](deploy.md#BKMK_SelfCert).
    
    Observe que o Agente utiliza a verificação de impressão digital do certificado (em vez de verificação de cadeia). Ele não fará a validação completa do certificado, pois é possível usar certificados autoassinados.
    
### <a name="install-the-listener-service"></a>Instalar o serviço de escuta

Instale o serviço de escuta no computador host executando o StatsManPerfAgentListener.msi e especificando o seguinte:
  
1. Leia o Contrato de Licença e, se estiver de acordo, selecione **Aceito os termos do Contrato de Licença ** e clique em **Avançar**.  
    
2. Na próxima página, especifique as seguintes informações:
    
   - **Senha do Serviço:** esta é a senha que os Agentes remotos usarão para se autenticarem no serviço de escuta.
    
   - **Porta do Serviço:** Este é o número de porta HTTPS que o Ouvinte usará para se comunicar com os Agentes. Durante a instalação, essa porta será permitida através do firewall local, uma ACL de URL será criada e um certificado SSL será associado a essa porta. O padrão é 8443.
    
   - **Impressão Digital do Certificado:** Essa é a impressão digital de certificado que o Ouvinte usará para criptografar o protocolo HTTPS. O Serviço de Rede deve ter acesso de leitura à chave privada.
    
     Clique no botão **Selecionar...** para escolher a impressão digital.
    
     Você pode encontrar a impressão digital do Certificado usando o Gerenciador de Certificados ou o seguinte comando do PowerShell:
    
   ```PowerShell
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - **Install Dir:** Esse é o diretório no qual os binários serão instalados. Você pode alterá-lo do padrão usando o botão **Procurar... **.
    
   - **AppData Dir:** Esse é o diretório onde a pasta Logs e outros dados serão armazenados. Você pode alterá-lo do padrão. Ele não será excluído na desinstalação.
    
3. Clique em **Instalar**.
    
Para validar a instalação, execute as etapas a seguir:
  
1. Abra um navegador e navegue até https://localhost:\<service-port\>/healthcheck/
    
    Por padrão, a porta de serviço é 8443 (a menos que você tenha especificado outra porta).
    
2. Para garantir que o Ouvinte tenha sido instalado corretamente, procure o seguinte:
    
   - Se a página de verificação de integridade aparecer, a instalação do Ouvinte foi bem-sucedida.
    
   - Se o KnownServerCount for 1 ou superior, a conexão com Redis será estabelecida.
    
   - Após aguardar alguns minutos e depois que pelo menos um Agente tiver sido instalado, verifique se o contador ValuesWritten está aumentando.
    
### <a name="install-the-website"></a>Instalar o site

Instalar o site no computador host executando o StatsManWebSite.msi (incluindo o[Skype for Business Server, o Gerenciador de Estatísticas em tempo real (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) e especificar o seguinte:
  
1. Leia o Contrato de Licença e, se estiver de acordo, selecione **Aceito os termos do Contrato de Licença ** e clique em **Avançar**.  
    
2. Na próxima página, especifique as seguintes informações:
    
   - **Porta do Serviço:** Esse é o número de porta que o site da web escutará. Você pode alterá-lo posteriormente usando a associação do gerenciador do IIS. Durante a instalação, essa porta será permitida através do firewall local.
    
   - **Instalação Dir:** Esse é o diretório onde os binários serão instalados. Você pode alterá-lo do padrão usando o botão **Procurar... **.
    
   - **AppData Dir:** Esse é o diretório onde a pasta Logs e outros dados serão armazenados. Você pode alterá-lo do padrão. Ele não será excluído na desinstalação.
    
3. Clique em **Instalar**.
    
Para exibir o site, abra um navegador e navegue até: http://localhost, webport\>/.
  
Para exibir apenas informações de integridade, abra um navegador e vá até: http://localhost:\<webport\>/healthcheck/.
  
Por padrão, o número da porta da Web é 8080. Você pode alterar a associação de porta do site usando o gerenciador do IIS.
  
O instalador da Web adiciona um grupo de segurança local, chamado StatsManWebSiteUsers. Você pode adicionar contas a esse grupo de segurança para conceder acesso ao site. 
  
### <a name="install-the-agents"></a>Instalar os Agentes

Instale um Agente em cada Skype for Business Server que deseja monitorar executando o arquivo StatsManPerfAgent.msi e especificando o seguinte:
  
1. Leia o Contrato de Licença e, se estiver de acordo, selecione **Aceito os termos do Contrato de Licença ** e clique em **Avançar**.  
    
2. Na próxima página, especifique as seguintes informações:
    
   - **Senha do Serviço:** esta é a senha que o agente remoto usará para se autenticar no serviço de escuta.
    
   - **Serviço URI:** Esse é o URI onde o Ouvinte reside. Deve-se usar o https://name:port formatar.
    
     Você pode usar um nome NetBIOS ou um FQDN. Você pode usar o nome especificado como também os **Assunto** ou **Nomes de Assuntos Alternativos** do certificado em serviço de escuta, mas isso não é um requisito.
    
   - **Serviço de Impressão Digital:** Essa é a impressão digital do certificado SSL que o Ouvinte está usando. O Agente usará essa impressão digital para se autenticar com o Ouvinte. (Ele não fará a validação completa do certificado, pois é possível usar certificados autoassinados.)
    
   - **Install Dir:** Esse é o diretório no qual os binários serão instalados. Você pode alterá-lo do padrão usando o botão **Procurar... **.
    
   - **AppData Dir:** Esse é o diretório onde a pasta Logs e o arquivo password.txt criptografado serão armazenados. Você pode alterar o diretório do padrão. Ele não será excluído na desinstalação.
    
3. Clique em **Instalar**.
    
Se você estiver instalando um Agente em muitos computadores, convém fazer isso no modo autônomo. Por exemplo: 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importar a topologia
<a name="BKMK_ImportTopology"> </a>

Depois que o StatisticsManager for instalado e executado, você precisará importar a topologia do Skype for Business Server para que o Gerenciador de Estatísticas saiba o Site, o Pool e a Função de cada servidor. Para importar a topologia do Skype for Business Server, você usará o [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet para recuperar informações sobre cada grupo em uso na sua organização. Em seguida, importe essas informações para o Gerenciador de Estatísticas.
  
Para importar a topologia do Skype for Business Server, siga estas etapas:
  
1. Em um host que tem o Skype for Business Server PowerShell cmdlets:
    
    a. Execute o seguinte comando: 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. Copie o arquivo “mypoolinfo.xml” no servidor que executa o Ouvinte.
    
2. No host que executa o Ouvinte:
    
   a. Execute o PowerShell.
    
   b. Navegue até o diretório no qual o Ouvinte está instalado. O padrão é: 
    
   ```PowerShell
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. Para confirmar quais servidores estão sendo adicionados e atualizados, execute o seguinte comando:
    
   ```PowerShell
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

O seguinte comando permite ver todas as opções:
  
```PowerShell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

Para ver as informações que estão sendo importadas atualmente no seu servidor, execute o seguinte script: 
  
```PowerShell
.\Get-StatsManServerInfo.ps1
```

Se quiser monitorar servidores que não estão em sua topologia do Skype for Business Server--um Exchange Server, por exemplo--você pode fazer uma importação de um único servidor no host que executa o Ouvinte. Para fazer uma importação de um único servidor, siga estas etapas:
  
1. Navegue até o diretório no qual o Ouvinte está instalado. O padrão é: 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Execute o seguinte comando:
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Solução de problemas de implantação
<a name="BKMK_Troubleshoot"> </a>

Se ocorrer falha na inicialização de um Agente, verifique o seguinte: 
  
- O agente está registrado no Gerenciador de Estatísticas?
    
1. 	Certifique-se de seguir as instruções para importar a topologia. Veja [Importar a topologia](deploy.md#BKMK_ImportTopology).  
    
2. Se o Agente estiver em um servidor que não está listado na topologia (por exemplo, os nós de um cluster SQL AlwaysOn), você precisará adicionar o Agente manualmente seguindo as instruções contidas em [Importar a topologia](deploy.md#BKMK_ImportTopology).
    
- O Agente pode contatar o Ouvinte?
    
1. Verifique se o serviço de escuta está em execução. 
    
    Se não estiver, verifique se o Redis está em execução e, em seguida, tente reiniciar o Ouvinte.
    
2. Verifique se a porta está aberta para o serviço de escuta, e se o computador do Agente consegue se comunicar com a porta.
    
- Para garantir que o Gerenciador de Estatísticas esteja coletando dados, você pode verificar o arquivo CSV da seguinte maneira. 
    
    O seguinte comando recupera os nomes de armazenamento do contador: 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    O próximo comando recupera os valores dos contadores especificados: 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Para obter informações sobre todos os eventos que você talvez veja no log de eventos do aplicativo, consulte [Solução de Problemas do Gerenciador de Estatísticas do Skype for Business Server](troubleshoot.md).
  
## <a name="create-a-self-signed-certificate"></a>Criar um certificado autoassinado
<a name="BKMK_SelfCert"> </a>

A Microsoft recomenda que você use um certificado assinado por uma autoridade de certificação confiável. No entanto, se quiser usar um certificado autoassinado para fins de teste, faça o seguinte: 
  
1. Conectado como Administrador em um console do PowerShell, digite o seguinte:
    
   ```PowerShell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Tipo `certlm.msc`. Isso abrirá o Gerenciador de Certificados do computador local.
    
3. Navegue até **Pessoal**e abra **Certificados**.
    
4. Clique com botão direito do mouse em **StatsManListener –\>Todas as Tarefas-\>Gerenciar Chaves Privadas...**
    
5. Clique em **Adicionar**.
    
6. Na caixa **Digite os nomes de objeto a serem selecionados**, digite o seguinte: Serviço de Rede.
    
7. Clique em **OK**.
    
8. Em **Controle Total**, desmarque a caixa de seleção **Permitir**. (Apenas o acesso de leitura é necessário.)
    
9. Clique em **OK**.
    
## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_SelfCert"> </a>

Para obter mais informações, consulte o seguinte:
  
- [Planejar o Gerenciador de Estatísticas do Skype for Business Server](plan.md)
    
- [Atualizar o Gerenciador de Estatísticas do Skype for Business Server](upgrade.md)
    
- [Solução de Problemas do Gerenciador de Estatísticas do Skype for Business Server](troubleshoot.md) ß
