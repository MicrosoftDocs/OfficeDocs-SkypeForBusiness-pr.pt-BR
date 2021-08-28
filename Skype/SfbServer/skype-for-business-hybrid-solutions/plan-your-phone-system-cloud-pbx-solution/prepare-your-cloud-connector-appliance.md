---
title: Preparar o dispositivo do Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Saiba como preparar seu dispositivo do Cloud Connector para implantação e uso com Sistema de Telefonia (Cloud PBX).
ms.openlocfilehash: 255b276ebb0d192f876d07e318cf94ccf3698a1f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589995"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Preparar o dispositivo do Cloud Connector

> [!Important]
> O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com Skype for Business Online. Depois que sua organização tiver sido atualizada para Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)

Saiba como preparar seu dispositivo do Cloud Connector para implantação e uso com Sistema de Telefonia (Cloud PBX).

Esta seção descreve como obter os arquivos de Skype for Business Cloud Connector Edition de instalação, instalar o software do Cloud Connector e preparar seu dispositivo Cloud Connector para implantação. Depois de concluir todas as etapas desta seção, você estará pronto para implantar o Cloud Connector para um único site ou vários sites. Se você tiver uma implantação existente do Cloud Connector e ainda não tiver atualizado para o Cloud Connector versão 2.1, consulte Upgrade to a new [version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> A Microsoft dá suporte à versão atual do Cloud Connector Edition, versão 2.1. Se você configurou a atualização automática, o Cloud Connector será atualizado automaticamente. Se você configurou a atualização manual, precisará atualizar para a versão 2.1 dentro de 60 dias após a versão. A Microsoft dará suporte à versão anterior por 60 dias após o lançamento do 2.1 para permitir a atualização. 

> [!NOTE]
> Para o Cloud Connector versão 2.1 e posterior, o dispositivo host deve ter .NET Framework 4.6.1 ou posterior instalado. 

> [!IMPORTANT]
> Para implantação bem-sucedida, quando você executar os cmdlets para configurar Skype for Business Cloud Connector Edition, sempre use a mesma sessão de console que a que você iniciou. Evite alternar para sessões diferentes durante a implantação e configuração. 

> [!NOTE]
> Existem algumas etapas que você executa apenas para o primeiro dispositivo em sua implantação: criar um compartilhamento para o diretório do site, baixar os bits e preparar um arquivo VHDX (disco rígido virtual) da imagem ISO do Windows Server. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Baixar o Skype for Business Cloud Connector Edition instalador

1. No servidor host onde as VMs do Cloud Connector serão executados, baixe os arquivos de instalação: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) . 

    > [!IMPORTANT]
    > O servidor host deve poder acessar a Internet durante a instalação do Cloud Connector porque arquivos adicionais são baixados durante a instalação. 

2. Execute o instalador e aceite os valores padrão durante a instalação.

3. Confirme se a instalação foi concluída com êxito.

## <a name="verify-the-installation-and-configure-the-environment"></a>Verificar a instalação e configurar o ambiente

1. Abra um console do PowerShell como administrador e confirme se os cmdlets Skype for Business Cloud Connector Edition estão disponíveis usando o seguinte cmdlet:

   ```powershell
   Get-Command *-Cc*
   ```

    O comando deve retornar uma lista de cmdlets para Skype for Business Cloud Connector Edition.

2. Os arquivos VHDs, SfBBits e VersionInfo serão armazenados no **Diretório de Sites.**

    Você pode encontrar o local do **Diretório de Sites** com o seguinte cmdlet:

   ```powershell
   Get-CcSiteDirectory
   ```

    O comando deve retornar um local em seu sistema de arquivos. O local pode ser uma pasta local ou um compartilhamento de arquivos. O local padrão para o **Diretório de Sites** é: %USERPROFILE%\CloudConnector\SiteRoot. O local padrão deve ser alterado para um compartilhamento de arquivos no primeiro dispositivo criado em cada site.

    O local selecionado deve ser:

   - Criado no primeiro dispositivo criado em cada site.

   - Uma pasta compartilhada acessível pelos outros servidores host (dispositivos) no mesmo site.

     Para definir o **Diretório de Sites** para um local diferente do padrão, execute o seguinte cmdlet:

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Se você estiver implantando alta disponibilidade (HA) para o site, execute o cmdlet para definir o Diretório de **Sites** para o mesmo local em cada servidor host no site.

    Ao fazer logon e implantar cada dispositivo no site, certifique-se de que sua conta de logon atual tenha o acesso certo ao **Diretório de Sites.**

