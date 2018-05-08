---
title: Preparar o dispositivo do Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Saiba mais sobre como preparar seu aparelho de conector de nuvem para implantação e usar com o sistema telefônico no Office 365 (nuvem PBX).
ms.openlocfilehash: 130d593ba94eff9da163363a652bc389b713d1b0
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="prepare-your-cloud-connector-appliance"></a>Preparar o dispositivo do Cloud Connector
 
Saiba mais sobre como preparar seu aparelho de conector de nuvem para implantação e usar com o sistema telefônico no Office 365 (nuvem PBX).
  
Esta seção descreve como obter os arquivos de instalação do Skype for Business Cloud Connector Edition, instalar o software Cloud Connector e preparar o dispositivo do Cloud Connector para implantação. Depois de ter concluído todas as etapas desta seção, você estará pronto para implantar o Cloud Connector em um único site ou em vários sites. Se você possui uma implantação existente do conector de nuvem e você ainda não tiver atualizado para o conector de nuvem versão 2.1, consulte [atualizar para uma nova versão do conector de nuvem](upgrade-to-a-new-version-of-cloud-connector.md).
  
> [!NOTE]
> A Microsoft oferece suporte à versão atual do Edition do conector de nuvem, versão 2.1. Se você configurou a atualização automática, o Cloud Connector será atualizado automaticamente. Se você configurou a atualização manual, você precisará atualizar para a versão 2.1 até 60 dias após o lançamento. Microsoft dará suporte a versão anterior para 60 dias após o lançamento do 2.1 para permitir que o seu tempo para atualizar. 
  
> [!NOTE]
> Para o conector de nuvem versão 2.1 e posterior, o aparelho de host deve ter o .NET Framework 4.6.1 ou posterior instalado. 
  
> [!IMPORTANT]
> Para uma implantação bem-sucedida, quando você executar os cmdlets para configurar Skype para Business Edition do conector de nuvem, sempre use a mesma sessão de console como aquele em que você começou. Evite alternar entre diferentes sessões durante a implantação e a configuração. 
  
> [!NOTE]
> Existem algumas etapas que você executa somente para o primeiro dispositivo de sua implantação: criar um compartilhamento para o diretório do site, baixar os bits e preparar um arquivo VHDX (disco rígido virtual) com a imagem ISO do Windows Server. 
  
## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Baixar o instalador do Skype for Business Cloud Connector Edition

1. No servidor host onde executará as VMs do conector de nuvem, baixe os arquivos de instalação: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller). 
    
    > [!IMPORTANT]
    > O servidor host precisa acessar a Internet durante a instalação do Cloud Connector porque arquivos adicionais são baixados durante a instalação. 
  
2. Execute o instalador e aceite os valores padrão durante a instalação.
    
3. Confirme se a instalação foi concluída com êxito.
    
## <a name="verify-the-installation-and-configure-the-environment"></a>Verificar a instalação e configurar o ambiente

1. Abra um console do PowerShell como administrador e confirme que o Skype para os cmdlets de conector de nuvem Business Edition estão disponíveis usando o seguinte cmdlet:
    
  ```
  Get-Command *-Cc*
  ```

    O comando deve retornar uma lista de cmdlets para Skype para o conector de nuvem Business Edition.
    
2. Os arquivos VHDs, SfBBits e VersionInfo serão armazenados no **Diretório de Sites**.
    
    Você pode localizar o **Diretório de Sites** com o seguinte cmdlet:
    
  ```
  Get-CcSiteDirectory
  ```

    O comando deve retornar um local no sistema de arquivos. O local pode ser uma pasta local ou um compartilhamento de aquivo. O local padrão para o **Diretório de Sites** é: %USERPROFILE%\CloudConnector\SiteRoot. O local padrão deve ser alterado para um compartilhamento de aquivo no primeiro dispositivo criado em cada site.
    
    O local selecionado deve ser:
    
  - Criado no primeiro dispositivo criado em cada site.
    
  - Uma pasta compartilhada acessível por outros servidores host (dispositivos) no mesmo site.
    
    Para definir o **Diretório de Sites** para um local diferente do padrão, execute o seguinte cmdlet:
    
  ```
  Set-CcSiteDirectory <UNC File path>
  ```

    Se você estiver implantando alta disponibilidade para o site, execute o cmdlet para definir o **Diretório de Sites ** para o mesmo local em cada servidor host do site.
    
    Quando você fizer logon e implantar cada aparelho no site, certifique-se de que sua conta de logon atual tiver o acesso correto para o **Diretório de sites**.
    
