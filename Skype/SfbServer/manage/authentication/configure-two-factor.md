---
title: Configurar a autenticação de dois fatores no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Resumo: configurar a autenticação de dois fatores no Skype for Business Server.'
ms.openlocfilehash: 91a8929b89a584b116f1c7ec9313daa2fe679fd0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283837"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Configurar a autenticação de dois fatores no Skype for Business Server

**Resumo:** Configurar a autenticação de dois fatores no Skype for Business Server.

As seções a seguir descrevem as etapas necessárias para configurar a autenticação de duas etapas para sua implementação. Para obter mais informações sobre a autenticação de dois fatores, consulte [habilitando a autenticação multifator do Office 365 para administradores online-publicação do usuário em grade](https://go.microsoft.com/fwlink/p/?LinkId=313332).

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configuração de uma Autoridade de Certificação Raiz Corporativa para dar suporte à Autenticação de Cartão Inteligente

As seguintes etapas descrevem como configurar uma CA Raiz Corporativa para dar suporte à Autenticação de Cartão Inteligente:

Para obter informações sobre como instalar uma autoridade de certificação raiz corporativa, consulte [instalar uma autoridade de certificação raiz corporativa](https://go.microsoft.com/fwlink/p/?LinkID=313364).

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

Um fator que deve ser levado em consideração na implantação da autenticação de dois fatores e na tecnologia de cartão inteligente é o custo da implementação. O Windows 8 fornece vários recursos de segurança novos, e um dos novos recursos mais interessantes é o suporte para cartões inteligentes virtuais.

Para computadores que contam com um chip Trusted Platform Module (TPM) compatível com a especificação da versão 1.2, as organizações podem agora se beneficiar do logon com cartões inteligentes sem fazer mais nenhum investimento em hardware. Para obter mais informações, consulte [usando cartões inteligentes virtuais com o Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Para configurar o Windows 8 para cartões inteligentes virtuais

1. Faça logon no computador com o Windows 8 usando as credenciais de um usuário habilitado para o Skype for Business.

2. Na tela Iniciar do Windows 8, mova seu cursor para o canto inferior direito da tela.

3. Selecione a opção de **pesquisa** e, em seguida, pesquise forCommand prompt.

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

Para obter mais informações sobre como registrar-se em nome dos usuários como um agente de inscrição, consulte registrar-se [para obter certificados em nome de outros usuários](https://go.microsoft.com/fwlink/p/?LinkID=313367).

### <a name="to-enroll-users-for-smart-card-authentication"></a>Para registrar usuários para autenticação de cartão inteligente

1. Faça logon na estação de trabalho do Windows 8 usando as credenciais de um usuário habilitado para o Skype for Business.

2. Inicie o Internet Explorer.

3. Navegue até a página de **registro na Web da autoridade** de https://MyCA.contoso.com/certsrv)certificação (por exemplo,.

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

    - Em **Tamanho da Chave**, digite 2048

    - Confirme se a opção **Nome de contêiner de chave automático** está selecionada

    - Deixe as outras caixas desmarcadas.

  - Em **Opções Adicionais**, confirme os seguintes valores:

    - Em **Formato da Solicitação**, selecione **CMC**.

    - Em **Algoritmo de Hash**, selecione **sha1**.

    - Para um certificado enterSmardcard de **nome amigável** .

8. Caso você esteja usando um leitor de cartão inteligente físico, insira o cartão inteligente no dispositivo.

9. Clique em **Enviar** para enviar a solicitação do certificado.

10. Quando solicitado, digite o PIN usado para criar o cartão inteligente virtual.

    > [!NOTE]
    > O valor padrão do PIN do cartão inteligente virtual é ' 12345678 '.

11. Depois que o certificado tiver sido emitido, clique em **Instalar este certificado** para concluir o processo de registro.

    > [!NOTE]
    >  Se a solicitação de certificado falhar com o erro "Este navegador da Web não é compatível com a geração de solicitações de certificado", há três maneiras possíveis de solucionar o problema:

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configuração dos Serviços de Federação do Active Directory (AD FS 2.0)

A seção a seguir descreve como configurar o Serviços de Federação do Active Directory (AD FS 2.0) para dar suporte à autenticação multifator. Para obter informações sobre como instalar o AD FS 2,0, consulte guias passo a [passo do AD fs 2,0 passo a passo e instruções](https://go.microsoft.com/fwlink/p/?LinkId=313374).

> [!NOTE]
> Ao instalar o AD FS 2.0, não use o Windows Server Manager para adicionar a função do Active Directory Federation. Em vez disso, baixe e instale o [pacote RTW do serviços de Federação do Active Directory 2,0](https://go.microsoft.com/fwlink/p/?LinkId=313375).

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

6. Expanda **relações** > de confiança**confiança de terceira parte confiável**.

7. Verifique se uma nova relação de confiança foi criada para o seu Skype for Business Server.

8. Crie e atribua uma Regra de Autorização de Emissão para seu objeto de confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Crie e atribua uma Regra de Transformação de Emissão para seu objeto de confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
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

Utilizando a autenticação baseada em formulários, você pode desenvolver uma página da Web que permite que os usuários autentiquem usando seus nomes de usuário/senhas ou usando o cartão inteligente e o PIN. Este tópico tem como foco como implementar a Autenticação de Cliente de Segurança na Camada de Transporte com o AD FS 2.0. Para obter mais informações sobre os tipos de autenticação do AD FS 2,0, consulte [ad fs 2,0: como alterar o tipo de autenticação local](https://go.microsoft.com/fwlink/p/?LinkId=313384).

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Para configurar o AD FS 2.0 para suportar a autenticação de cliente

1. Faça logon no computador do AD FS 2.0 utilizando uma conta de Administrador de Domínio.

2. Inicie o Windows Explorer.

3. Navegue até C:\inetpub\adfs\ls

4. Faça uma cópia de backup do arquivo web.config existente.

5. Abra o arquivo web.config existente utilizando o Bloco de Notas.

6. Na barra de Menu, selecione **Editar** e, em seguida, selecione **Localizar**.

7. Procure por \<localAuthenticationTypes\>.

    Observe que há quatro tipos de autenticação listados, um por linha.

8. Mova para a linha que contém o tipo de autenticação TLSClient para o topo da lista na seção.

9. Salve e Feche o arquivo web.config.

10. Inicie um Prompt de Comando com privilégios elevados.

11. Reinicie o IIS executando o seguinte comando:

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configuração da autenticação passiva do Skype for Business Server

A seção a seguir descreve como configurar o Skype for Business Server para dar suporte à autenticação passiva. Uma vez habilitado, os usuários habilitados para a autenticação de dois fatores serão necessários para usar um cartão inteligente físico ou virtual e um PIN válido para entrar usando o cliente Skype for Business.

> [!NOTE]
> Recomendamos que os clientes habilitem a autenticação passiva para o Registrador e para os Serviços Web no nível de serviço. Caso a autenticação passiva esteja habilitada para o Registrador e para os Serviços Web no nível global, é provável que ocorram falhas de autenticação em toda a organização para usuários que não estão se conectando com o cliente de desktop compatível.

### <a name="web-service-configuration"></a>Configuração dos Serviços Web

As etapas a seguir descrevem como criar uma configuração personalizada de serviços Web para servidores Diretores, pools Enterprise e Standard Edition que serão habilitados para a autenticação passiva.

### <a name="to-create-a-custom-web-service-configuration"></a>Para criar uma configuração personalizada de serviços Web

1. Conecte-se ao seu servidor front-end do Skype for Business Server usando uma conta de administrador do Skype for Business.

2. Inicie o Shell de gerenciamento do Skype for Business Server.

3. Na linha de comando do Shell de gerenciamento do Skype for Business Server, crie uma nova configuração de serviço Web para cada director, pool corporativo e servidor Standard Edition que será habilitado para autenticação passiva executando o seguinte comando:

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > O valor para o FQDN WsFedPassiveMetadataUri é o Nome de Serviço de Federação do seu servidor AD FS 2.0. O valor do Nome de Serviço de Federação pode ser encontrado no Console de Gerenciamento do AD FS 2.0 clicando com o botão direito do mouse em **Serviço** a partir do painel de navegação, selecionando em seguida **Editar propriedades do serviço de federação**.

4. Verifique se os valores UseWsFedPassiveAuth e WsFedPassiveMetadataUri foram definidos corretamente executando o seguinte comando:

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Para clientes, a Autenticação Passiva é o método de autenticação menos indicado para autenticação de webticket. Para todos os directors, pools corporativos e servidores Standard Edition que serão habilitados para autenticação passiva, todos os outros tipos de autenticação deverão ser desabilitados nos serviços Web do Skype for Business executando o seguinte cmdlet:

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Verifique se todos os outros tipos de autenticação foram desabilitados com sucesso executando o seguinte cmdlet:

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Configuração de proxy

Quando a autenticação de certificado estiver desabilitada para os serviços Web do Skype for Business, o cliente Skype for Business usará um tipo de autenticação menos preferencial, como Kerberos ou NTLM, para autenticar para o serviço registrador. A autenticação de certificado ainda é necessária para permitir que o cliente recupere um webticket, no entanto, Kerberos e NTLM devem ser desabilitados para o serviço registrador.

As etapas a seguir descrevem como criar uma configuração personalizada de proxy para servidores de pools Edge, pools Enterprise e Standard Edition que serão habilitados para a autenticação passiva.

### <a name="to-create-a-custom-proxy-configuration"></a>Para criar uma configuração personalizada de proxy

1. Na linha de comando do Shell de gerenciamento do Skype for Business Server, crie uma nova configuração de proxy para cada pool de borda do Skype for Business Server, pool corporativo e servidor Standard Edition que será habilitado para autenticação passiva executando o seguinte comandos

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Verifique se todos os outros tipos de autenticação de proxy foram desabilitados com sucesso executando o seguinte comando:

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Confira também

[Gerenciar a autenticação de dois fatores no Skype for Business Server](two-factor-authentication.md)

[Usar a autenticação de dois fatores com o cliente Skype for Business e o Skype for Business Server](use-two-factor.md)
