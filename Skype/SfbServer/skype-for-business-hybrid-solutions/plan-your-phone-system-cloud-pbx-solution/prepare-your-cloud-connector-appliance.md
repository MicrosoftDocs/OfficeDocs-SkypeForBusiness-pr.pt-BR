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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Saiba como preparar seu aparelho do Cloud Connector para implantação e uso com o sistema telefônico no Office 365 (Cloud PBX).
ms.openlocfilehash: f2140eb0be25ba0b6935f389e5ae7b27bfc37359
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286996"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Preparar o dispositivo do Cloud Connector

Saiba como preparar seu aparelho do Cloud Connector para implantação e uso com o sistema telefônico no Office 365 (Cloud PBX).

Esta seção descreve como obter os arquivos de instalação do Skype for Business Cloud Connector Edition, instalar o software do Cloud Connector e preparar o dispositivo do Cloud Connector para implantação. Depois de ter concluído todas as etapas desta seção, você estará pronto para implantar o Cloud Connector em um único site ou em vários sites. Se você tiver uma implantação existente do conector de nuvem e ainda não tiver atualizado para o Cloud Connector versão 2,1, confira [atualizar para uma nova versão do Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> A Microsoft oferece suporte à versão atual do Cloud Connector Edition, versão 2,1. Se você tiver configurado a atualização automática, o Cloud Connector será atualizado automaticamente. Se você configurou a atualização manual, será preciso atualizar para a versão 2,1 dentro de 60 dias após a sua versão. A Microsoft dará suporte à versão anterior por 60 dias após o lançamento do 2,1 para permitir que você atualize o tempo. 

> [!NOTE]
> Para o Cloud Connector versão 2,1 e posterior, o host Appliance deve ter o .NET Framework 4.6.1 ou posterior instalado. 

> [!IMPORTANT]
> Para uma implantação bem-sucedida, ao executar os cmdlets para configurar o Skype for Business Cloud Connector Edition, use sempre a mesma sessão de console que você iniciou. Evite alternar entre diferentes sessões durante a implantação e a configuração. 

> [!NOTE]
> Existem algumas etapas que você executa somente para o primeiro dispositivo de sua implantação: criar um compartilhamento para o diretório do site, baixar os bits e preparar um arquivo VHDX (disco rígido virtual) com a imagem ISO do Windows Server. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Baixar o instalador do Skype for Business Cloud Connector Edition

1. No servidor host onde as VMs do conector de nuvem serão executadas, baixe os arquivos de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)instalação:. 

    > [!IMPORTANT]
    > O servidor host precisa acessar a Internet durante a instalação do Cloud Connector porque arquivos adicionais são baixados durante a instalação. 

2. Execute o instalador e aceite os valores padrão durante a instalação.

3. Confirme se a instalação foi concluída com êxito.

## <a name="verify-the-installation-and-configure-the-environment"></a>Verificar a instalação e configurar o ambiente

1. Abra um console do PowerShell como administrador e confirme se os cmdlets do Skype for Business Cloud Connector Edition estão disponíveis usando o seguinte cmdlet:

   ```
   Get-Command *-Cc*
   ```

    O comando deve retornar uma lista de cmdlets para o Skype for Business Cloud Connector Edition.

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

    Ao fazer logon e implantar cada aplicativo no site, verifique se a conta de logon atual tem o acesso certo ao diretório de **sites**.

3. O **diretório de aplicativos** é o diretório raiz de trabalho local para o Skype for Business Cloud Connector Edition e o local onde certificados, instâncias e registros externos são salvos. O local padrão é: %USERPROFILE%\CloudConnector\ApplianceRoot.

    Você pode localizar o **Diretório de Sites** executando o seguinte cmdlet:

   ```
   Get-CcApplianceDirectory
   ```

    Para definir o **Diretório de Dispositivos** para um local diferente do padrão, execute o seguinte cmdlet:

   ```
   Set-CcApplianceDirectory <File path>
   ```

    O Diretório de Dispositivos deve ser definido em uma pasta local no dispositivo. Você só deve definir o **diretório do aparelho** antes de iniciar a implantação do Skype for Business Cloud Connector Edition. Se você alterá-lo após a implantação, será necessário reimplantar o servidor host.

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
    > **Se você tiver atualizado para o Cloud Connector versão 1.4.2 ou posteriores**, verifique se o certificado externo preparado contém chaves privadas e a cadeia completa de certificados, inclusive o certificado de Autoridade de Certificação raiz e os certificados de Autoridade de Certificação intermediária. **Se você NÃO tiver atualizado ainda para o Cloud Connector versão 1.4.2**, certifique-se de que  o certificado externo preparado contém chaves privadas. Esse certificado externo deve ser emitido pela Autoridade de Certificação que é confiável para o Windows por padrão.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Definir o caminho do certificado de gateway PSTN externo/SBC

