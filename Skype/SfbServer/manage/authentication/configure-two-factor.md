---
title: Configurar a autenticação de dois fatores Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Resumo: Configure a autenticação de dois fatores Skype for Business Server.'
ms.openlocfilehash: c1749c6fcd97e10f7e09ddc243059cedc695fb65
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751790"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Configurar a autenticação de dois fatores Skype for Business Server

**Resumo:** Configure a autenticação de dois fatores Skype for Business Server.

As seções a seguir descrevem as etapas necessárias para configurar a autenticação de dois fatores para sua implantação. Para obter mais informações sobre a autenticação de dois fatores, consulte [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurar uma autoridade Enterprise certificado raiz para dar suporte à autenticação de cartão inteligente

As etapas a seguir descrevem como configurar uma AC raiz Enterprise para dar suporte à Autenticação de Cartão Inteligente:

Para obter informações sobre como instalar uma Enterprise Raiz, consulte [Install an Enterprise Root Certification Authority](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10)).

1. Faça logoff no computador Enterprise CA usando uma conta de Administrador de Domínio.

2. Iniciar o System Manager e verificar se a função de Registro da Web da Autoridade de Certificação está instalada.

3. No menu **Ferramentas Administrativas,** abra o console de gerenciamento **da Autoridade** de Certificação.

4. No painel De navegação, expanda **a Autoridade de Certificação**.

5. Clique com o botão direito do mouse em Modelos **de Certificados,** selecione **Novo** e, em seguida, selecione Modelo de Certificado **para Emitir**.

6. Selecione **Agente de Registro,** **Usuário Smartcard** e **Logon do Smartcard.**

7. Clique em **OK**.

8. Clique com o botão **direito do mouse em Modelos de Certificado.**

9. Selecione **Gerenciar**.

10. Abra as propriedades do modelo de usuário smartcard.

11. Clique na guia **Segurança.**

12. Altere as permissões da seguinte forma:

    - Adicionar contas de AD de usuário individuais com permissões de Leitura/Registro (Permitir) ou

    - Adicionar um grupo de segurança que contém usuários de cartão inteligente com permissões de Leitura/Registro (Permitir) ou

    - Adicionar o grupo Usuários de Domínio com permissões de Leitura/Registro (Permitir)

## <a name="configure-windows-8-for-virtual-smart-cards"></a>Configurar Windows 8 para Cartões Inteligentes Virtuais

Um fator a ser considerado ao implantar a autenticação de dois fatores e a tecnologia de cartão inteligente é o custo da implementação. Windows 8 fornece uma série de novos recursos de segurança, e um dos novos recursos mais interessantes é o suporte a cartões inteligentes virtuais.

Para computadores equipados com um chip TPM (Trusted Platform Module) que atenda à especificação versão 1.2, as organizações agora podem obter os benefícios do logon de cartão inteligente sem fazer investimentos adicionais em hardware. Para obter mais informações, consulte [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Para configurar Windows 8 para cartões inteligentes virtuais

1. Entre no computador Windows 8 usando as credenciais de um usuário Skype for Business habilitado.

2. Na tela Windows 8 Inicial, mova o cursor para o canto inferior direito da tela.

3. Selecione a **opção Pesquisar** e, em seguida, pesquise prompt de comando.

4. Clique com o **botão direito do** mouse no Prompt de Comando e selecione Executar como **Administrador**.

5. Abra o console de Gerenciamento do Módulo de Plataforma Confiável (TPM) executando o seguinte comando:

   ```console
   Tpm.msc
   ```

6. No console de gerenciamento do TPM, verifique se sua versão de especificação do TPM é pelo menos 1,2

    > [!NOTE]
    > Se você receber uma caixa de diálogo informando que não é possível encontrar um TPM (Compatible Trust Platform Module), verifique se o computador tem um módulo TPM compatível e se ele está habilitado no BIOS do sistema.

7. Fechar o console de gerenciamento do TPM

8. No prompt de comando, crie um novo cartão inteligente virtual usando o seguinte comando:

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

   > [!NOTE]
   > Para fornecer um valor pin personalizado ao criar o cartão inteligente virtual, use o prompt /pin em vez disso.

9. No prompt de comando, abra o console de Gerenciamento de Computador executando o seguinte comando:

  ```console
  CompMgmt.msc
  ```

10. No console de Gerenciamento de Computador, selecione **Gerenciamento de Dispositivos**.

11. Expanda **leitores de cartão inteligente**.

12. Verifique se o novo leitor de cartão inteligente virtual foi criado com êxito.

## <a name="enroll-users-for-smart-card-authentication"></a>Registrar usuários para autenticação de cartão inteligente

Geralmente, há dois métodos para registrar usuários para autenticação de cartão inteligente. O método mais fácil envolve fazer com que os usuários se inscrevam diretamente para autenticação de cartão inteligente usando o registro da Web, enquanto o método mais complexo envolve o uso de um agente de registro. Este tópico se concentra no auto-registro para certificados de cartão inteligente.

Para obter mais informações sobre o registro em nome dos usuários como agente de registro, consulte [Enroll for Certificates on Behalf of Other Users](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11)).

