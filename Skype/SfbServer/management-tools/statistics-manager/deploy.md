---
title: Implantar o Gerenciador de estatísticas para Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Resumo: Leia este tópico para saber como implantar o Gerenciador de estatísticas para Skype para Business Server.'
ms.openlocfilehash: 4d32c10852091d494f59c65648cb370878fc3413
ms.sourcegitcommit: 8a6bf02958436fcdeed336f09079bd3827e2fccb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2018
ms.locfileid: "26282977"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Implantar o Gerenciador de estatísticas para Skype para Business Server
 
**Resumo:** Leia este tópico para saber como implantar o Gerenciador de estatísticas para Skype para Business Server.
  
 Gerenciador de estatísticas para Skype para Business Server é uma ferramenta poderosa que permite que você visualize Skype para dados de integridade e desempenho do servidor de negócios em tempo real. Você pode sondar dados de desempenho em centenas de servidores por cada alguns segundos e exiba os resultados instantaneamente no site do Gerenciador de estatísticas.
  
Antes de tentar instalar o Gerenciador de estatísticas, certifique-se de que você está familiarizado com os requisitos de hardware, software e rede. Para obter mais informações, consulte [Planejar para o Gerenciador de estatísticas de Skype para Business Server](plan.md).
  
> [!NOTE]
> Se você estiver atualizando de uma versão anterior do Gerenciador de estatísticas, consulte [Atualizar o Gerenciador de estatísticas para Skype para Business Server](upgrade.md). 
  
> [!NOTE]
> O site do Gerenciador de Estatísticas foi testado e funciona corretamente no Internet Explorer 11+, Edge 20.10240+ e Chrome 46+ (versão evergreen atual). 
  
Você pode encontrar o Gerenciador de estatísticas disponível para download em [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload). 
  
Este tópico inclui as seguintes seções:
  
