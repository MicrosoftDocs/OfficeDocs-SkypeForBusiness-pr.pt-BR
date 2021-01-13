---
title: Configurar a autenticação de dois fatores no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Resumo: Configure a autenticação de dois fatores no Skype for Business Server.'
ms.openlocfilehash: a7c5b4489b6b39e924a85c5e99796044d892c11f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814411"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Configurar a autenticação de dois fatores no Skype for Business Server

**Resumo:** Configure a autenticação de dois fatores no Skype for Business Server.

As seções a seguir descrevem as etapas necessárias para configurar a autenticação de dois fatores para sua implantação. Para obter mais informações sobre a autenticação de dois fatores, consulte Habilitando a autenticação [multifatório do Office 365](https://go.microsoft.com/fwlink/p/?LinkId=313332)para administradores online - Postagem de usuário de grade.

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurar uma autoridade de certificação raiz corporativa para dar suporte à autenticação de cartão inteligente

As etapas a seguir descrevem como configurar uma AC raiz corporativa para dar suporte à Autenticação de Cartão Inteligente:

Para obter informações sobre como instalar uma AUTORIDADE de Certificação Raiz Corporativa, consulte Instalar uma Autoridade de [Certificação Raiz Empresarial.](https://go.microsoft.com/fwlink/p/?LinkID=313364)

1. Faça logoff no computador da AC corporativa usando uma conta de Administrador de Domínio.

2. Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.

3. No menu **Ferramentas Administrativas,** abra o console **de gerenciamento da Autoridade** de Certificação.

4. No painel de navegação, expanda a Autoridade **de Certificação.**

5. Clique com o botão direito do mouse em Modelos de **Certificado,** selecione **Novo** e Selecione **Modelo de Certificado a Ser Emitido.**

6. Selecione **Agente de Registro,** **Usuário do Cartão** Inteligente e **Logon do Cartão Inteligente.**

7. Clique em **OK**.

8. Clique com o botão direito do mouse **em Modelos de Certificado.**

9. Selecione **Gerenciar**.

10. Abra as propriedades do modelo usuário cartão inteligente.

11. Clique na **guia** Segurança.

12. Altere as permissões da seguinte forma:

    - Adicionar contas do AD de usuário individual com permissões de Leitura/Registro (Permitir) ou

    - Adicionar um grupo de segurança contendo usuários de cartão inteligente com permissões de Leitura/Registro (Permitir) ou

    - Adicionar o grupo Usuários do Domínio com permissões de Leitura/Registro (Permitir)

## <a name="configure-windows-8-for-virtual-smart-cards"></a>Configurar o Windows 8 para cartões inteligentes virtuais

Um fator a ser considerado ao implantar a autenticação de dois fatores e a tecnologia de cartão inteligente é o custo da implementação. O Windows 8 oferece vários novos recursos de segurança, e um dos novos recursos mais interessantes é o suporte a cartões inteligentes virtuais.

Para computadores equipados com um chip TPM (Trusted Platform Module) que atenda à especificação versão 1.2, as organizações agora podem obter os benefícios do logon de cartão inteligente sem fazer investimentos adicionais em hardware. Para obter mais informações, consulte [Usando cartões inteligentes virtuais com o Windows 8.](https://go.microsoft.com/fwlink/p/?LinkId=313365)

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Para configurar o Windows 8 para cartões inteligentes virtuais

1. Entre no computador com Windows 8 usando as credenciais de um usuário habilitado para Skype for Business.

2. Na tela inicial do Windows 8, mova o cursor para o canto inferior direito da tela.

3. Selecione a **opção** Pesquisar e pesquise Prompt de Comando.

4. Clique com o botão **direito do mouse** no Prompt de Comando e selecione Executar como **Administrador.**

5. Abra o console de gerenciamento do Trusted Platform Module (TPM) executando o seguinte comando:

  ```console
  Tpm.msc
  ```

6. No console de gerenciamento do TPM, verifique se sua versão de especificação do TPM é pelo menos 1.2

    > [!NOTE]
    > Se você receber uma caixa de diálogo informando que um TPM (Módulo plataforma de confiança compatível) não pode ser encontrado, verifique se o computador tem um módulo TPM compatível e se ele está habilitado no BIOS do sistema.

7. Feche o console de gerenciamento do TPM

8. No prompt de comando, crie um novo cartão inteligente virtual usando o seguinte comando:

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > Para fornecer um valor de PIN personalizado ao criar o cartão inteligente virtual, use o prompt /pin.

9. No prompt de comando, abra o console de Gerenciamento do Computador executando o seguinte comando:

  ```console
  CompMgmt.msc
  ```

10. No console de Gerenciamento do Computador, selecione **Gerenciamento de Dispositivo.**

11. Expanda **leitores de cartão inteligente.**

12. Verifique se o novo leitor de cartão inteligente virtual foi criado com êxito.

## <a name="enroll-users-for-smart-card-authentication"></a>Registrar usuários para autenticação de cartão inteligente

Geralmente, há dois métodos para registrar usuários para autenticação de cartão inteligente. O método mais fácil envolve fazer com que os usuários se inscrevam diretamente para autenticação de cartão inteligente usando o registro na Web, enquanto o método mais complexo envolve o uso de um agente de registro. Este tópico se concentra no auto-registro para certificados de cartão inteligente.

Para obter mais informações sobre como se inscrever em nome dos usuários como um agente de registro, consulte Registrar-se para [certificados em nome de outros usuários.](https://go.microsoft.com/fwlink/p/?LinkID=313367)

### <a name="to-enroll-users-for-smart-card-authentication"></a>Para registrar usuários para autenticação de cartão inteligente

1. Entre na estação de trabalho do Windows 8 usando as credenciais de um usuário habilitado para Skype for Business.

2. Iniciar o Internet Explorer.

3. Navegue até a **página Registro da Web da** Autoridade de Certificação (por exemplo, https://MyCA.contoso.com/certsrv) .

    > [!NOTE]
    > Se você estiver usando o Internet Explorer 10, talvez seja necessário exibir este site no Modo de Compatibilidade.

4. Na página **de boas-vindas,** selecione **Solicitar um certificado.**

5. Em seguida, selecione **Solicitação Avançada.**

6. Selecione **Criar e envie uma solicitação para esta AC.**

7. Selecione **Usuário de Cartão Inteligente** na seção Modelo **de** Certificado e conclua a solicitação de certificado avançada com os seguintes valores:

  - **As opções principais** confirmam as seguintes configurações:

    - Selecione o **botão de opção Criar novo conjunto de** teclas

    - Para **CSP**, selecione **Microsoft Base Smart Card Crypto Provider**

    - Para **Uso de Chave,** **selecione Exchange** (essa é a única opção disponível).

    - Para **o tamanho da** chave, insira 2048

    - Confirme se **o nome automático do contêiner de chave** está selecionado

    - Deixe as outras caixas desmarcadas.

  - Em **Opções Adicionais,** confirme os seguintes valores:

    - Para **o Formato de Solicitação,** selecione **CMC**.

    - Para **Algoritmo de Hash,** **selecione sha1**.

    - Para **Nome Amigável,** insira Certificado Smardcard.

8. Se você estiver usando um leitor de cartão inteligente físico, insira o cartão inteligente no dispositivo.

9. Clique **em Enviar** para enviar a solicitação de certificado.

10. Quando solicitado, insira o PIN que foi usado para criar o cartão inteligente virtual.

    > [!NOTE]
    > O valor padrão do PIN do cartão inteligente virtual é '12345678'.

11. Depois que o certificado tiver sido emitido, clique em **Instalar este certificado** para concluir o processo de inscrição.

    > [!NOTE]
    >  Se sua solicitação de certificado falhar com o erro "Este navegador da Web não dá suporte à geração de solicitações de certificado", há três maneiras possíveis de resolver o problema:

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configurar os Serviços de Federação do Active Directory (AD FS 2.0)

A seção a seguir descreve como configurar os Serviços de Federação do Active Directory (AD FS 2.0) para dar suporte à autenticação multifacional. Para obter informações sobre como instalar o AD FS 2.0, consulte o [AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=313374)passo a passo e guias de como instalar.

> [!NOTE]
> Ao instalar o AD FS 2.0, não use o Gerenciador do Windows Server para adicionar a função serviços de federação do Active Directory. Em vez disso, baixe e instale o pacote RTW dos Serviços de Federação do [Active Directory 2.0.](https://go.microsoft.com/fwlink/p/?LinkId=313375)

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>Para configurar o AD FS para autenticação de dois fatores

1. Entre no computador do AD FS 2.0 usando uma conta de Administrador de Domínio.

2. Inicie o Windows PowerShell.

3. Na linha de comando do Windows PowerShell, execute o seguinte comando:

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Estabeleça uma parceria com cada servidor que será habilitado para autenticação passiva executando o seguinte comando, substituindo o nome do servidor específico para sua implantação:

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. No menu Ferramentas Administrativas, iniciar o console de Gerenciamento do AD FS 2.0.

6. Expanda **relações de confiança**  >  **confianças de terceiros confiados**.

7. Verifique se uma nova confiança foi criada para seu Skype for Business Server.

8. Crie e atribua uma Regra de Autorização de Emissão para sua confiança de terceiros confiável usando o Windows PowerShell executando os seguintes comandos:

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Crie e atribua uma Regra de Transformação de Emissão para seu grupo confiável usando o Windows PowerShell executando os seguintes comandos:

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. No console de Gerenciamento do AD FS 2.0, clique com o botão direito do mouse no seu trust de terceiros confiável e selecione Editar Regras **de Declaração.**

11. Selecione a **guia Regras de Autorização de Emissão** e verifique se a nova regra de autorização foi criada com êxito.

12. Selecione a **guia Regras de Transformação de Emissão** e verifique se a nova regra de transformação foi criada com êxito.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Configurando o AD FS 2.0 para dar suporte à autenticação de cliente

Há dois tipos de autenticação possíveis que podem ser configurados para permitir que o AD FS 2.0 suporte a autenticação usando cartões inteligentes:

- Autenticação baseada em formulários (FBA)

- Autenticação do cliente de segurança da camada de transporte

Usando a autenticação baseada em formulários, você pode desenvolver uma página da Web que permite aos usuários autenticar usando seu nome de usuário/senha ou usando seu cartão inteligente e PIN. Este tópico se concentra em como implementar a Autenticação do Cliente de Segurança de Camada de Transporte com o AD FS 2.0. Para obter mais informações sobre os tipos de autenticação do AD FS 2.0, consulte [AD FS 2.0: Como](https://go.microsoft.com/fwlink/p/?LinkId=313384)alterar o tipo de autenticação local.

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Para configurar o AD FS 2.0 para dar suporte à autenticação de cliente

1. Entre no computador do AD FS 2.0 usando uma conta de Administrador de Domínio.

2. Iniciar o Windows Explorer.

3. Navegue até C:\inetpub\adfs\ls

4. Faça uma cópia de backup do arquivo de web.config existente.

5. Abra o arquivo de web.config usando o Bloco de Notas.

6. Na barra de menus, selecione **Editar** e, em seguida, **encontre**.

7. Procure \<localAuthenticationTypes\> por .

    Observe que há quatro tipos de autenticação listados, um por linha.

8. Mova a linha que contém o tipo de autenticação TLSClient para o topo da lista na seção.

9. Salve e feche o arquivo web.config arquivo.

10. Iniciar um Prompt de Comando com privilégios elevados.

11. Reinicie o IIS executando o seguinte comando:

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configurando a autenticação passiva do Skype for Business Server

A seção a seguir descreve como configurar o Skype for Business Server para dar suporte à autenticação passiva. Uma vez habilitado, os usuários habilitados para autenticação de dois fatores precisarão usar um cartão inteligente físico ou virtual e um PIN válido para entrar usando o cliente Skype for Business.

> [!NOTE]
> É altamente recomendável que os clientes habilitam a autenticação passiva para Registrador e Serviços Web no nível de serviço. Se a autenticação passiva estiver habilitada para Registrador e Serviços Web no nível global, isso provavelmente resultará em falhas de autenticação em toda a organização para usuários que não estão se registrando com o cliente de área de trabalho suportado.

### <a name="web-service-configuration"></a>Configuração do serviço Web

As etapas a seguir descrevem como criar uma configuração de serviço Web personalizada para servidores Diretores, Pools Enterprise e Standard Edition que serão habilitados para autenticação passiva.

### <a name="to-create-a-custom-web-service-configuration"></a>Para criar uma configuração de serviço Web personalizada

1. Entre no servidor front-end do Skype for Business Server usando uma conta de administrador do Skype for Business.

2. Iniciar o Shell de Gerenciamento do Skype for Business Server.

3. Na linha de comando do Shell de Gerenciamento do Skype for Business Server, crie uma nova configuração de Serviço Web para cada servidor Diretor, Pool Enterprise e Standard Edition que será habilitado para autenticação passiva executando o seguinte comando:

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > O valor do FQDN WsFedPassiveMetadataUri é o Nome do Serviço de Federação do seu servidor do AD FS 2.0. O valor do Nome do Serviço de Federação pode ser encontrado no Console de  Gerenciamento do AD FS 2.0 clicando com o botão direito do mouse em Serviço no painel de navegação e selecionando Editar Propriedades do Serviço de **Federação.**

4. Verifique se os valores UseWsFedPassiveAuth e WsFedPassiveMetadataUri foram definidos corretamente executando o seguinte comando:

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Para clientes, a Autenticação Passiva é o método de autenticação menos preferido para autenticação de webticket. Para todos os servidores Diretores, Pools Enterprise e Standard Edition que serão habilitados para autenticação passiva, todos os outros tipos de autenticação devem ser desabilitados nos Serviços Web do Skype for Business executando o seguinte cmdlet:

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Verifique se todos os outros tipos de autenticação foram desabilitados com êxito executando o seguinte cmdlet:

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Configuração de Proxy

Quando a autenticação de certificado estiver desabilitada para os Serviços Web do Skype for Business, o cliente do Skype for Business usará um tipo de autenticação menos preferencial, como Kerberos ou NTLM, para autenticar no serviço registrador. A autenticação de certificado ainda é necessária para permitir que o cliente recupere um webticket, no entanto, Kerberos e NTLM devem ser desabilitados para o serviço registrador.

As etapas a seguir descrevem como criar uma configuração de proxy personalizada para Pools de Borda, Pools Enterprise e servidores Standard Edition que serão habilitados para autenticação passiva.

### <a name="to-create-a-custom-proxy-configuration"></a>Para criar uma configuração de proxy personalizada

1. Na linha de comando do Shell de Gerenciamento do Skype for Business Server, crie uma nova configuração de proxy para cada pool de borda do Skype for Business Server, pool Enterprise e servidor Standard Edition que será habilitado para autenticação passiva executando os seguintes comandos:

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Verifique se todos os outros tipos de autenticação de proxy foram desabilitados com êxito executando o seguinte comando:

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Confira também

[Gerenciar a autenticação de dois fatores no Skype for Business Server](two-factor-authentication.md)

[Usar a autenticação de dois fatores com o cliente Skype for Business e o Skype for Business Server](use-two-factor.md)