3. O **Diretório de Dispositivos** é o diretório raiz de trabalho local para Skype for Business Cloud Connector Edition e o local onde certificados externos, instâncias e logs são salvos. O local padrão é: %USERPROFILE%\CloudConnector\ApplianceRoot.

    Para localizar o local do **Diretório de Dispositivos,** execute o seguinte cmdlet:

   ```powershell
   Get-CcApplianceDirectory
   ```

    Para definir o **Diretório de Dispositivos** como um local diferente do padrão, execute o seguinte cmdlet:

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    O Diretório de Dispositivos deve ser definido como uma pasta local no dispositivo. Você só deve definir **o Diretório do Appliance antes** de iniciar a Skype for Business Cloud Connector Edition implantação. Se você alterá-lo após a implantação, precisará reimplantar o servidor host.

    > [!IMPORTANT]
    > O caminho para o **Diretório do Dispositivo** não deve conter espaços.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Definir o caminho para o certificado de Borda externo

- Execute o cmdlet a seguir para definir o caminho, incluindo o nome do arquivo, para o certificado de Borda externo. Por exemplo: C:\certs\cce\ap.contoso.com.pfx. O certificado deve conter chaves privadas.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Observe que o parâmetro -Target é específico das versões 1.4.2 e posteriores. 

    Especifique o caminho completo para o certificado externo, incluindo o nome do arquivo. O certificado pode ser armazenado localmente ou em um compartilhamento de arquivos. Se o certificado for armazenado em uma pasta compartilhada, a pasta compartilhada deverá ser criada no primeiro dispositivo de cada site e deverá ser acessível por outros dispositivos pertencentes ao mesmo site. Este cmdlet copia o certificado externo para o **Diretório de Dispositivos.**

    > [!IMPORTANT]
    > Se você tiver atualizado para o Cloud Connector versão **1.4.2** ou posterior , certifique-se de que seu certificado externo preparado contenha chaves privadas e a cadeia de certificados completa, incluindo o certificado de AC raiz e os certificados ca intermediários. Se você ainda não tiver atualizado para o **Cloud Connector versão 1.4.2**, certifique-se de que seu certificado externo preparado contenha chaves privadas. Esse certificado externo deve ser emitido por uma Autoridade de Certificação confiável Windows por padrão.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Definir o caminho para o gateway PSTN externo/certificado SBC

Se você estiver usando o TLS entre o Servidor de Mediação e o gateway PSTN/SBC, execute o cmdlet a seguir para definir o caminho, incluindo o nome do arquivo, para o certificado de gateway. Por exemplo: C:\certs\cce\sbc.contoso.com.cer. O certificado deve conter a CA raiz e a cadeia intermediária do certificado atribuído ao gateway:

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Observe que o parâmetro -Target é específico das versões 1.4.2 e posteriores. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Criar comutadores virtuais no Hyper-V Manager

1. Abra o Gerenciador de Comutor Virtual do **Hyper-V**  >  **Manager** e selecione **Novo Gerenciador de Comuleções Virtuais.**

2. Crie uma opção virtual externa e a vinecte ao adaptador de rede físico que está conectado ao seu domínio de rede interno:

    Selecione **Permitir que o sistema operacional de gerenciamento compartilhe esse adaptador de rede** para essa opção virtual.

3. Crie uma opção virtual externa e a vin ligue ao adaptador de rede físico roteado para a Internet:

    Des selecione **Permitir que o sistema operacional de gerenciamento compartilhe esse adaptador de rede** para essa opção virtual.

4. De definir o nome da opção que conecta sua rede de perímetro ao seu domínio de rede **interno SfB CCE Corpnet Switch**.

    De definir o nome da opção que conecta sua rede de perímetro ao Internet **SfB CCE Internet Switch**.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Atualizar o arquivo CloudConnector.ini configuração