3. O **Aparelho de diretório** é o diretório raiz de trabalho local para Skype para Business Edition do conector de nuvem e o local onde os certificados externos, instâncias e logs são salvos. O local padrão é: %USERPROFILE%\CloudConnector\ApplianceRoot.
    
    Você pode localizar o **Diretório de Sites** executando o seguinte cmdlet:
    
  ```
  Get-CcApplianceDirectory
  ```

    Para definir o **Diretório de Dispositivos** para um local diferente do padrão, execute o seguinte cmdlet:
    
  ```
  Set-CcApplianceDirectory <File path>
  ```

    O Diretório de Dispositivos deve ser definido em uma pasta local no dispositivo. Você só deve definir o **Aparelho de diretório** antes de iniciar o Skype para implantação do conector de nuvem Business Edition. Se você alterá-lo após a implantação, será necessário reimplantar o servidor host.
    
    > [!IMPORTANT]
    > O caminho do **Diretório de Dispositivos** não deve conter espaços.
  
## <a name="set-the-path-for-the-external-edge-certificate"></a>Definir o caminho do certificado externo de Borda

- Execute o cmdlet a seguir para definir o caminho do certificado externo de Borda, incluindo o nome do arquivo. Por exemplo: C:\certs\cce\ap.contoso.com.pfx. O certificado deve conter chaves privadas.
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Note que o parâmetro -Target é específico à versão 1.4.2 e posteriores. 
  
    Especificar o caminho completo do certificado externo, incluindo o nome do arquivo. O certificado pode ser armazenado localmente ou em um compartilhamento de arquivo. Se o certificado for armazenado em uma pasta compartilhada, essa pasta deverá ser criada no primeiro dispositivo de cada site e deverá ser acessível por outros dispositivos pertencentes ao mesmo site. Esse cmdlet copia o certificado externo para o **Diretório de Dispositivos**.
    
    > [!IMPORTANT]
    > **Se você atualizou o conector de nuvem versão 1.4.2 ou posterior**, verifique se o certificado externo preparado contém chaves privadas e a cadeia de certificados completo incluindo o certificado de autoridade de certificação raiz e a intermediário certificados de autoridade de certificação. > **se você tiver Ainda não foi atualizado para o conector de nuvem versão 1.4.2**, verifique se o certificado externo preparado contém chaves particulares. Esse certificado externo deve ser emitido pela Autoridade de Certificação que é confiável para o Windows por padrão.
  
## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Definir o caminho para o certificado externo do gateway/SBC PSTN

Se você estiver usando o TLS entre o Servidor de Mediação e o gateway PSTN/SBC, execute o seguinte cmdlet para definir o caminho, incluindo o nome do arquivo, para o certificado de gateway. Por exemplo: C:\certs\cce\sbc.contoso.com.cer. O certificado deve conter a Autoridade de Certificação raiz e a cadeia intermediária para o certificado atribuído ao gateway:
  
```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 

```

> [!NOTE]
> Note que o parâmetro -Target é específico à versão 1.4.2 e posteriores. 
  
## <a name="create-virtual-switches-in-hyper-v-manager"></a>Criar comutadores virtuais no Gerenciador do Hyper-V

1. Abra o **Gerenciador de Hyper-V** > **Gerenciador de comutador Virtual**e selecione **Novo Gerenciador de comutador Virtual**.
    
2. Crie um comutador virtual externo e associe-o ao adaptador de rede física que está conectado ao domínio da rede interna:
    
    Selecione a opção **Permitir que o sistema operacional de gerenciamento compartilhe este adaptador de rede** para esse comutador virtual.
    