### <a name="to-enroll-users-for-smart-card-authentication"></a>Para registrar usuários para autenticação de cartão inteligente

1. Faça logoff na Windows 8 de trabalho usando as credenciais de um usuário Skype for Business habilitado.

2. Iniciar o Internet Explorer.

3. Navegue até a página **Registro da Web da** Autoridade de Certificação (por exemplo, https://MyCA.contoso.com/certsrv) .

    > [!NOTE]
    > Se você estiver usando Internet Explorer 10, talvez seja necessário exibir este site no Modo de Compatibilidade.

4. Na Página **de Boas-vindas,** selecione **Solicitar um certificado**.

5. Em seguida, selecione **Solicitação Avançada**.

6. Selecione **Criar e enviar uma solicitação para esta CA**.

7. Selecione **Usuário de Cartão Inteligente** na seção Modelo **de** Certificado e conclua a solicitação de certificado avançada com os seguintes valores:

  - **Opções de chave** confirmam as seguintes configurações:

    - Selecione o **botão de opção Criar novo conjunto de** chaves

    - Para **CSP,** selecione **Provedor de Criptografia de Cartão Inteligente da Microsoft Base**

    - Para **Uso de Chave,** **selecione Exchange** (esta é a única opção disponível).

    - Para **Tamanho da Chave**, insira 2048

    - Confirme se **o nome do contêiner de chave automática** está selecionado

    - Deixe as outras caixas desmarcadas.

  - Em **Opções Adicionais,** confirme os seguintes valores:

    - Para **Formato de Solicitação,** **selecione CMC**.

    - Para **Algoritmo de Hash,** **selecione sha1**.

    - Para **Nome Amigável,** enterSmardcard Certificate.

8. Se você estiver usando um leitor de cartão inteligente físico, insira o cartão inteligente no dispositivo.

9. Clique **em Enviar** para enviar a solicitação de certificado.

10. Quando solicitado, insira o PIN usado para criar o cartão inteligente virtual.

    > [!NOTE]
    > O valor padrão de PIN de cartão inteligente virtual é "12345678".

11. Depois que o certificado for emitido, clique em **Instalar esse certificado para** concluir o processo de registro.

    > [!NOTE]
    >  Se sua solicitação de certificado falhar com o erro "Este navegador da Web não dá suporte à geração de solicitações de certificado", há três maneiras possíveis de resolver o problema:
    >- Habilitar o Modo de Exibição de Compatibilidade no Internet Explorer.
    >- Habilita a opção Ativar configurações de Intranet no Internet Explorer.
    >- Selecione a configuração Redefinir todas as zonas para o nível padrão na guia Segurança no menu opções do Internet Explorer.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configurar os Serviços de Federação do Active Directory (AD FS 2.0)

A seção a seguir descreve como configurar os Serviços de Federação do Active Directory (AD FS 2.0) para dar suporte à autenticação multifacional. Para obter informações sobre como instalar o AD FS 2.0, consulte [AD FS 2.0 Passo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))a passo e Como Guias .

> [!NOTE]
> Ao instalar o AD FS 2.0, não use o Gerenciador de Servidores Windows para adicionar a função serviços de federação do Active Directory. Em vez disso, baixe e instale os [Serviços de Federação do Active Directory.](/troubleshoot/windows-server/identity/availability-description-afds)

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>Para configurar o AD FS para autenticação de dois fatores

1. Faça logoff no computador do AD FS 2.0 usando uma conta de Administrador de Domínio.

2. Inicie o Windows PowerShell.

3. Na linha Windows PowerShell de comando, execute o seguinte comando:

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Estabeleça uma parceria com cada servidor que será habilitado para autenticação passiva executando o seguinte comando, substituindo o nome do servidor específico da sua implantação:

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. No menu Ferramentas Administrativas, iniciar o console de Gerenciamento do AD FS 2.0.

6. Expanda **relações de confiança**  >  **Confiando confianças de terceiros.**

7. Verifique se uma nova confiança foi criada para sua Skype for Business Server.

8. Crie e atribua uma Regra de Autorização de Emissão para sua confiança de parte confiável usando Windows PowerShell executando os seguintes comandos:

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Crie e atribua uma Regra de Transformação de Emissão para sua confiança de parte confiável usando Windows PowerShell executando os seguintes comandos:

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. No console de Gerenciamento do AD FS 2.0, clique com o botão direito do mouse em sua confiança de parte confiável e selecione **Editar Regras de Declaração.**

11. Selecione a **guia Regras de Autorização** de Emissão e verifique se a nova regra de autorização foi criada com êxito.

12. Selecione a **guia Regras de Transformação de Emissão** e verifique se a nova regra de transformação foi criada com êxito.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Configurando o AD FS 2.0 para dar suporte à autenticação do cliente

Há dois tipos de autenticação possíveis que podem ser configurados para permitir que o AD FS 2.0 suporte a autenticação usando cartões inteligentes:

