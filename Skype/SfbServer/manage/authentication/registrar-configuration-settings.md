---
title: Gerenciar definições de configuração do Registrador no Skype for Business Server
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
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Resumo: Gerencie as definições de configuração do Registrador para o Skype for Business Server.'
ms.openlocfilehash: 9a56e803470054ab8c2ba3cf9e2c758d4e71e17a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828321"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>Gerenciar definições de configuração do Registrador no Skype for Business Server
 
**Resumo:** Gerenciar definições de configuração do Registrador para o Skype for Business Server.
  
É possível usar o Registrador para configurar métodos de autenticação do servidor proxy. O protocolo de autenticação que você especificar determina que tipo de desafios os servidores no pool vão gerar para os clientes. Os protocolos disponíveis são:
  
- **Kerberos** Esse é o esquema de autenticação baseado em senha mais forte disponível para clientes, mas normalmente está disponível somente para clientes corporativos porque exige conexão de cliente com um Centro de Distribuição de Chaves (controlador de domínio Kerberos). Essa configuração é apropriada se o servidor autenticar somente clientes empresariais.
    
- **NTLM** Essa é a autenticação baseada em senha disponível para clientes que usam um esquema de hash de desafio-resposta na senha. Essa é a única forma de autenticação disponível para clientes sem conectividade com um Centro de distribuição de chaves (controlador de domínio Kerberos), como usuários remotos. Se um servidor autenticar somente usuários remotos, escolha NTLM.
    
- **Autenticação de certificado** Esse é o novo método de autenticação quando o servidor precisa obter certificados de clientes do Lync Phone Edition, telefones de área comum, Skype for Business e o aplicativo da Windows Store do Lync. Em clientes do Lync Phone Edition, depois que um usuário entrar e for autenticado com êxito fornecendo um PIN (número de identificação pessoal), o Skype for Business Server provisiona o URI do SIP para o telefone e provisiona um certificado assinado do Skype for Business Server ou um certificado de usuário que identifique Joe (ex: SN=joe@contoso.com ) para o telefone. Esse certificado é usado para autenticação com o Registrador e Serviços Web.
    
> [!NOTE]
> Recomendamos a habilitação do Kerberos e NTLM quando um servidor suporta autenticação para clientes remotos e empresariais. O Servidor de Borda e os servidores internos se comunicam para assegurar que somente a autenticação NTLM seja oferecida aos clientes remotos. Se somente Kerberos for habilitado nesses servidores, não poderão autenticar usuários remotos. Se os usuários empresariais também autenticarem com base no servidor, o Kerberos será usado. 
  
Se você usará clientes de aplicativo do Lync da Windows Store, deverá habilitar a autenticação de certificado.
  
### <a name="to-create-new-registrar-configuration-settings"></a>Para criar novas definições de configuração do Registrador

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.
    
4. Na página **Registrador**, clique em **Novo**
    
5. Em **Selecionar um Serviço**, clique no serviço ao qual o Registrador será aplicado e clique em **OK**.
    
6. Em **Nova Configuração do Registrador**, selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes e do suporte em seu ambiente:
    
   - **Habilitar autenticação Kerberos** para que os servidores no pool emitam desafios usando a autenticação Kerberos.
    
   - **Habilitar autenticação NTLM** para que os servidores no pool emitam desafios usando NTLM.
    
   - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.
    
7. Clique em **Confirmar**.
    
## <a name="modify-existing-registrar-configuration-settings"></a>Modificar definições de configuração existentes do Registrador

Você pode usar o Registrador para configurar protocolos de autenticação de servidor proxy. 
  
> [!NOTE]
> É recomendável que você habilite Kerberos e NTLM quando um servidor oferecer suporte a autenticação a ambos, clientes remotos e corporativos. O Servidor de Borda e servidores internos se comunicam para garantir que somente a autenticação NTLM seja oferecida a clientes remotos. Se somente Kerberos estiver habilitada nesses servidores, eles não poderão autenticar usuários remotos. Se os usuários corporativos também se autenticarem no servidor, Kerberos será usada. 
  
Siga estas etapas para modificar um Registrador Avançado existente. 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>Para modificar as definições de configuração existentes do registrador

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação à esquerda, clique em **Segurança** e em **Registrador Avançado**.
    
4. Na página **Registrador Avançado**, clique em um serviço, em **Editar** e em **Exibir detalhes**.
    
5. Em **Editar Configuração do Registrador Avançado**, selecione um ou mais dos itens a seguir, dependendo dos recursos dos clientes e do suporte em seu ambiente:
    
   - **Habilitar autenticação Kerberos** para que os servidores no pool tratem desafios usando a autenticação Kerberos.
    
   - **Habilitar autenticação NTLM** para que os servidores no pool emitam desafios usando NTLM.
    
   - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.
    
6. Clique em **Confirmar**.
    
### <a name="to-delete-registrar-configuration-settings"></a>Para excluir as definições de configuração do Registrador

1. Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.
    
4. Na página **Registrador** e no campo de pesquisa, digite todo ou parte do nome do Registrador que você deseja excluir.
    
5. Na lista, clique no Registrador que você deseja, clique em **Editar** e em **Excluir.**
    
6. Clique em **OK**.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Removendo definições de configuração do Registrador usando cmdlets do Windows PowerShell

Você pode excluir as definições de configuração do Registrador usando o Windows PowerShell e o cmdlet **Remove-CsProxyConfiguration.** Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>Para remover um conjunto específico de configurações de segurança do Registrador

- O comando a seguir remove as configurações de segurança do Registrador aplicadas ao servidor de atl-edge-011.litwareinc.com:
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>Para remover todas as configurações de segurança do Registrador aplicadas ao escopo do site

- O comando a seguir remove todas as configurações de segurança do Registrador aplicadas ao serviço registrador:
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>Para remover todas as configurações de segurança do Registrador que permitem a autenticação NTLM

- O comando a seguir exclui todas as configurações de segurança do Registrador que permitem o uso de NTLM para autenticação de cliente:
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

Para obter detalhes, [consulte Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).
  

