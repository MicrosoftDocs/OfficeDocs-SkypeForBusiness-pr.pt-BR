---
title: Configurar a autenticação de dois fatores no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Summary: Configure two-factor authentication in Skype for Business Server 2015.'
ms.openlocfilehash: edd32559a136573e7b3cf1fe5dc3a153ce0eb61c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server-2015"></a>Configurar a autenticação de dois fatores no Skype for Business Server 2015
 
**Summary:** Configure two-factor authentication in Skype for Business Server 2015.
  
As seções a seguir descrevem as etapas necessárias para configurar a autenticação de duas etapas para sua implementação. For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).
  
## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configuração de uma Autoridade de Certificação Raiz Corporativa para dar suporte à Autenticação de Cartão Inteligente

As seguintes etapas descrevem como configurar uma CA Raiz Corporativa para dar suporte à Autenticação de Cartão Inteligente:
  
For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).
  
1. Faça o login no computador da AC corporativa utilizando uma conta de Administrador de Domínio.
    
2. Inicie o Gerenciador de Sistema e verifique se a função de Registro da Web da Autoridade de Certificação está instalada.
    
3. No menu **Ferramentas Administrativas**, abra o console de gerenciamento da **Autoridade de Certificação**.
    
4. No painel de Navegação, expanda **Autoridade de Certificação**.
    
5. Clique com o botão direito do mouse em **Modelos de Certificado**, selecione **Novo** e, em seguida, selecione **Modelo de Certificação para Emissão**.
    
6. Selecione **Agente de Registro**, **Usuário do Cartão Inteligente** e **Logon do Cartão Inteligente**.
    
7. Clique em **OK**.
    
8. Clique com o botão direito em **Modelos de Certificado**.
    
9. Selecione **Gerenciar**.
    
10. Abra as propriedades do modelo do Usuário do Cartão Inteligente.
    
11. Clique na guia **Segurança**.
    
12. Altere as permissões da seguinte forma:
    
    - Adicione contas de AD de usuários individuais com permissões para Ler/Registrar (Permitir) ou
    
    - Adicione um grupo de segurança contendo usuários do cartão inteligente com permissões para Ler/Registrar (Permitir), ou
    
    - Adicione o grupo do Usuário de Domínio com as permissões para Ler/Registrar (Permitir)
    
## <a name="configure-windows-8-for-virtual-smart-cards"></a>Configuração do Windows 8 para cartões inteligentes virtuais

Um fator que deve ser levado em consideração na implantação da autenticação de dois fatores e na tecnologia de cartão inteligente é o custo da implementação. Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.
  
Para computadores que contam com um chip Trusted Platform Module (TPM) compatível com a especificação da versão 1.2, as organizações podem agora se beneficiar do logon com cartões inteligentes sem fazer mais nenhum investimento em hardware. For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).
  
### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Para configurar o Windows 8 para cartões inteligentes virtuais

1. Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.
    
2. Na tela Iniciar do Windows 8, mova seu cursor para o canto inferior direito da tela.
    
3. Select the **Search** option, and then search forCommand Prompt.
    
4. Clique com o botão direito do mouse em **Prompt de comando** e selecione **Executar como administrador**.
    
5. Abra o Console de Gerenciamento do Trusted Platform Module (TPM) executando o seguinte comando:
    
  ```
  Tpm.msc
  ```

6. No Console de Gerenciamento do TPM, confira se a versão do seu TPM é 1.2 ou superior.
    
    > [!NOTE]
    > Caso surja uma caixa de diálogo com a mensagem de que não foi possível encontrar o Trust Platform Module (TPM) compatível, verifique se o computador tem um módulo TPM compatível e se ele está habilitado na BIOS do sistema. 
  
7. Feche o Console de Gerenciamento do TPM
    
8. No prompt de comando, crie um novo cartão inteligente virtual usando o seguinte comando:
    
  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > Para personalizar o valor do PIN ao criar o cartão inteligente virtual, use o prompt /pin. 
  
9. No prompt de comando, abre o Console de Gerenciamento do computador executando o seguinte comando:
    
  ```
  CompMgmt.msc
  ```

10. No Console de Gerenciamento do computador, selecione **Gerenciamento de Dispositivos**.
    
11. Expanda **Leitores de cartão inteligente**.
    
12. Verifique se o novo leitor de cartão inteligente virtual foi criado com êxito.
    
