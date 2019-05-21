---
title: Gerenciar definições de configuração do registrador no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Resumo: Gerenciar definições de configuração do registrador do Skype for Business Server.'
ms.openlocfilehash: 4ad7815da0744a78cd72208ef390362bff26c2ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291169"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>Gerenciar definições de configuração do registrador no Skype for Business Server
 
**Resumo:** Gerenciar definições de configuração do registrador do Skype for Business Server.
  
É possível usar o Registrador para configurar métodos de autenticação do servidor proxy. O protocolo de autenticação que você especificar determina que tipo de desafios os servidores no pool vão gerar para os clientes. Os protocolos disponíveis são:
  
- **Kerberos** Esse é o esquema de autenticação baseado em senhas mais forte disponível para clientes, mas normalmente está disponível somente para clientes corporativos porque requer conexão do cliente a um centro de distribuição de chaves (controlador de domínio Kerberos). Essa configuração será apropriada se o servidor autenticar somente clientes empresariais.
    
- **NTLM** Esta é a autenticação baseada em senha disponível para clientes que usam um esquema de hash de resposta de desafio na senha. Essa é a única forma de autenticação disponível para clientes sem conectividade com um Centro de distribuição de chaves (controlador de domínio Kerberos), como usuários remotos. Se um servidor autenticar somente usuários remotos, escolha NTLM.
    
- **Autenticação de certificado** Esse é o novo método de autenticação quando o servidor precisa obter certificados de clientes do Lync Phone Edition, telefones de área comuns, Skype for Business e o aplicativo Lync da Windows Store. Nos clientes do Lync Phone Edition, após o usuário entrar e ter sido autenticado com êxito fornecendo um PIN (número de identificação pessoal), o Skype for Business Server, em seguida, provisiona o URI SIP para o telefone e provisiona um Skype for Business Server assinado certificado ou um certificado de usuário que identifica Joe (ex: SN=joe@contoso.com) para o telefone. This certificate is used for authenticating with the Registrar and Web Services.
    
> [!NOTE]
> Recomendamos a habilitação do Kerberos e NTLM quando um servidor suporta autenticação para clientes remotos e empresariais. O Servidor de Borda e os servidores internos se comunicam para assegurar que somente a autenticação NTLM seja oferecida aos clientes remotos. Se somente Kerberos for habilitado nesses servidores, não poderão autenticar usuários remotos. Se os usuários empresariais também autenticarem com base no servidor, o Kerberos será usado. 
  
Se você usará os clientes do aplicativo Lync da Windows Store, será necessário habilitar a autenticação de certificado.
  
### <a name="to-create-new-registrar-configuration-settings"></a>Para criar novas configurações de Registrador

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.
    
4. Na página **Registrado**, clique em **Novo**
    
5. Em **Selecionar um Serviço**, clique no serviço ao qual o Registrador será aplicado e clique em **OK**.
    
6. Em **Nova Configuração do Registrador**, selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes e do suporte em seu ambiente:
    
   - **Habilitar autenticação Kerberos** para que os servidores no pool emitam desafios usando a autenticação Kerberos.
    
   - **Habilitar autenticação NTLM** para que os servidores no pool emitam desafios usando NTLM.
    
   - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.
    
7. Clique em **Confirmar**.
    
## <a name="modify-existing-registrar-configuration-settings"></a>Modificar as configurações existentes do Registrador

Você pode usar o Registrador para configurar protocolos de autenticação de servidor proxy. 
  
> [!NOTE]
> Recomendamos a habilitação do Kerberos e NTLM quando um servidor suporta autenticação para clientes remotos e empresariais. O Servidor de Borda e os servidores internos se comunicam para assegurar que somente a autenticação NTLM seja oferecida aos clientes remotos. Se somente Kerberos for habilitado nesses servidores, não poderão autenticar usuários remotos. Se os usuários empresariais também autenticarem com base no servidor, o Kerberos será usado. 
  
Siga estas etapas para modificar um Registrador Avançado existente. 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>Para modificar as configurações existentes do Registrador

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.
    
4. Na página **Registrador Avançado**, clique em um serviço, em **Editar** e em **Exibir detalhes**.
    
5. Em **Editar Configuração do Registrador Avançado**, selecione um ou mais dos itens a seguir, dependendo dos recursos dos clientes e do suporte em seu ambiente:
    
   - **Habilitar autenticação Kerberos** para que os servidores no pool emitam desafios usando a autenticação Kerberos.
    
   - **Habilitar autenticação NTLM** para que os servidores no pool emitam desafios usando NTLM.
    
   - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.
    
6. Clique em **Confirmar**.
    
### <a name="to-delete-registrar-configuration-settings"></a>Para excluir as definições de configuração do Registrador

1. Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.
    
4. Na página **Registrador Avançado** e no campo de pesquisa, digite todo ou parte do nome do Registrador Avançado que você deseja excluir.
    
5. Na lista, clique no Registrador Avançado desejado, clique em **Editar** e em **Excluir**.
    
6. Clique em **OK**.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Como remover as configurações de registrador usando cmdlets do Windows PowerShell

Você pode excluir as definições de configuração do registrador usando o Windows PowerShell e o cmdlet **Remove-CsProxyConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>Para remover um conjunto específico de configurações de segurança do Registrador

- O seguinte comando remove as configurações de segurança do Registrador aplicadas ao servidor de borda atl-edge-011.litwareinc.com:
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>Para remover todas as configurações de segurança do Registrador aplicadas ao escopo do site

- O seguinte comando remove todas as configurações de segurança do Registrador aplicadas ao serviço registrador:
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>Para remover todas as configurações de segurança do Registrador que permitem a autenticação de NTLM

- O seguinte comando exclui todas as configurações de segurança do Registrador que permite o uso de NTLM para autenticação do cliente:
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

Para obter detalhes, consulte [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).
  