3. Crie um comutador virtual externo e vinculá-lo ao adaptador de rede física que é roteado para a Internet:
    
    Desprovisionamento selecione **Permitir que o sistema operacional de gerenciamento compartilhe este adaptador de rede** para este comutador virtual.
    
4. Defina o nome do comutador que se conecta a rede de perímetro para o seu domínio de rede interna **SfB CCE Corpnet alternar**.
    
    Defina o nome do comutador que se conecta a rede de perímetro para a Internet **SfB CCE Internet alternar**.
    
## <a name="update-the-cloudconnectorini-configuration-file"></a>Atualizar o arquivo de configuração CloudConnector.ini

Prepare o arquivo CloudConnector.ini usando as informações coletadas na [Determine parâmetros de implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) no tópico [Planejar Skype para o conector de nuvem Business Edition](plan-skype-for-business-cloud-connector-edition.md) .
  
Para atualizar o arquivo, execute o seguinte cmdlet para obter o modelo (CloudConnector.Sample.ini):
  
```
Export-CcConfigurationSampleFile
```

O modelo é armazenado no **Diretório de Dispositivos**.
  
Depois de atualizá-lo com os valores para seu ambiente, salve o arquivo como CloudConnector.ini no **Diretório de Dispositivos**. É possível executar **Get-CcApplianceDirectory** para determinar o caminho para o **Aparelho de diretório**.
  
Ao atualizar o arquivo .ini, considere o seguinte:
  
> [!NOTE]
> Nem todos os valores para o arquivo .ini são mencionados nesta seção, somente aqueles com uma consideração especial são incluídos aqui. Para obter uma lista completa, consulte a seção [parâmetros de implantação Determine](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) a [Planejar Skype para o conector de nuvem Business Edition](plan-skype-for-business-cloud-connector-edition.md) tópico. > para obter mais informações sobre quais valores precisam ser alteradas para novos sites ou de dispositivos adicionais, consulte [ Site único com alta disponibilidade (HA) em comparação com implantações de múltiplos sites](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) no tópico[implantar vários sites em nuvem de conector](deploy-multiple-sites-in-cloud-connector.md). 
  
- **SiteName:** o valor padrão é **Site1**. Você deve atualizá-lo antes de implantar o Cloud Connector, pois quando você executar **Register-CcAppliance** para registrar um dispositivo em um site novo ou existente, o cmdlet usará **SiteName** para determinar qual site registrar.
    
     Se você deseja registrar o dispositivo em um site novo, o valor de **SiteName** deverá ser exclusivo e diferente dos sites existentes. Se você deseja registrar o aparelho a um site existente, o valor para **SiteName** no arquivo. ini deve corresponder o nome definido na sua configuração de Inquilino do Office 365. Se você estiver copiando um arquivo de configuração de um site para outro, atualize o valor de **SiteName** devidamente para cada site.
    
- **ServerName:** O nome do servidor não deve conter o nome do domínio e deve ser limitado a 15 caracteres. 
    
- **HardwareType:** Se você não definir ou deixe o valor como nulo, o valor padrão de **Normal** será usado. Use **Normal** , se você planeja implantar a versão maior do conector de nuvem para oferecer suporte a 500 chamadas simultâneas por máquina host conforme descrito em [Plan for Skype para o conector de nuvem Business Edition](plan-skype-for-business-cloud-connector-edition.md). Use **Mínimo** para uma implantação menor que permita 50 chamadas simultâneas.
    
- **Comutadores virtuais de Internet/Corpnet/Gerenciamento**: adicione o nome dos comutadores criados. Para o comutador virtual de gerenciamento, apenas deixe o valor padrão. O script de implantação o criará no início da implantação e o excluirá quando a implantação terminar.
    
- **ManagementIPPrefix:** o ManagementIPPrefix, na seção Rede, deve ser uma sub-rede diferente dos outros IPs internos. Por exemplo, como o valor padrão mostra, ManagementIPPrefix é 192.168.213.0, enquanto o IPAddress do AD é 192.168.0.238.
    
    Os scripts de implantação criam um adaptador de rede de gerenciamento em cada máquina virtual, atribui a cada uma delas um IP de gerenciamento e as conecta a um comutador virtual de gerenciamento. Isso permite que o servidor host se conecte a todas as máquinas virtuais e as gerencie por meio da rede de gerenciamento. O comutador virtual de gerenciamento é excluído quando a implantação é concluída.
    
