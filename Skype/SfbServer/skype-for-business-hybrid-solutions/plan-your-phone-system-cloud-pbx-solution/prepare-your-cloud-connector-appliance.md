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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Saiba mais sobre como preparar seu dispositivo do Cloud Connector para implantação e uso com o sistema de telefonia no Office 365 (Cloud PBX).
ms.openlocfilehash: 21943dfd8b86bfeabb4cbd28b501b80a3f2b5c45
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779237"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Preparar o dispositivo do Cloud Connector

Saiba mais sobre como preparar seu dispositivo do Cloud Connector para implantação e uso com o sistema de telefonia no Office 365 (Cloud PBX).

Esta seção descreve como obter os arquivos de instalação do Skype for Business Cloud Connector Edition, instalar o software do Cloud Connector e preparar o dispositivo do Cloud Connector para implantação. Após concluir todas as etapas desta seção, você estará pronto para implantar o Cloud Connector para um único site ou vários sites. Se você tiver uma implantação do Cloud Connector existente e ainda não tiver atualizado para o Cloud Connector versão 2,1, consulte [upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> A Microsoft oferece suporte à versão atual do Cloud Connector Edition, versão 2,1. Se você configurou a atualização automática, o Cloud Connector será atualizado automaticamente. Se você configurou a atualização manual, será necessário atualizar para a versão 2,1 dentro de 60 dias de seu lançamento. A Microsoft dará suporte à versão anterior por 60 dias após o lançamento de 2,1 para permitir a atualização. 

> [!NOTE]
> Para o Cloud Connector versão 2,1 e posterior, o dispositivo host deve ter o .NET Framework 4.6.1 ou posterior instalado. 

> [!IMPORTANT]
> Para uma implantação bem-sucedida, ao executar os cmdlets para configurar o Skype for Business Cloud Connector Edition, use sempre a mesma sessão de console do que você iniciou. Evite mudar para sessões diferentes durante a implantação e a configuração. 

> [!NOTE]
> Há algumas etapas que você executa apenas para o primeiro dispositivo em sua implantação: criar um compartilhamento para o diretório de sites, baixar os bits e preparar um arquivo de disco rígido virtual (VHDX) a partir da imagem ISO do Windows Server. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Baixar o instalador do Skype for Business Cloud Connector Edition

1. No servidor host onde as VMs do Cloud Connector serão executadas, baixe os arquivos de instalação [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller):. 

    > [!IMPORTANT]
    > O servidor host deve poder acessar a Internet durante a instalação do Cloud Connector porque arquivos adicionais são baixados durante a instalação. 

2. Execute o instalador e aceite os valores padrão durante a instalação.

3. Confirme se a instalação foi concluída com êxito.

## <a name="verify-the-installation-and-configure-the-environment"></a>Verificar a instalação e configurar o ambiente

1. Abra um console do PowerShell como administrador e confirme se os cmdlets do Skype for Business Cloud Connector Edition estão disponíveis usando o seguinte cmdlet:

   ```powershell
   Get-Command *-Cc*
   ```

    O comando deve retornar uma lista de cmdlets para o Skype for Business Cloud Connector Edition.

2. Os arquivos VHDs, SfBBits e VersionInfo serão armazenados no **diretório de sites**.

    Você pode encontrar o local do **diretório de sites** com o seguinte cmdlet:

   ```powershell
   Get-CcSiteDirectory
   ```

    O comando deve retornar um local no sistema de arquivos. O local pode ser uma pasta local ou um compartilhamento de arquivos. O local padrão para o **diretório de sites** é:%userprofile%\CloudConnector\SiteRoot. O local padrão deve ser alterado para um compartilhamento de arquivos no primeiro dispositivo criado em cada site.

    O local selecionado deve ser:

   - Criado no primeiro dispositivo criado em cada site.

   - Uma pasta compartilhada acessível pelos outros servidores host (dispositivos) no mesmo site.

     Para definir o **diretório de sites** para um local diferente do padrão, execute o seguinte cmdlet:

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Se você estiver implantando a alta disponibilidade (HA) para o site, certifique-se de executar o cmdlet para definir o **diretório de sites** para o mesmo local em cada servidor host no site.

    Ao fazer logon e implantar cada dispositivo no site, certifique-se de que sua conta de logon atual tenha o acesso certo ao **diretório de sites**.

3. O **diretório de dispositivos** é o diretório raiz de trabalho local para o Skype for Business Cloud Connector Edition e o local onde certificados, instâncias e logs externos são salvos. O local padrão é:%USERPROFILE%\CloudConnector\ApplianceRoot.

    Para encontrar o local do **diretório de dispositivos**, execute o seguinte cmdlet:

   ```powershell
   Get-CcApplianceDirectory
   ```

    Para definir o **diretório de dispositivos** para um local diferente do padrão, execute o seguinte cmdlet:

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    O diretório de dispositivos deve ser definido como uma pasta local no dispositivo. Você só deve definir o **diretório de dispositivos** antes de iniciar a implantação do Skype for Business Cloud Connector Edition. Se você alterá-lo após a implantação, será necessário reimplantar o servidor host.

    > [!IMPORTANT]
    > O caminho para o **diretório de dispositivos** não deve conter espaços.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Definir o caminho para o certificado de borda externa

- Execute o cmdlet a seguir para definir o caminho, incluindo o nome do arquivo, para o certificado de borda externa. Por exemplo: C:\certs\cce\ap.contoso.com.pfx. O certificado deve conter chaves privadas.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Observe que o parâmetro-Target é específico para as versões 1.4.2 e posteriores. 

    Especifique o caminho completo para o certificado externo, incluindo o nome do arquivo. O certificado pode ser armazenado localmente ou em um compartilhamento de arquivos. Se o certificado estiver armazenado em uma pasta compartilhada, a pasta compartilhada deverá ser criada no primeiro dispositivo de cada site e deve ser acessível por outros dispositivos que pertençam ao mesmo site. Este cmdlet copia o certificado externo para o **diretório de dispositivos**.

    > [!IMPORTANT]
    > **Se você tiver atualizado para o Cloud Connector versão 1.4.2 ou posterior**, certifique-se de que seu certificado externo preparado contém chaves privadas e a cadeia de certificados completa, incluindo o certificado de autoridade de certificação raiz e os certificados de autoridade de certificação intermediários. **Se você ainda não tiver atualizado para o Cloud Connector versão 1.4.2**, verifique se o certificado externo preparado contém chaves privadas. Esse certificado externo deve ser emitido por uma autoridade de certificação que é confiável para o Windows por padrão.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Definir o caminho para o gateway PSTN externo/certificado SBC

Se você estiver usando o TLS entre o servidor de mediação e o gateway PSTN/SBC, execute o seguinte cmdlet para definir o caminho, incluindo o nome do arquivo, para o certificado de gateway. Por exemplo: C:\certs\cce\sbc.contoso.com.cer. O certificado deve conter a autoridade de certificação raiz e a cadeia intermediária para o certificado atribuído ao gateway:

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Observe que o parâmetro-Target é específico para as versões 1.4.2 e posteriores. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Criar comutadores virtuais no Hyper-V Manager

1. Abra o > **Gerenciador de comutador virtual**do **Gerenciador do Hyper-V**e selecione **novo Gerenciador de comutador virtual**.

2. Crie um comutador virtual externo e associe-o ao adaptador de rede física que está conectado ao seu domínio de rede interna:

    Selecione **permitir sistema operacional de gerenciamento para compartilhar este adaptador de rede** para esse comutador virtual.

3. Crie um comutador virtual externo e vincule-o ao adaptador de rede física que é roteado para a Internet:

    Desmarque **a opção permitir que o sistema operacional de gerenciamento Compartilhe este adaptador de rede** para esse comutador virtual.

4. Defina o nome do comutador que conecta sua rede de perímetro ao seu domínio de rede interna **SfB o comutador do CCE corpnet**.

    Defina o nome do comutador que conecta sua rede de perímetro ao **comutador Internet SFB CCE**.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Atualize o arquivo de configuração do CloudConnector. ini

Prepare o arquivo CloudConnector. ini usando as informações coletadas em [determinar parâmetros de implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) no tópico [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .

Para atualizar o arquivo, primeiro execute o cmdlet a seguir para obter o modelo de exemplo (CloudConnector. Sample. ini):

```powershell
Export-CcConfigurationSampleFile
```

O modelo de exemplo é armazenado no **diretório de dispositivos**.

Depois de atualizá-lo com os valores para seu ambiente, salve o arquivo como CloudConnector. ini no **diretório de dispositivos**. Você pode executar o **Get-CcApplianceDirectory** para determinar o caminho para o **diretório de dispositivos**.

Ao atualizar o arquivo. ini, considere o seguinte:

> [!NOTE]
> Nem todos os valores para o arquivo. ini são abordados nesta seção, apenas aqueles com uma consideração especial são abordados aqui. Para obter uma lista completa, consulte a seção [determinar parâmetros de implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) do tópico [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) . Para obter mais informações sobre quais valores precisam ser alterados para dispositivos adicionais ou novos sites, consulte [single site com alta disponibilidade (ha) em comparação a implantações de vários sites](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) no tópico [implantar vários sites no Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName:** O valor padrão é **site1**. Você deve atualizá-lo antes de implantar o Cloud Connector, porque ao executar o **Register-CcAppliance** para registrar um dispositivo em um site existente ou novo, o cmdlet usará **SiteName** para determinar qual site será registrado.

     Se você deseja registrar o dispositivo em um novo site, o valor de **SiteName** deve ser exclusivo e diferente dos sites existentes. Se você deseja registrar o dispositivo em um site existente, o valor de **SiteName** no arquivo. ini deve corresponder ao nome definido na sua configuração de organização do Office 365. Se você estiver copiando um arquivo de configuração de um site para outro, certifique-se de atualizar o valor de **SiteName** para cada site adequadamente.

- **ServerName:** O nome do servidor não deve conter o nome do domínio e deve ser limitado a 15 caracteres.

- **HardwareType:** Se você não definir ou deixar o valor como nulo, o valor padrão **normal** será usado. Use **normal** se você planeja implantar a versão maior do Cloud Connector para dar suporte a 500 chamadas simultâneas por máquina host, conforme descrito em [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). Use **mínimo** para uma implantação menor que dê suporte a 50 chamadas simultâneas.

- **Opções virtuais de Internet/corpnet/gerenciamento:**: Adicione o nome dos comutadores virtuais que você criou. Para o comutador virtual de gerenciamento, deixe o valor padrão. O script de implantação criará o comutador virtual de gerenciamento no início da implantação e o excluirá quando a implantação terminar.

- **ManagementIPPrefix:** ManagementIPPrefix na seção rede deve ser uma sub-rede diferente de outros IPs internos. Por exemplo, como o valor padrão mostra, ManagementIPPrefix é 192.168.213.0, enquanto o AD IPAddress é 192.168.0.238.

    Os scripts de implantação criam um adaptador de rede de gerenciamento em cada máquina virtual, atribuem um IP de gerenciamento e o conectam a um comutador virtual de gerenciamento. Isso permite que o servidor host se conecte e gerencie cada máquina virtual por meio desta rede de gerenciamento. O comutador virtual de gerenciamento é excluído quando a implantação é concluída.

- **Configurações específicas da VM base:** As configurações nesta seção devem ser configuradas para o cmdlet **Convert-CcIsoToVhdx** .

    Durante a preparação da imagem da VM base, a VM base será conectada ao comutador da rede interna. As configurações a seguir são fundamentais para que a VM possa acessar a Internet:

  - Convencionais BaseVMIP: o endereço IP corpnet a ser atribuído à VM base.

  - Rede CorpnetDefaultGateway: o gateway padrão a ser atribuído à VM base.

  - Rede CorpnetDNSIPAddress: o endereço IP de DNS a ser atribuído à VM base.

  - Rede WSUSServer: o endereço IP do serviço de atualização do Windows Server.

  - Rede Wsusserver: o endereço IP do servidor de status do Windows Server Update Service.

  - Rede EnableReferSupport: isso definirá se o suporte a SIP REFERENCIAr está habilitado ou desabilitado na configuração do tronco para o IP/PBX.

- **IPs internos:**

  - Verifique se a máscara de sub-rede CorpnetIPPrefixLength está correta.

  - Certifique-se de que não haja conflitos de IP para esses IPs internos.

- **IPs externos:**

  - Para o IP público do Sr: especifique ExternalMRIPs para não NAT ou ExternalMRPublicIPs para NAT.

  - ExternalSIPIPs e ExternalMRIPs podem ser os mesmos.

  - Verifique se a máscara de sub-rede InternetIPPrefixLength está correta.

  - Certifique-se de que não haja conflitos de IP para esses IPs externos.

- **Gateways**

  - Se você tiver apenas um gateway, remova a seção do gateway secundário. Se você tiver mais de dois gateways, crie seções adicionais copiando e colando a existente e, em seguida, atualizando-a.

  - Verifique se o endereço IP e a porta do (s) gateway (s) estão corretos.

  - Para dar suporte à alta disponibilidade no nível do gateway PSTN, mantenha o gateway secundário e adicione os gateways adicionais que você usará. Você pode copiar e colar uma entrada existente e depois atualizá-la.

- Opcionalmente, você pode atualizar o valor LocalRoute para restringir os números de chamada de saída.

## <a name="download-the-bits-to-the-site-directory"></a>Baixar os bits para o diretório de sites

Execute o seguinte cmdlet para baixar os arquivos de informações de versão e bits para o **diretório de sites**:

```powershell
Start-CcDownload
```

> [!NOTE]
> Você precisa executar esta etapa somente para o primeiro dispositivo. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Preparar o disco virtual base (VHDX) do arquivo ISO baixado

Esta etapa prepara um arquivo de disco rígido virtual (VHDX) da imagem ISO do Windows Server 2012. O VHDX será usado para criar máquinas virtuais durante a implantação. Uma máquina virtual temporária (VM base) será criada e o Windows Server 2012 será instalado a partir do arquivo ISO. Após a criação da VM, alguns componentes necessários serão instalados e a atualização mais recente do Windows será aplicada. No final, a VM base será generalizada (Sysprep) e limpa, deixando apenas o arquivo de disco virtual gerado.

> [!NOTE]
> Você precisa executar esta etapa somente para o primeiro dispositivo. 

Antes de prosseguir com esta etapa, verifique se a opção corpnet foi criada. Além disso, confirme se as configurações a seguir estão configuradas corretamente no arquivo CloudConnector. ini:

- Rede CorpnetSwitchName

- Convencionais BaseVMIP

- Rede CorpnetIPPrefixLength

- Rede CorpnetDefaultGateway

- Rede CorpnetDNSIPAddress

Inicie um console do PowerShell como administrador e execute o cmdlet a seguir para converter a imagem ISO em um VHD (disco rígido virtual):

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Especifique o caminho completo, incluindo o nome do arquivo, para a imagem ISO. Por exemplo: C:\ISO\WindowsServer2012R2.iso.

O arquivo VHD criado é armazenado na pasta \Bits\VHD do **diretório de sites** . Você pode obter o caminho para o **diretório de sites** executando o **Get-CcSiteDirectory**.

> [!IMPORTANT]
> Por padrão, as configurações de proxy não são configuradas na VM base. Se um proxy for necessário em seu ambiente de rede para atualizar a VM por meio do Windows Update, adicione a opção-PauseBeforeUpdate ao executar "Convert-CcIsoToVhdx". O script será pausado antes do Windows Update e você terá a oportunidade de configurar manualmente o proxy na VM. Depois que o proxy é configurado e a VM pode acessar a Internet, você pode retomar o script para concluir as etapas restantes. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Criar VHDs para uma implantação de vários sites

Esta é uma etapa opcional que se aplica somente a implantações de vários sites.

Se você estiver implantando uma implantação de vários sites, não será necessário converter o ISO em um VHD para cada site. Você pode copiar o VHDX criado para o primeiro site para o servidor host de um segundo site.

 Copie o arquivo para o mesmo local de arquivo (pasta \Bits\VHD **do diretório de sites** ) e com o mesmo nome de arquivo, no servidor host de um site adicional.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Definir a política de execução do PowerShell como RemoteSigned

Os scripts do PowerShell fornecidos exigem que a política de execução seja definida como RemoteSigned. Para ver a configuração atual, abra um console do PowerShell como administrador e execute o seguinte cmdlet:

```powershell
Get-ExecutionPolicy
```

Se não estiver definida como "RemoteSigned", execute o seguinte cmdlet para alterá-la:

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Alterar a política de grupo local na máquina host (versões 1.4.1 e anteriores)

> [!NOTE]
> Esta tarefa não é necessária para o Cloud Connector versões 1.4.2 e posteriores. 

A conta CceService é criada durante a implantação do Skype for Business Cloud Connector Edition. Ele executa o serviço de gerenciamento do Cloud Connector e exige permissão para desinstalar o cloudconnector. msi. Você deve alterar a configuração da política de grupo na máquina host do Cloud Connector para especificar que o registro do usuário não deve ser descarregado quando o usuário fizer logoff. Siga as etapas abaixo:

### <a name="to-change-the-group-policy-setting"></a>Para alterar a configuração da política de grupo

1. Abra o **Editor de política de grupo** executando gpedit. msc.

2. No **Editor de política de grupo**, navegue até modelos administrativos > sistema > USERPROFILE > não descarregue o registro do usuário de maneira forçada no logoff do usuário. 

3. Defina seu valor como **habilitado**.

## <a name="set-up-your-office-365-organization"></a>Configurar sua organização do Office 365

É necessária uma organização do Office 365 com o Skype for Business Online e o sistema de telefonia do Office 365. Verifique se seu locatário está definido e configurado antes de tentar usar o Cloud Connector.

Algumas etapas de configuração do Office 365 exigem que você use o PowerShell Remote locatário (TRPS) para configurar sua organização do Office 365. **Isso deve ser instalado no servidor host.** Você pode baixar o módulo do Skype for Business online para PowerShell de: [Skype for Business Online, módulo do Windows PowerShell](https://www.microsoft.com/download/details.aspx?id=39366).

Crie uma conta de administrador dedicada do Skype for Business para o gerenciamento online do Cloud Connector, por exemplo,, Cceonlinemanagmentadministrator. Essa conta será usada pelo dispositivo para adicionar ou remover um dispositivo, habilitar ou desabilitar a atualização automática do sistema operacional, habilitar ou desabilitar a atualização binária automática. Defina a senha dessa conta como nunca expirar para que você não precise alterá-la para o serviço sempre que ela expirar.