Prepare o arquivo CloudConnector.ini usando as informações coletadas em [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the Plan for [Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.

Para atualizar o arquivo, primeiro execute o seguinte cmdlet para obter o modelo de exemplo (CloudConnector.Sample.ini):

```powershell
Export-CcConfigurationSampleFile
```

O modelo de exemplo é armazenado no **Diretório de Dispositivos**.

Depois de atualizá-lo com os valores do seu ambiente, salve o arquivo como CloudConnector.ini no **Diretório do Dispositivo.** Você pode executar **Get-CcApplianceDirectory** para determinar o caminho para o **Diretório do Appliance**.

Ao atualizar o arquivo .ini, considere o seguinte:

> [!NOTE]
> Nem todos os valores para o arquivo .ini são discutidos nesta seção, apenas aqueles com uma consideração especial são abordados aqui. Para uma lista completa, consulte a seção [Determinar parâmetros de implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) do [tópico Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md) Para obter mais informações sobre quais valores precisam ser alterados para dispositivos adicionais ou novos sites, consulte Site único com alta disponibilidade [(HA)](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) em comparação com implantações de vários sites no tópico Implantar vários sites no [Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName:** O valor padrão é **Site1**. Você deve atualizá-lo antes de implantar o Cloud Connector, porque quando você executar **Register-CcAppliance** para registrar um dispositivo em um site existente ou novo, o cmdlet usará **SiteName** para determinar qual site registrar.

     Se você quiser registrar o dispositivo em um novo site, o valor **de SiteName** deve ser exclusivo e diferente dos sites existentes. Se você quiser registrar o dispositivo em um site existente, o valor de **SiteName** no arquivo .ini deve corresponder ao nome definido na configuração da sua Microsoft 365 ou Office 365 da organização. Se você estiver copiando um arquivo de configuração de um site para outro, atualize o valor de **SiteName** para cada site de acordo.

- **ServerName:** O nome do servidor não deve conter o nome de domínio e deve ser limitado a 15 caracteres.

- **HardwareType:** Se você não definir ou deixar o valor como nulo, o valor padrão de **Normal** será usado. Use **Normal** se você planeja implantar a versão maior do Cloud Connector para dar suporte a 500 chamadas simultâneas por máquina host, conforme descrito em [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). Use **o Mínimo** para uma implantação menor que oferece suporte a 50 chamadas simultâneas.

- Opções virtuais de **Internet/Corpnet/Gerenciamento:**: Adicionar o nome das opções virtuais que você criou. Para a opção virtual de gerenciamento, deixe o valor padrão. O script de implantação criará a opção virtual de gerenciamento no início da implantação e a excluirá quando a implantação for finalizado.

- **ManagementIPPrefix:** ManagementIPPrefix na seção Rede deve ser uma sub-rede diferente de outros IPs internos. Por exemplo, como o valor padrão mostra, ManagementIPPrefix é 192.168.213.0, enquanto a AD IPAddress é 192.168.0.238.

    Os scripts de implantação criam um adaptador de rede de gerenciamento em cada máquina virtual, atribuem um IP de gerenciamento e o conectam a uma opção virtual de gerenciamento. Isso permite que o servidor host se conecte e gerencie cada máquina virtual por meio dessa rede de gerenciamento. A opção virtual de gerenciamento é excluída quando a implantação é concluída.

- **Configurações específicas da VM base:** Configurações nesta seção devem ser configuradas para o cmdlet **Convert-CcIsoToVhdx.**

    Durante a preparação da imagem da VM base, a VM base será conectada à opção de rede interna. As configurações a seguir são fundamentais para que a VM possa acessar a Internet:

  - [Comum] BaseVMIP: o endereço IP de corpnet a ser atribuído à VM base.

  - [Rede] CorpnetDefaultGateway: o gateway padrão a ser atribuído à VM base.

  - [Rede] CorpnetDNSIPAddress: o endereço IP DNS a ser atribuído à VM base.

  - [Rede] WSUSServer: o endereço IP do Windows Server Update.

  - [Rede] WSUSStatusServer: o endereço IP do servidor Windows de status do Serviço de Atualização do Servidor.

  - [Rede] EnableReferSupport: isso definirá se o suporte SIP REFER está habilitado ou desabilitado na Configuração do Tronco para seu IP/PBX.

- **IPs internos:**

  - Certifique-se de que a máscara de sub-rede CorpnetIPPrefixLength está correta.

  - Certifique-se de que não haja conflitos IP para esses IPs internos.

- **IPs externos:**

  - Para o IP público mr: especifique ExternalMRIPs para não NAT ou ExternalMRPublicIPs para NAT.

  - ExternalSIPIPs e ExternalMRIPs podem ser os mesmos.

  - Certifique-se de que a máscara de sub-rede InternetIPPrefixLength está correta.

  - Certifique-se de que não haja conflitos IP para esses IPs externos.

- **Gateways:**

  - Se você tiver apenas um gateway, remova a seção do gateway secundário. Se você tiver mais de dois gateways, crie seções adicionais copiando e colar o existente e atualizando-o.

  - Certifique-se de que o endereço IP e a porta dos gateways estão corretos.

  - Para dar suporte a HA de nível de gateway PSTN, deixe o gateway secundário e adicione os gateways adicionais que você usará. Você pode copiar e colar uma entrada existente e atualizá-la.

- Opcionalmente, você pode atualizar o valor LocalRoute para restringir os números de chamada de saída.

## <a name="download-the-bits-to-the-site-directory"></a>Baixar os bits para o Diretório do Site

Execute o seguinte cmdlet para baixar os arquivos de informações de bits e versão para o **Diretório do Site**:

```powershell
Start-CcDownload
```

> [!NOTE]
> Você precisa executar esta etapa apenas para o primeiro dispositivo. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Preparar disco virtual base (VHDX) do arquivo ISO baixado

Esta etapa prepara um arquivo VHDX (disco rígido virtual) Windows Server 2012 imagem ISO. O VHDX será usado para criar máquinas virtuais durante a implantação. Uma máquina virtual temporária (VM base) será criada e Windows Server 2012 será instalada a partir do arquivo ISO. Depois que a VM for criada, alguns componentes necessários serão instalados e a atualização Windows mais recente será aplicada. No final, a VM base será generalizada (sysprep) e limpa, deixando apenas o arquivo de disco virtual gerado.

> [!NOTE]
> Você precisa executar esta etapa apenas para o primeiro dispositivo. 

Antes de prosseguir com esta etapa, certifique-se de que a opção corpnet foi criada. Além disso, confirme se as configurações a seguir estão configuradas corretamente no arquivo CloudConnector.ini arquivo:

- [Rede] CorpnetSwitchName

- [Comum] BaseVMIP

- [Rede] CorpnetIPPrefixLength

- [Rede] CorpnetDefaultGateway

- [Rede] CorpnetDNSIPAddress

Inicie um console do PowerShell como administrador e execute o seguinte cmdlet para converter a imagem ISO em um disco rígido virtual (VHD):

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Especifique o caminho completo, incluindo o nome do arquivo, para a imagem ISO. Por exemplo: C:\ISO\WindowsServer2012R2.iso.

O arquivo VHD criado é armazenado na pasta **Diretório do Site** \Bits\VHD. Você pode obter o caminho para o **Diretório de Sites** executando o **Get-CcSiteDirectory**.

> [!IMPORTANT]
> Por padrão, as configurações de proxy não são configuradas na VM base. Se um proxy for necessário em seu ambiente de rede para atualizar a VM por meio do Windows Update, adicione a opção -PauseBeforeUpdate ao executar "Convert-CcIsoToVhdx". O script pausa antes Windows Atualizar e você terá a chance de configurar manualmente o proxy na VM. Depois que o proxy for configurado e a VM puder acessar a Internet, você poderá retomar o script para concluir as etapas restantes. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Criar VHDs para uma implantação de vários sites

Esta é uma etapa opcional que se aplica somente a implantações de vários sites.

Se você estiver implantando uma implantação de vários sites, não será necessário converter o ISO em um VHD para cada site. Você pode copiar o VHDX criado para o primeiro site para o servidor host de um segundo site.

 Copie o arquivo para o mesmo local do arquivo ( **Pasta Diretório** do Site \Bits\VHD) e com o mesmo nome de arquivo, no servidor host para um site adicional.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Definir a política de execução do PowerShell como RemoteSigned

Os scripts do PowerShell fornecidos exigem que a política de execução seja definida como RemoteSigned. Para ver a configuração atual, abra um console do PowerShell como administrador e execute o seguinte cmdlet:

```powershell
Get-ExecutionPolicy
```

Se ele não estiver definido como "RemoteSigned", execute o seguinte cmdlet para alterá-lo:

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Alterar a Política de Grupo local no computador host (versões 1.4.1 e anteriores)

> [!NOTE]
> Essa tarefa não é necessária para as versões 1.4.2 e posteriores do Cloud Connector. 

A conta CceService é criada durante a Skype for Business Cloud Connector Edition implantação. Ele executa o Serviço de Gerenciamento do Cloud Connector e requer permissão para desinstalar o cloudconnector.msi. Você deve alterar a configuração da política de grupo na máquina host do Cloud Connector para especificar que o registro do usuário não deve ser descarregado quando o usuário faz o login. Siga as etapas abaixo:

### <a name="to-change-the-group-policy-setting"></a>Para alterar a configuração de Política de Grupo

1. Abra o **Editor de Política de Grupo** executando gpedit.msc.

2. No Editor de Política de **Grupo,** navegue até Modelos Administrativos > Sistema > UserProfile > Não descarregar o registro do usuário com força no logoff do usuário. 

3. De definir seu valor como **Habilitado**.

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>Configurar sua Microsoft 365 ou Office 365 organização

Uma Microsoft 365 ou Office 365 com Skype for Business Online e Sistema de Telefonia é necessária. Certifique-se de que o locatário está configurado e configurado antes de tentar usar o Cloud Connector.

Algumas Microsoft 365 e Office 365 de instalação exigem que você use o TRPS (Tenant Remote PowerShell) para configurar sua organização Microsoft 365 ou Office 365 locatário. **Isso deve ser instalado no servidor host.** Você pode baixar o módulo Skype for Business Online do PowerShell em: [Skype for Business Online, Windows PowerShell Módulo](https://www.microsoft.com/download/details.aspx?id=39366).

Crie uma conta de administrador Skype for Business para gerenciamento online do Cloud Connector, por exemplo, CceOnlineManagmentAdministrator. Essa conta será usada pelo dispositivo para adicionar ou remover dispositivo, habilitar ou desabilitar a atualização automática do sistema operacional, habilitar ou desabilitar a atualização binária automática. De definir a senha dessa conta para nunca expirar para que você não precise alterá-la para o serviço sempre que ela expirar.