- [Implantar o Gerenciador de Estatísticas](deploy.md#BKMK_Deploy)
    
- [Solução de problemas de implantação](deploy.md#BKMK_Troubleshoot)
    
- [Criar um certificado autoassinado](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Implantar o Gerenciador de Estatísticas
<a name="BKMK_Deploy"> </a>

Para implantar o Gerenciador de estatísticas, siga estas etapas:
  
1. Prepare o computador host Ouvinte instalando o sistema de cache na memória Redis e verificando se você instalou os certificados adequados.
    
2. Instale o serviço de escuta no computador host.  
    
3. Instale o site no computador host.
    
4. Instale um agente em cada Skype para máquina Business Server que devem ser monitoradas.
    
5. Importe a topologia para os servidores que estiver monitorando.
    
> [!NOTE]
> O Redis, o serviço de escuta e o site deverão estar todos instalados no mesmo computador host. Certifique-se de que a máquina host não tem Skype para Business Server instalado. 
  
### <a name="prepare-the-listener-host-machine"></a>Preparar o computador host Ouvinte

Para preparar a máquina host, você precisará instalar o sistema de cache de na memória relacionada e verifique se é um certificado válido na máquina. A Microsoft recomenda que você instale a compilação estável mais recente do 3.0 relacionada. Gerenciador de estatísticas versão 2.0 foi testado com relacionada 3.2.100. 
  
1. Baixe o relacionada nos seguinte site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis). 
    
    Instaladores não assinados podem ser baixados do[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    Se necessário, binários assinados estão disponíveis por meio de gerenciadores de pacotes populares: [Nuget](https://www.nuget.org/packages/Redis-64/) e [Choclatey](https://chocolatey.org/packages/redis-64).
    
   - Execute o msi fornecido e siga as instruções.
    
   - Não marque a caixa para adicionar uma regra de firewall.
    
2. O serviço de escuta requer um certificado. Microsoft recomenda que você tenha um certificado assinado por uma autoridade de certificação confiável. 
    
    Se quiser usar um certificado autoassinado (para fins de teste em um laboratório, por exemplo), veja [Criar um certificado autoassinado](deploy.md#BKMK_SelfCert).
    
    Observe que o Agente utiliza a verificação de impressão digital do certificado (em vez de verificação de cadeia). Ele não fará a validação completa do certificado, pois é possível usar certificados autoassinados.
    
### <a name="install-the-listener-service"></a>Instalar o serviço de escuta

Instale o serviço de ouvinte na máquina host executando o StatsManPerfAgentListener.msi e especificando o seguinte:
  
1. Leia o Contrato de Licença e, se estiver de acordo, selecione **Aceito os termos do Contrato de Licença ** e clique em **Avançar**.  
    
2. Na próxima página, especifique as seguintes informações:
    
   - **Senha do Serviço:** esta é a senha que os Agentes remotos usarão para se autenticarem no serviço de escuta.
    
   - **Porta de serviço:** Esse é o número de porta HTTPS que o ouvinte usará para se comunicar com os agentes. Durante a instalação, essa porta poderão através do firewall local, será criada uma ACL de URL e um certificado SSL será vinculado a essa porta. O padrão é 8443.
    
   - **Impressão digital do certificado:** Esta é a impressão digital do certificado que o ouvinte usará para criptografar o protocolo HTTPS. Serviço de rede deve ter acesso de leitura para a chave privada.
    
     Clique no botão **Selecionar...** para escolher a impressão digital.
    
     Você pode encontrar a impressão digital do Certificado usando o Gerenciador de Certificados ou o seguinte comando do PowerShell:
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - **Instalar Dir:** Esse é o diretório no qual os binários serão instalados. Você pode alterá-lo do padrão usando o botão **Browse...** .
    
   - **AppData Dir:** Esse é o diretório onde a pasta de Logs e outros dados serão armazenados. Você pode alterá-lo do padrão. Ela não será excluída em Desinstalar.
    
3. Clique em **Instalar**.
    
Para validar a instalação, execute as etapas a seguir:
  
1. Abra um navegador e navegue atéhttps://localhost:\<service-port\>/healthcheck/
    
    Por padrão, a porta de serviço é 8443 (a menos que você tenha especificado outra porta).
    
2. Para garantir que o Ouvinte tenha sido instalado corretamente, procure o seguinte:
    
   - Se a página de verificação de integridade aparecer, a instalação do Ouvinte foi bem-sucedida.
    
   - Se o valor de KnownServersCount for 1 ou maior, a conexão com o Redis foi estabelecida.
    
   - Após aguardar alguns minutos e depois que pelo menos um Agente tiver sido instalado, verifique se o contador ValuesWritten está aumentando.
    
### <a name="install-the-website"></a>Instalar o site

Instale o site na máquina host executando o StatsManWebSite.msi e especificando o seguinte:
  
1. Leia o Contrato de Licença e, se estiver de acordo, selecione **Aceito os termos do Contrato de Licença ** e clique em **Avançar**.  
    
2. Na próxima página, especifique as seguintes informações:
    
   - **Porta de serviço:** Esse é o número de porta que o site escutará. Você pode alterar posteriormente usando o Gerenciador do IIS vinculando. Durante a instalação, essa porta poderão através do firewall local.
    
   - **Instalar Dir:** Esse é o diretório onde os binários serão instalados. Você pode alterá-lo do padrão usando o botão **Browse...** .
    
   - **AppData Dir:** Esse é o diretório onde a pasta de Logs e outros dados serão armazenados. Você pode alterá-lo do padrão. Ela não será excluída em Desinstalar.
    
3. Clique em **Instalar**.
    
Para exibir o site da Web, abra um navegador e navegue até: http://localhost, webport\>/.
  
Para exibir somente informações de integridade, abra um navegador e navegue até: http://localhost:\<webport\>/healthcheck/.
  
Por padrão, o número da porta da Web é 8080. Você pode alterar a associação de porta do site usando o gerenciador do IIS.
  
O instalador da Web adiciona um grupo de segurança local, chamado StatsManWebSiteUsers. Você pode adicionar contas a esse grupo de segurança para conceder acesso ao site. 
  
### <a name="install-the-agents"></a>Instalar os Agentes

Instale um agente em cada Skype para servidor de negócios que você deseja monitorar executando o StatsManPerfAgent.msi e especificando o seguinte:
  
1. Leia o Contrato de Licença e, se estiver de acordo, selecione **Aceito os termos do Contrato de Licença ** e clique em **Avançar**.  
    
2. Na próxima página, especifique as seguintes informações:
    
   - **Senha do Serviço:** esta é a senha que o agente remoto usará para se autenticar no serviço de escuta.
    
   - **URI do serviço:** Esse é o URI de onde o ouvinte reside. Ela deve usar o https://name:port formato.
    
     Você pode usar um nome NetBIOS ou um FQDN. Você pode usar o nome que também é especificado como o **assunto** ou **Nomes alternativos do assunto** do certificado no serviço do ouvinte, mas isso não é um requisito.
    
   - **Pessoal Thumbprint:** Esta é a impressão digital do certificado SSL que do ouvinte está usando. O agente usará essa impressão digital para autenticar para o ouvinte. (Não farão completos de validação do certificado porque é possível usar certificados autoassinados.)
    
   - **Instalar Dir:** Esse é o diretório no qual os binários serão instalados. Você pode alterá-lo do padrão usando o botão **Browse...** .
    
   - **AppData Dir:** Esse é o diretório onde a pasta de Logs e o arquivo Password criptografadas serão armazenados. Você pode Agradeço alterá-lo do padrão. Ela não será excluída em Desinstalar.
    
3. Clique em **Instalar**.
    
Se você estiver instalando um Agente em muitos computadores, convém fazer isso no modo autônomo. Por exemplo:   
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importar a topologia
<a name="BKMK_ImportTopology"> </a>

Depois de estatísticas Manager é instalado e em execução, você precisa importar o Skype para a topologia de servidor de negócios assim que o Gerenciador de estatísticas sabe o Site, Pool e a função de cada servidor. Para importar sua Skype para topologia de servidores corporativos, você usará o cmdlet [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) para recuperar informações sobre cada pool em uso na sua organização e importar essas informações para o Manager de estatísticas.
  
Para importar o Skype para topologia de servidores corporativos, siga estas etapas:
  
1. Em um host que possui o Skype para cmdlets do PowerShell do servidor de negócios:
    
    a. Execute o seguinte comando: 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. Copie o arquivo de "mypoolinfo.xml" para o servidor que executa o ouvinte.
    
2. No host que executa o Ouvinte:
    
   a. Execute o PowerShell.
    
   b. Navegue até o diretório no qual o Ouvinte está instalado. O padrão é: 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. Para confirmar quais servidores estão sendo adicionados e atualizados, execute o seguinte comando:
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

O seguinte comando permite ver todas as opções:
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

Para ver as informações do servidor atualmente importado, execute o seguinte script: 
  
```
.\Get-StatsManServerInfo.ps1
```

Por exemplo-- se você gostaria de monitorar os servidores que não estão na sua Skype para topologia de servidores de negócios – um servidor Exchange, você poderá fazer uma importação de servidor único no host que executa o ouvinte. Para fazer uma importação de um único servidor, siga estas etapas:
  
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
  
- É o agente registrado no Gerenciador de estatísticas?
    
1. 	Certifique-se de seguir as instruções para importar a topologia. Veja [Importar a topologia](deploy.md#BKMK_ImportTopology).  
    
2. Se o Agente estiver em um servidor que não está listado na topologia (por exemplo, os nós de um cluster SQL AlwaysOn), você precisará adicionar o Agente manualmente seguindo as instruções contidas em [Importar a topologia](deploy.md#BKMK_ImportTopology).
    
- O Agente pode contatar o Ouvinte?
    
1. Verifique se o serviço de escuta está em execução.   
    
    Se não estiver, verifique se o Redis está em execução e, em seguida, tente reiniciar o Ouvinte.
    
2. Verifique se a porta está aberta para o serviço de escuta e que o computador agente pode se comunicar com a porta.
    
- Para garantir que o Gerenciador de estatísticas é coleta de dados, você pode verificar o arquivo CSV da seguinte maneira. 
    
    O seguinte comando recupera os nomes de armazenamento do contador:   
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    O próximo comando recupera os valores dos contadores especificados:  
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Para obter informações sobre todos os eventos que talvez você veja no log de eventos de aplicativo, consulte [Solucionar problemas de Gerenciador de estatísticas para Skype para Business Server](troubleshoot.md).
  
## <a name="create-a-self-signed-certificate"></a>Criar um certificado autoassinado
<a name="BKMK_SelfCert"> </a>

A Microsoft recomenda que você use um certificado assinado por uma autoridade de certificação confiável. No entanto, se quiser usar um certificado autoassinado para fins de teste, faça o seguinte: 
  
1. Conectado como Administrador em um console do PowerShell, digite o seguinte:
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Tipo `certlm.msc`. Isso abrirá o Gerenciador de Certificados do computador local.
    
3. Navegue até o **pessoal**e abra **certificados**.
    
4. Clique com o botão direito em **StatsManListener -\>todas as tarefas -\>gerenciar chaves particulares …**
    
5. Clique em **Adicionar**.
    
6. Na caixa **Digite os nomes de objeto a serem selecionados**, digite o seguinte: Serviço de Rede.
    
7. Clique em **OK**.
    
8. Em **Controle Total**, desmarque a caixa de seleção **Permitir**. (Apenas o acesso de leitura é necessário.)
    
9. Clique em **OK**.
    
## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_SelfCert"> </a>

Para obter mais informações, consulte:
  
- [Planejar para o Gerenciador de estatísticas de Skype Business Server](plan.md)
    
- [Atualizar o Gerenciador de estatísticas para Skype para Business Server](upgrade.md)
    
- [Solucionar problemas de gerente de estatísticas para Skype para Business Server](troubleshoot.md)
    
- [Blog sobre o Gerenciador de Estatísticas do Skype for Business Server](https://blogs.technet.microsoft.com/skypestatsman/)
    