## <a name="enroll-users-for-smart-card-authentication"></a>Registrar usuários para a autenticação de cartão inteligente

Em geral, há dois métodos para registrar usuários para autenticação de cartão inteligente. O método mais fácil envolve ter usuários registrados diretamente para autenticação de cartão inteligente usando o registro via Web, enquanto o método mais complexo envolve o uso de um agente de registro. Este tópico se concentra no autorregistro para certificados de cartões inteligentes.
  
For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).
  
### <a name="to-enroll-users-for-smart-card-authentication"></a>Para registrar usuários para autenticação de cartão inteligente

1. Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.
    
2. Inicie o Internet Explorer.
    
3. Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).
    
    > [!NOTE]
    > Caso esteja usando o Internet Explorer 10, pode ser necessário visualizar esta página em Modo de Compatibilidade. 
  
4. Na **Página Inicial**, selecione **Solicitar um certificado**.
    
5. Em seguida, selecione **Solicitação Avançada**.
    
6. Selecione **Criar e enviar uma solicitação para esta autoridade de certificação**.
    
7. Selecione **Usuário do Cartão Inteligente** na seção **Modelo de Certificado** e preencha a solicitação de certificado avançado com os seguintes valores:
    
  - As **Opções de Chave** confirmam as seguintes configurações:
    
    - Selecione o botão de opção **Criar novo conjunto de chaves**
    
    - Em **CSP**, selecione **Microsoft Base Smart Card Crypto Provider**
    
    - Em **Uso da Chave**, selecione **Exchange** (é a única opção disponível).
    
    - For **Key Size**, enter 2048
    
    - Confirme se a opção **Nome de contêiner de chave automático** está selecionada
    
    - Deixe as outras caixas desmarcadas.
    
  - Em **Opções Adicionais**, confirme os seguintes valores:
    
    - Em **Formato da Solicitação**, selecione **CMC**.
    
    - Em **Algoritmo de Hash**, selecione **sha1**.
    
    - For **Friendly Name** enterSmardcard Certificate.
    
8. Caso você esteja usando um leitor de cartão inteligente físico, insira o cartão inteligente no dispositivo.
    
9. Clique em **Enviar** para enviar a solicitação do certificado.
    
10. Quando solicitado, digite o PIN usado para criar o cartão inteligente virtual.
    
    > [!NOTE]
    > The default virtual smart card PIN value is '12345678'. 
  
11. Depois que o certificado tiver sido emitido, clique em **Instalar este certificado** para concluir o processo de registro.
    
    > [!NOTE]
    >  If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:
  
        a. Enable Compatibility View in Internet Explorer 
        b. Enable the Turn on Intranet settings option in Internet Explorer 
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.
  
## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configuração dos Serviços de Federação do Active Directory (AD FS 2.0)

A seção a seguir descreve como configurar o Serviços de Federação do Active Directory (AD FS 2.0) para dar suporte à autenticação multifator. For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).
  
> [!NOTE]
> Ao instalar o AD FS 2.0, não use o Windows Server Manager para adicionar a função do Active Directory Federation. Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375). 
  
### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>Para configurar o AD FS para autenticação de dois fatores

1. Faça logon no computador do AD FS 2.0 utilizando uma conta de Administrador de Domínio.
    
2. Inicie o Windows PowerShell.
    
3. Na linha de comando do Windows PowerShell, execute o seguinte comando:
    
  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Estabeleça uma parceria com cada servidor que será habilitado para a autenticação passiva executando o seguinte comando, substituindo pelo nome do servidor específico de sua implantação:
    
  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. No menu Ferramentas Administrativas, inicie o Console de Gerenciamento do AD FS 2.0.
    
6. Expand **Trust Relationships** > **Relying Party Trusts**.
    
7. Verify that a new trust has been created for your Skype for Business Server.
    
8. Crie e atribua uma Regra de Autorização de Emissão para seu objeto de confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:
    
  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth 
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Crie e atribua uma Regra de Transformação de Emissão para seu objeto de confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:
    
  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. No Console de Gerenciamento do AD FS 2.0, clique com o botão direito no seu objeto de confiança de terceira parte confiável e selecione **Editar Regras de Declaração**.
    
11. Selecione a guia **Regras de Autorização de Emissão** e verifique se a nova regra de autorização foi criada com sucesso.
    