- Autenticação baseada em formulários (FBA)

- Autenticação do cliente de segurança de camada de transporte

Usando a autenticação baseada em formulários, você pode desenvolver uma página da Web que permite aos usuários autenticar usando seu nome de usuário/senha ou usando seu cartão inteligente e PIN. Este tópico se concentra em como implementar a Autenticação do Cliente de Segurança de Camada de Transporte com o AD FS 2.0. Para obter mais informações sobre tipos de autenticação do AD FS 2.0, consulte [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Para configurar o AD FS 2.0 para dar suporte à autenticação do cliente

1. Faça logoff no computador do AD FS 2.0 usando uma conta de Administrador de Domínio.

2. Iniciar Windows Explorer.

3. Navegue até C:\inetpub\adfs\ls

4. Faça uma cópia de backup do arquivo web.config existente.

5. Abra o arquivo de web.config existente usando Bloco de notas.

6. Na barra menu, selecione **Editar** e selecione **Encontrar**.

7. Pesquise \<localAuthenticationTypes\> por .

    Observe que há quatro tipos de autenticação listados, um por linha.

8. Mova a linha que contém o tipo de autenticação TLSClient para a parte superior da lista na seção.

9. Salve e feche o arquivo web.config arquivo.

10. Iniciar um Prompt de Comando com privilégios elevados.

11. Reinicie o IIS executando o seguinte comando:

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configurando Skype for Business Server autenticação passiva

A seção a seguir descreve como configurar o Skype for Business Server para dar suporte à autenticação passiva. Depois de habilitado, os usuários habilitados para autenticação de dois fatores serão obrigados a usar um cartão inteligente físico ou virtual e um PIN válido para entrar usando o cliente Skype for Business.

> [!NOTE]
> É altamente recomendável que os clientes habilitam a autenticação passiva para Registrador e Serviços Web no nível de serviço. Se a autenticação passiva estiver habilitada para o Registrador e os Serviços Web no nível global, provavelmente resultará em falhas de autenticação em toda a organização para usuários que não estão fazendo o contato com o cliente da área de trabalho com suporte.

### <a name="web-service-configuration"></a>Configuração do Serviço Web

As etapas a seguir descrevem como criar uma configuração de serviço Web personalizada para Diretores, Enterprise Pools e Edição Standard servidores que serão habilitados para autenticação passiva.

### <a name="to-create-a-custom-web-service-configuration"></a>Para criar uma configuração de serviço Web personalizada

1. Faça logoff no servidor Skype for Business Server front-end usando uma conta Skype for Business administrador.

2. Iniciar o Shell Skype for Business Server Gerenciamento.

3. Na linha de comando Skype for Business Server Shell de Gerenciamento, crie uma nova configuração do Serviço Web para cada diretor, pool Enterprise e servidor Edição Standard que serão habilitados para autenticação passiva executando o seguinte comando:

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

   > [!CAUTION]
   > O valor do FQDN WsFedPassiveMetadataUri é o Nome do Serviço de Federação do servidor do AD FS 2.0. O valor Nome do Serviço de Federação pode ser encontrado no Console de Gerenciamento do AD FS 2.0 clicando com o botão direito do mouse em **Serviço** no painel de navegação e selecionando Editar Propriedades do Serviço de **Federação.**

4. Verifique se os valores UseWsFedPassiveAuth e WsFedPassiveMetadataUri foram definidos corretamente executando o seguinte comando:

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Para clientes, Autenticação Passiva é o método de autenticação menos preferencial para autenticação de webticket. Para todos os Diretores, Enterprise Pools e servidores Edição Standard que serão habilitados para autenticação passiva, todos os outros tipos de autenticação devem ser desabilitados no Skype for Business Web Services executando o seguinte cmdlet:

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Verifique se todos os outros tipos de autenticação foram desabilitados com êxito executando o seguinte cmdlet:

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Configuração de Proxy

Quando a autenticação de certificado estiver desabilitada para Skype for Business Web Services, o cliente Skype for Business usará um tipo de autenticação menos preferencial, como Kerberos ou NTLM, para autenticar no serviço Registrador. A autenticação de certificado ainda é necessária para permitir que o cliente recupere uma webticket, no entanto, Kerberos e NTLM devem ser desabilitados para o serviço Registrador.

As etapas a seguir descrevem como criar uma configuração de proxy personalizada para Pools de Borda, Enterprise Pools e Edição Standard servidores Edição Standard que serão habilitados para autenticação passiva.

### <a name="to-create-a-custom-proxy-configuration"></a>Para criar uma configuração de proxy personalizada

1. Na linha de comando do Shell de Gerenciamento do Skype for Business Server, crie uma nova configuração de proxy para cada pool de borda do Skype for Business Server, pool Enterprise e servidor Edição Standard que serão habilitados para autenticação passiva executando os seguintes comandos :

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

[Gerenciar a autenticação de dois fatores Skype for Business Server](two-factor-authentication.md)

[Use a autenticação de dois fatores com Skype for Business cliente e Skype for Business Server](use-two-factor.md)