- **Configurações específicas de base VM:** Configurações nesta seção devem ser definidas para o cmdlet **Convert-CcIsoToVhdx** .
    
    Durante a preparação da imagem da VM base, ela será conectada ao comutador de rede interno. As seguintes configurações são essenciais para a VM acessar a Internet:
    
  - [Common]BaseVMIP: o endereço IP corpnet que será atribuído à VM base.
    
  - [Network]CorpnetDefaultGateway: o gateway padrão a ser atribuído à VM base.
    
  - [Network]CorpnetDNSIPAddress: o endereço IP do DNS que será atribuído à VM base.
    
  - [Network]WSUSServer: o endereço IP do Windows Server Update Service.
    
  - [Network]WSUSServer: o endereço IP do servidor de status do Windows Server Update Service.
    
  - [Network]EnableReferSupport: isso definirá se o suporte para SIP REFER está habilitado ou desabilitado na Configuração do Tronco em seu IP/PBX.
    
- **IPs externos:**
    
  - Verifique se a máscara de sub-rede CorpnetIPPrefixLength está correta.
    
  - Verifique se que há nenhum conflito IP para esses IPs interno.
    
- **IPs externos:**
    
  - Para IP público do MR: especifique ExternalMRIPs para não-NAT ou ExternalMRPublicIPs para NAT.
    
  - ExternalSIPIPs e ExternalMRIPs podem ser os mesmos.
    
  - Verifique se a máscara de sub-rede InternetIPPrefixLength está correta.
    
  - Verifique se que há nenhum conflito IP para esses IPs externo.
    
- **Gateways:**
    
  - Se você tiver somente um gateway, remova a seção do gateway secundário. Se você tiver mais de dois gateways, crie seções adicionais copiando e colando a existente e atualizando-a depois.
    
  - Verifique se o endereço IP e a porta do(s) gateway(s) estão corretos.
    
  - Para dar suporte ao nível de alta disponibilidade do Gateway PSTN, saia do gateway secundário e adicione os gateways adicionais que você usará. Você pode copiar e colar uma entrada existente e, em seguida, atualizá-lo.
    
- Opcionalmente, você pode atualizar o valor de LocalRoute para restringir os números de chamada de saída.
    
## <a name="download-the-bits-to-the-site-directory"></a>Baixar os bits para o Diretório de Sites

Execute o seguinte cmdlet para baixar os bits e os arquivos de informações de versão para o **Diretório de Sites**:
  
```
Start-CcDownload
```

> [!NOTE]
> Você deve executar esta etapa somente para o primeiro dispositivo. 
  
## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Preparar VHDX (disco virtual base) usando o arquivo ISO baixado

Esta etapa prepara o VHDX (arquivo do disco virtual) a partir da imagem ISO do Windows Server 2012. O VHDX será usado para criar máquinas virtuais durante a implantação. Será criada uma temporária (máquina virtual base) e Windows Server 2012 será instalado do arquivo ISO. Após a VM ser criada, alguns componentes necessários serão instalados e a atualização mais recente do Windows será aplicada. Por fim, a VM base será generalizada (sysprep) e limpa, permanecendo apenas o arquivo de disco virtual gerado.
  
> [!NOTE]
> Você deve executar esta etapa somente para o primeiro dispositivo. 
  
Antes de continuar com esta etapa, verifique se o comutador corpnet foi criado. Além disso, confirme se as seguintes configurações estão corretas no arquivo CloudConnector.ini:
  
- [Network] CorpnetSwitchName
    
- [Comuns] BaseVMIP
    
- [Network] CorpnetIPPrefixLength
    
- [Network] CorpnetDefaultGateway
    
- [Network] CorpnetDNSIPAddress
    