12. Selecione a guia **Regras de Transformação de Emissão** e verifique se a nova regra de transformação foi criada com sucesso.
    
## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Configuração do AD FS 2.0 para suporte à autenticação de cliente

Há dois tipos possíveis de autenticação que podem ser configurados para permitir que o AD FS 2.0 suporte autenticações utilizando cartões inteligentes:
  
- Autenticação baseada em formulário (FBA)
    
- Autenticação de Cliente de Segurança na Camada de Transporte
    
Utilizando a autenticação baseada em formulários, você pode desenvolver uma página da Web que permite que os usuários autentiquem usando seus nomes de usuário/senhas ou usando o cartão inteligente e o PIN. Este tópico tem como foco como implementar a Autenticação de Cliente de Segurança na Camada de Transporte com o AD FS 2.0. For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).
  
### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Para configurar o AD FS 2.0 para suportar a autenticação de cliente

1. Faça logon no computador do AD FS 2.0 utilizando uma conta de Administrador de Domínio.
    
2. Inicie o Windows Explorer.
    
3. Navegue até C:\inetpub\adfs\ls
    
4. Faça uma cópia de backup do arquivo web.config existente.
    
5. Abra o arquivo web.config existente utilizando o Bloco de Notas.
    
6. Na barra de Menu, selecione **Editar** e, em seguida, selecione **Localizar**.
    
7. Search for \<localAuthenticationTypes\>.
    
    Observe que há quatro tipos de autenticação listados, um por linha.
    
8. Mova para a linha que contém o tipo de autenticação TLSClient para o topo da lista na seção.
    
9. Salve e Feche o arquivo web.config.
    
10. Inicie um Prompt de Comando com privilégios elevados.
    
11. Reinicie o IIS executando o seguinte comando:
    
  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configuração da autenticação passiva do Skype for Business Server

The following section describes how to configure Skype for Business Server 2015 to support passive authentication. Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.
  
> [!NOTE]
> Recomendamos que os clientes habilitem a autenticação passiva para o Registrador e para os Serviços Web no nível de serviço. Caso a autenticação passiva esteja habilitada para o Registrador e para os Serviços Web no nível global, é provável que ocorram falhas de autenticação em toda a organização para usuários que não estão se conectando com o cliente de desktop compatível. 
  
### <a name="web-service-configuration"></a>Configuração dos Serviços Web

As etapas a seguir descrevem como criar uma configuração personalizada de serviços Web para servidores Diretores, pools Enterprise e Standard Edition que serão habilitados para a autenticação passiva.
  
### <a name="to-create-a-custom-web-service-configuration"></a>Para criar uma configuração personalizada de serviços Web

1. Log in to your Skype for Business Server 2015 Front End server using a Skype for Business administrator account.
    
2. Launch the Skype for Business Server Management Shell.
    
3. From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:
    
  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > O valor para o FQDN WsFedPassiveMetadataUri é o Nome de Serviço de Federação do seu servidor AD FS 2.0. O valor do Nome de Serviço de Federação pode ser encontrado no Console de Gerenciamento do AD FS 2.0 clicando com o botão direito do mouse em **Serviço** a partir do painel de navegação, selecionando em seguida **Editar propriedades do serviço de federação**. 
  
4. Verifique se os valores UseWsFedPassiveAuth e WsFedPassiveMetadataUri foram definidos corretamente executando o seguinte comando:
    
  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Para clientes, a Autenticação Passiva é o método de autenticação menos indicado para autenticação de webticket. For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:
    
  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Verifique se todos os outros tipos de autenticação foram desabilitados com sucesso executando o seguinte cmdlet:
    
  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Configuração de proxy

When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service. Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.
  
As etapas a seguir descrevem como criar uma configuração personalizada de proxy para servidores de pools Edge, pools Enterprise e Standard Edition que serão habilitados para a autenticação passiva.
  
### <a name="to-create-a-custom-proxy-configuration"></a>Para criar uma configuração personalizada de proxy

1. From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server 2015 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:
    
  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
-UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" 
-UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Verifique se todos os outros tipos de autenticação de proxy foram desabilitados com sucesso executando o seguinte comando:
    
  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com"
 | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Consulte também

#### 

[Manage two-factor authentication in Skype for Business Server 2015](two-factor-authentication.md)
  
[Use two-factor authentication with Skype for Business client and Skype for Business Server 2015](use.md)