Se você estiver usando o TLS entre o Servidor de Mediação e o gateway PSTN/SBC, execute o seguinte cmdlet para definir o caminho, incluindo o nome do arquivo, para o certificado de gateway. Por exemplo: C:\certs\cce\sbc.contoso.com.cer. O certificado deve conter a Autoridade de Certificação raiz e a cadeia intermediária para o certificado atribuído ao gateway:

```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Note que o parâmetro -Target é específico à versão 1.4.2 e posteriores. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Criar comutadores virtuais no Gerenciador do Hyper-V

1. Abra o**Gerenciador de comutador virtual**do **Hyper-V Manager** > e selecione **novo Gerenciador de comutador virtual**.

2. Crie um comutador virtual externo e associe-o ao adaptador de rede física que está conectado ao domínio da rede interna:

    Selecione a opção **Permitir que o sistema operacional de gerenciamento compartilhe este adaptador de rede** para esse comutador virtual.

3. Crie um comutador virtual externo e vincule-o ao adaptador de rede física que está roteado para a Internet:

    Desmarque **permitir que o sistema operacional de gerenciamento Compartilhe este adaptador de rede** para este comutador virtual.

4. Defina o nome da opção que conecta a sua rede de perímetro ao seu domínio da rede interna **SfB do CCE corpnet**.

    Defina o nome da opção que conecta a sua rede de perímetro à Internet **SFB CCE Internet**.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Atualizar o arquivo de configuração CloudConnector.ini

Prepare o arquivo CloudConnector. ini usando as informações coletadas em [determinar parâmetros de implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) no tópico [plano para o Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .

Para atualizar o arquivo, execute o seguinte cmdlet para obter o modelo (CloudConnector.Sample.ini):

```
Export-CcConfigurationSampleFile
```

O modelo é armazenado no **Diretório de Dispositivos**.

Depois de atualizá-lo com os valores para seu ambiente, salve o arquivo como CloudConnector.ini no **Diretório de Dispositivos**. Você pode executar o **Get-CcApplianceDirectory** para determinar o caminho do **Diretório de Dispositivos**.

Ao atualizar o arquivo .ini, considere o seguinte:

> [!NOTE]
> Nem todos os valores para o arquivo .ini são mencionados nesta seção, somente aqueles com uma consideração especial são incluídos aqui. Para obter uma lista completa, consulte a seção [determinar parâmetros de implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) do tópico [planejar para o Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) . Para obter mais informações sobre quais valores devem ser alterados para dispositivo adicionais ou novos sites, consulte [Único site com alta disponibilidade em comparação com implantações de vários sites](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) no tópico [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName:** o valor padrão é **Site1**. Você deve atualizá-lo antes de implantar o Cloud Connector, pois quando você executar **Register-CcAppliance** para registrar um dispositivo em um site novo ou existente, o cmdlet usará **SiteName** para determinar qual site registrar.

     Se você deseja registrar o dispositivo em um site novo, o valor de **SiteName** deverá ser exclusivo e diferente dos sites existentes. Se você quiser registrar o aplicativo em um site existente, o valor de **SiteName** no arquivo. ini deve corresponder ao nome definido na configuração do locatário do Office 365. Se você estiver copiando um arquivo de configuração de um site para outro, atualize o valor de **SiteName** devidamente para cada site.

- **ServerName:** O nome do servidor não deve conter o nome do domínio e deve ser limitado a 15 caracteres. 

- **HardwareType:** Se você não definir ou deixar o valor como NULL, o valor padrão de **normal** será usado. Use **normal** se você planeja implantar a versão maior do conector de nuvem para dar suporte a chamadas simultâneas de 500 por máquina host, conforme descrito em [plano para o Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). Use **Mínimo** para uma implantação menor que permita 50 chamadas simultâneas.

- **Comutadores virtuais de Internet/Corpnet/Gerenciamento**: adicione o nome dos comutadores criados. Para o comutador virtual de gerenciamento, apenas deixe o valor padrão. O script de implantação o criará no início da implantação e o excluirá quando a implantação terminar.

- **ManagementIPPrefix:** o ManagementIPPrefix, na seção Rede, deve ser uma sub-rede diferente dos outros IPs internos. Por exemplo, como o valor padrão mostra, ManagementIPPrefix é 192.168.213.0, enquanto o IPAddress do AD é 192.168.0.238.

    Os scripts de implantação criam um adaptador de rede de gerenciamento em cada máquina virtual, atribui a cada uma delas um IP de gerenciamento e as conecta a um comutador virtual de gerenciamento. Isso permite que o servidor host se conecte a todas as máquinas virtuais e as gerencie por meio da rede de gerenciamento. O comutador virtual de gerenciamento é excluído quando a implantação é concluída.

- **Configurações específicas da VM base:** as configurações apresentadas nesta seção devem ser configuradas para o cmdlet **Convert-CcIsoToVhdx**.

    Durante a preparação da imagem da VM base, ela será conectada ao comutador de rede interno. As seguintes configurações são essenciais para a VM acessar a Internet:

  - [Common]BaseVMIP: o endereço IP corpnet que será atribuído à VM base.

  - [Network]CorpnetDefaultGateway: o gateway padrão a ser atribuído à VM base.

  - [Network]CorpnetDNSIPAddress: o endereço IP do DNS que será atribuído à VM base.

  - [Network]WSUSServer: o endereço IP do Windows Server Update Service.

  - [Network]WSUSServer: o endereço IP do servidor de status do Windows Server Update Service.

  - [Network]EnableReferSupport: isso definirá se o suporte para SIP REFER está habilitado ou desabilitado na Configuração do Tronco em seu IP/PBX.

- **IPs externos:**

  - Verifique se a máscara de sub-rede CorpnetIPPrefixLength está correta.

  - Certifique-se de que não haja conflitos de IP para estes IPs internos.

- **IPs externos:**

  - Para o IP público do Sr: especifique ExternalMRIPs para não NAT ou ExternalMRPublicIPs para NAT.

  - ExternalSIPIPs e ExternalMRIPs podem ser iguais.

  - Verifique se a máscara de sub-rede InternetIPPrefixLength está correta.

  - Certifique-se de que não haja conflitos de IP para esses IPs externos.

- **Gateways:**

  - Se você tiver somente um gateway, remova a seção do gateway secundário. Se você tiver mais de dois gateways, crie seções adicionais copiando e colando a existente e atualizando-a depois.

  - Verifique se o endereço IP e a porta do(s) gateway(s) estão corretos.

  - Para dar suporte ao nível de alta disponibilidade do Gateway PSTN, saia do gateway secundário e adicione os gateways adicionais que você usará. Você pode copiar e colar uma entrada existente e atualizá-la.

- Opcionalmente, você pode atualizar o valor LocalRoute para restringir números de chamada de saída.

## <a name="download-the-bits-to-the-site-directory"></a>Baixar os bits para o Diretório de Sites

Execute o seguinte cmdlet para baixar os bits e os arquivos de informações de versão para o **Diretório de Sites**:

```
Start-CcDownload
```

> [!NOTE]
> Você deve executar esta etapa somente para o primeiro dispositivo. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Preparar VHDX (disco virtual base) usando o arquivo ISO baixado

Esta etapa prepara o VHDX (arquivo do disco virtual) a partir da imagem ISO do Windows Server 2012. O VHDX será usado para criar máquinas virtuais durante a implantação. Uma máquina virtual temporária (VM base) será criada e o Windows Server 2012 será instalado a partir do arquivo ISO. Após a VM ser criada, alguns componentes necessários serão instalados e a atualização mais recente do Windows será aplicada. Por fim, a VM base será generalizada (sysprep) e limpa, permanecendo apenas o arquivo de disco virtual gerado.

> [!NOTE]
> Você deve executar esta etapa somente para o primeiro dispositivo. 

Antes de continuar com esta etapa, verifique se o comutador corpnet foi criado. Além disso, confirme se as seguintes configurações estão corretas no arquivo CloudConnector.ini:

- [Network]CorpnetSwitchName

- [Common]BaseVMIP

- [Network]CorpnetIPPrefixLength

- [Network]CorpnetDefaultGateway

- [Network]CorpnetDNSIPAddress

Inicie um console do PowerShell como administrador e execute o seguinte cmdlet para converter a imagem ISO em um VHD:

```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Especifique o caminho completo da imagem ISO. Inclua o nome do arquivo. Por exemplo: C:\ISO\WindowsServer2012R2.iso.