Inicie um console do PowerShell como administrador e execute o seguinte cmdlet para converter a imagem ISO em um VHD:
  
```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Especifique o caminho completo da imagem ISO. Inclua o nome do arquivo. Por exemplo: C:\ISO\WindowsServer2012R2.iso.
  
O arquivo VHD criado é armazenado na pasta \Bits\VHD **Diretório de sites** . Você pode obter o caminho do **Diretório de Sites** executando **Get-CcSiteDirectory**.
  
> [!IMPORTANT]
> Por padrão, as configurações de proxy não são feitas na VM base. Se for necessário um proxy no seu ambiente de rede para atualizar a VM via Windows Update, adicione a opção - PauseBeforeUpdate quando você executa "Convert-CcIsoToVhdx". O script pausará antes do Windows Update e você terá a oportunidade para configurar manualmente a proxy no VM. Quando a configuração do proxy for concluída e a VM conseguir acessar a Internet, você poderá retomar o script para concluir as etapas restantes. 
  
### <a name="create-vhds-for-a-multi-site-deployment"></a>Criar VHDs para a implantação de vários sites

Esta é uma etapa opcional que se aplica apenas a implantações de vários sites.
  
Se você estiver fazendo uma implantação de vários sites, não será necessário converter ISO em um VHD para cada site. É possível copiar o VHDX criado para o primeiro site para o servidor host de um segundo site.
  
 Copie o arquivo no mesmo local de arquivo ( **Diretório de sites** \Bits\VHD pasta) e com o mesmo nome de arquivo, no servidor host para um site adicional.
  
## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Definir a política de Execução do PowerShell para RemoteSigned

Os scripts do PowerShell fornecidos exigem que a política de execução seja definida como RemoteSigned. Para ver a configuração atual, abra um console do PowerShell como administrador e execute o seguinte cmdlet:
  
```
Get-ExecutionPolicy
```

Caso ela não esteja definida como "RemoteSigned”, execute o seguinte cmdlet para alterá-la:
  
```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Alterar a Política de Grupo local na máquina host (versões 1.4.1 e anteriores)

> [!NOTE]
> Esta tarefa não é necessária para o Cloud Connector versão 1.4.2 e posteriores. 
  
A conta CceService é criada durante a implantação do Skype for Business Cloud Connector Edition. Ele executa o serviço de gerenciamento de conector de nuvem e exige permissão para desinstalar o cloudconnector.msi. Você deve alterar a configuração da política de grupo na máquina host do Cloud Connector para especificar que o registro do usuário não deve ser descarregado quando o usuário se desconecta. Siga estas etapas:
  
### <a name="to-change-the-group-policy-setting"></a>Para alterar a configuração da Política de Grupo

1. Abra o **Editor de diretiva de grupo** executando gpedit. msc.
    
2. No **Editor de Política de Grupo**, navegue até Modelos Administrativos > Sistema > Perfil de Usuário > Não descarregar forçosamente o Registro do usuário no logoff do usuário.  
    
3. Defina seu valor como **habilitada**.
    
## <a name="set-up-your-office-365-tenant"></a>Configure o locatário do Office 365

Um inquilino do Office 365 com o Skype para Business Online e o sistema telefônico no Office 365 é necessário. Verifique se seu locatário é instalado e configurado antes de tentar usar o conector de nuvem.
  
Algumas etapas de instalação do Office 365 exigem que você usar o PowerShell remoto do inquilino (TRPS) para configurar seu locatário do Office 365. **Isso deve ser instalado no servidor host.** Você pode baixar o Skype para módulo Business Online do PowerShell do:[Skype para negócios Online, o módulo do Windows PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=39366).
  
Crie um Skype dedicado para a conta de administrador de negócios para o gerenciamento on-line do conector de nuvem, por exemplo, CceOnlineManagmentAdministrator. Essa conta será usada pelo dispositivo para adicionar ou remover dispositivos, habilitar ou desabilitar a atualização automática do sistema operacional, habilitar ou desabilitar a atualização automática de binários. Defina a senha dessa conta para nunca expirar, assim não será necessário alterá-la para o serviço sempre que ela expirar.
  