O arquivo VHD criado é armazenado na pasta \Bits\VHD do **diretório de sites** . Você pode obter o caminho do **Diretório de Sites** executando **Get-CcSiteDirectory**.

> [!IMPORTANT]
> Por padrão, as configurações de proxy não são definidas na VM base. Se um proxy for necessário em seu ambiente de rede para atualizar a VM via Windows Update, você deve adicionar a opção-PauseBeforeUpdate ao executar "Convert-CcIsoToVhdx". O script será pausado antes do Windows Update e você terá a chance de configurar manualmente o proxy na VM. Quando a configuração do proxy for concluída e a VM conseguir acessar a Internet, você poderá retomar o script para concluir as etapas restantes. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Criar VHDs para a implantação de vários sites

Esta é uma etapa opcional que se aplica apenas a implantações de vários sites.

Se você estiver fazendo uma implantação de vários sites, não será necessário converter ISO em um VHD para cada site. É possível copiar o VHDX criado para o primeiro site para o servidor host de um segundo site.

 Copie o arquivo para o mesmo local de arquivo (pasta \Bits\VHD **do diretório de sites** ) e com o mesmo nome de arquivo no servidor host de um site adicional.

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

A conta CceService é criada durante a implantação do Skype for Business Cloud Connector Edition. Ele executa o serviço de gerenciamento do Cloud Connector e requer permissão para desinstalar o cloudconnector. msi. Você deve alterar a configuração da política de grupo na máquina host do Cloud Connector para especificar que o registro do usuário não deve ser descarregado quando o usuário se desconecta. Siga estas etapas:

### <a name="to-change-the-group-policy-setting"></a>Para alterar a configuração da Política de Grupo

1. Abra o **Editor de política de grupo** executando gpedit. msc.

2. No **Editor de Política de Grupo**, navegue até Modelos Administrativos > Sistema > Perfil de Usuário > Não descarregar forçosamente o Registro do usuário no logoff do usuário.  

3. Defina seu valor como **Enabled**.

## <a name="set-up-your-office-365-tenant"></a>Configure o locatário do Office 365

É necessário um locatário do Office 365 com o Skype for Business Online e o sistema telefônico no Office 365. Certifique-se de que seu locatário esteja configurado e configurado antes de tentar usar o conector de nuvem.

Algumas etapas de configuração do Office 365 exigem que você use o PowerShell Remote locatário (TRPS) para configurar seu locatário do Office 365. **Isso deve ser instalado no servidor host.** Você pode baixar o módulo Skype for Business online para PowerShell de: [Skype for Business Online, módulo do Windows PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Crie uma conta de administrador dedicada do Skype for Business para o gerenciamento online do conector de nuvem, por exemplo, CceOnlineManagmentAdministrator. Essa conta será usada pelo dispositivo para adicionar ou remover dispositivos, habilitar ou desabilitar a atualização automática do sistema operacional, habilitar ou desabilitar a atualização automática de binários. Defina a senha dessa conta como nunca expirar, assim não será necessário alterá-la para o serviço sempre que ela expirar.


